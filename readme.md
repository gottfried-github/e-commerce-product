# Product
## The nature of product
Product is the only and main entity. There's no variation of one and the same product, so there's no need for different items of the same product. 

## Product visibility to the visitor
Admin can add products that are not visible to the visitor. A product can be made visible to the visitor only if all it's characteristics have been specified.

## Product characteristics
Product should have the following characteristics:
* `name`
* `description`
* `price`
* `in stock`
* `date`
* `cover photo`
* `photos`
* `all photos`

### Photos
Each product has it's own set of photos. There's photos that are visible to the admin (`all photos`) and photos that are visible to visitor (`photos`). The latter is a subset of the former. 

# Products view
## Which products to display
Visitor should see all products that are made visible by the admin. They should be able to select whether to see products that are out of stock together with those that are in stock or only those that are in stock. 

Admin should see all products: both those that are not visible to visitor and those that are.

## Sorting
### Visitor
If out of stock products are visible, they should go after all products that are in stock, no matter how the products are otherwise sorted.

#### Characteristics to sort by
Products should be sorted by either `name`, `price` or `date`.

#### Default sort characteristic
The default characteristic to sort by should be `date`.

#### Sort order
Sort order should be this: 
1. `date`: *descending* 
2. `price`: *ascending*
3. `name`: *ascending*

When one of the above characteristics is chosen to sort by first, the other charactertistics should preserve their relative order. E.g., if sorted by `price`, the sort order should be: `price`, `date`, `name`; if sorted by `name`, the sort order should be: `name`, `date`, `price`.

### Admin
Products should be sorted by `date`. 

# Administration
## Relation between database and files
Each product has a set of photos, associated with it.

These photos are stored in the filesystem and their locations are stored in the database.

1. there should be no files on the filesystem which are not referenced from the database
2. there should be no photo entries in the database for which there is no file on the filesystem
3. when the user adds or removes photos, if the operation on one of the photos fails, none of the photos should be added or removed
4. when the user removes a product from the database, all photos, associated with it should be removed from the database and from the filesystem
5. when the user removes a product, if the removal fails, no photos should be removed from either the database or filesystem

# UI design
## Mobile menu view
The contents of the menu should be centered, as in graphical design. But if the contents exceeds the viewport height, it should be scrollable.

## Header and footer width difference on different pages
For example, on the page where products are displayed, the max width of the header and the footer should be larger, to corelate with the max width of the products view (as showed in the graphical design). On the other hand, on the page where an individual product is displayed, the max width of the product view is smaller, so the max width of header and footer should be smaller too.

## Dropdown width and positioning
If items in the dropdown are wider than the head, then the dropdown should be aligned right. If they are narrower, then the dropdown should be aligned left and have the width of the head. This is displayed in the graphical design.