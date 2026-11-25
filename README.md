# CanteenFreeOrder

## Community Problem
In our school community, students struggle to buy food during their limited break time because they have to wait in long queues at the school canteen.

## Solution
CanteenFreeOrder is a simple food pre-ordering website that allows students to select their food, enter their name, choose a quantity and pickup date, and submit their orders before their break.

## Functional Requirement FR-01
Students can submit a food pre-order by selecting a food item, entering their name, quantity, and pickup date. The system automatically calculates the total price and saves the order using localStorage. It validates blank names, missing food, quantities outside 1–50 (including decimals), and past pickup dates. Students can review orders and edit or cancel pending orders; cancellation is confirmed and the order remains in the list as cancelled.

## Features
- Food menu with prices
- Food selection
- Quantity input
- Pickup date validation
- Automatic total price calculation
- Order summary
- Submit orders
- Edit pending orders
- Cancel pending orders
- Order history
- localStorage persistence

## Technologies Used
- HTML
- CSS
- JavaScript
- localStorage

## Privacy
This project uses made-up student information for demonstration purposes only. No real personal data is used.

## How to Run
1. Download or clone the repository.
2. Open index.html in your browser.
3. Select a food item.
4. Enter a made-up student name, quantity, and pickup date.
5. Submit and test your order.

Orders are stored in the current browser and device under the `canteenOrders` localStorage key. Clearing browser storage removes them. Menu photos load from Unsplash; ordering and persistence do not depend on the photos.

## Manual Test Table

| # | Test | Steps / input | Expected result |
|---|---|---|---|
| 1 | Valid pre-order | Select a menu item; enter a name; quantity `2`; choose today or a future date; submit | Success popup shows item, quantity, total, and pending status; order appears in the list |
| 2 | Persistence | Submit an order and reload the page | The order remains in the list |
| 3 | Blank name | Leave name blank and submit otherwise valid details | Inline validation asks for a name; no order is saved |
| 4 | Missing food | Enter a name, quantity, and date without selecting food | Inline validation requests a menu selection; no order is saved |
| 5 | Quantity boundary | Submit with quantity `1`, then `50` | Both quantities are accepted and totals are correct |
| 6 | Invalid quantity | Submit with `0`, `51`, or a decimal | Inline validation rejects the quantity; no order is saved |
| 7 | Past pickup date | Choose a date before today | Date is rejected; no order is saved |
| 8 | Edit pending order | Choose Edit, change a value, and update | Success popup indicates the update; saved values and total change |
| 9 | Keep pending order | Choose Cancel Order, then Keep Order | Confirmation closes and order remains pending |
| 10 | Confirm cancellation | Choose Cancel Order, then Yes, Cancel | Order changes to Cancelled; edit/cancel controls are removed |
| 11 | Responsive layout | Open at mobile and desktop viewport widths | Content stays readable; form and summary stack at narrow widths |