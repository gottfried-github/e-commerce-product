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

### Admin
Products should be sorted by `date`. 