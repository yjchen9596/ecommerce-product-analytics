# Data Dictionary

This document describes the fields and event definitions in the eCommerce Behavior Data from Multi-Category Store dataset.

## Dataset Schema

| Property          | Description                                                                                                                                                      |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| event_time        | Time when event happened at (in UTC).                                                                                                                            |
| event_type        | Only one kind of event: purchase.                                                                                                                                |
| product_id        | ID of a product                                                                                                                                                  |
| category_id       | Product's category ID                                                                                                                                            |
| category_code     | Product's category taxonomy (code name) if it was possible to make it. Usually present for meaningful categories and skipped for different kinds of accessories. |
| brand             | Downcased string of brand name. Can be missed.                                                                                                                   |
| price             | Float price of a product. Present.                                                                                                                               |
| user_id           | Permanent user ID.                                                                                                                                               |
| ** user_session** | Temporary user's session ID. Same for each user's session. Is changed every time user come back to online store from a long pause.                               |

### Event Types

The event_type field represents the action performed by a user.

`Event` - Description <br>
`view` - User viewed a product.<br>
`cart` - User added a product to their shopping cart.<br>
`remove_from_cart` - User removed a product from their shopping cart.
`purchase` - User purchased a product.

### Sessions and Purchases

A single user_session can contain multiple purchase events.

Multiple purchase events within the same session may represent multiple products belonging to the same order. Therefore, a purchase event should not automatically be interpreted as a unique order without additional validation during the analysis.

### Source

Dataset: [eCommerce Behavior Data from Multi-Category Store](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store) <br>
Author: Michael Kechinov <br>
Data provided by: REES46 Marketing Platform