# CampusEats — Services, Contracts & Validation

## 1. Capabilities

1. **Authenticate Users** — verify users and provide secure access to CampusEats.
2. **Browse Menus** — allow customers to view restaurants, menu items, prices, and availability.
3. **Place Orders** — allow customers to select food items and submit orders.
4. **Process Payments** — process customer payments and maintain payment status.
5. **Manage Orders** — allow restaurant staff to accept, prepare, and complete orders.
6. **Track Orders** — allow customers to view the current status of their orders.

---

# 2. Service Contracts

## 2.1 Identity Service

| Operation | Input | Output | Errors |
|---|---|---|---|
| `authenticateUser` | username, password | authentication result, user role | Invalid credentials, user not found |

## 2.2 Catalogue Service

| Operation | Input | Output | Errors |
|---|---|---|---|
| `listRestaurants` | campus/location | available restaurants | No restaurants available |
| `getMenu` | restaurant identifier | menu items, prices, availability | Restaurant not found |
| `checkItem` | restaurant identifier, item identifier, quantity | item availability, current price | Item not found, item unavailable |

## 2.3 Order Service

| Operation | Input | Output | Errors |
|---|---|---|---|
| `placeOrder` | user identifier, restaurant identifier, selected items, payment details | order confirmation, order status, payment status | Invalid item, item unavailable, payment failed |
| `getOrder` | order identifier | order details, current status | Order not found, unauthorized access |
| `updateOrderStatus` | order identifier, new status | updated order status | Order not found, invalid status transition |

## 2.4 Payment Service

| Operation | Input | Output | Errors |
|---|---|---|---|
| `authorizePayment` | order information, payment details, amount | payment result, payment status | Payment declined, invalid payment details |

## 2.5 Notification Service

| Operation | Input | Output | Errors |
|---|---|---|---|
| `sendOrderUpdate` | user identifier, order identifier, message | notification result | User not found, notification delivery failed |

---

# 3. placeOrder — Full Specification

## Purpose

`placeOrder` allows a customer to submit a food order and receive confirmation of the order and payment status.

## Inputs

- User identifier
- Restaurant identifier
- Selected menu items and quantities
- Payment details

## Outputs

- Order confirmation
- Order status
- Payment status

## Error Cases

| Error | Meaning |
|---|---|
| `UserNotFound` | The customer cannot be located or authenticated. |
| `RestaurantNotFound` | The selected restaurant is unavailable. |
| `ItemNotFound` | A requested menu item does not exist. |
| `ItemUnavailable` | A requested menu item is currently unavailable. |
| `PaymentFailed` | Payment authorization was unsuccessful. |
| `OrderCreationFailed` | The order could not be completed. |

## Internal Details Hidden From Callers

Callers do not need to know:

- how orders are stored;
- how menu items are stored;
- how item availability is checked internally;
- how payment processing is implemented;
- how order status is stored or changed;
- which database or technology is used;
- how services communicate internally.

## Internal Flow

Customer calls `placeOrder`.

1. Order Service validates the requested items with Catalogue Service.
2. Order Service requests payment authorization from Payment Service.
3. Order Service creates the order after successful validation and payment.
4. Order Service returns the order confirmation and status.

---

# 4. Service Validation

| Service | Reachable | Self-contained | Has Contract | Independent | Loosely Coupled | Fix |
|---|---|---|---|---|---|---|
| Identity Service | Yes | Yes | Yes | Yes | Yes | None |
| Catalogue Service | Yes | Yes | Yes | Yes | Yes | None |
| Order Service | Yes | Yes | Yes | Yes | No | Use service contracts for Catalogue and Payment communication; never share their internal data. |
| Payment Service | Yes | Yes | Yes | Yes | Yes | None |
| Notification Service | Yes | Yes | Yes | Yes | Yes | None |