# **SmartProducts**

SmartBiz the online storefront that will disrupt e-commerce.

## *SmartProducts API*

1.  Interact with the SmartBiz cloudservice to manage your online storefront.
2.  Get, Create, Update, and Delete product information to be displayed for your account.

Do you want to transform your business and bring your products to a worldwide digital market? Then the **SmartProducts API** is for you! Integrate our Storefront e-commerce platform with your own inventory management solution and manage thousands of products at scale. 

At **SmartBiz** we believe in arming small businesses with the tools they need in an increasingly digital and competitive marketplace. We make our APIs simple, easy to use and understand and we make a lot of them! *Leverage the power of our cloud service to develop the solutions you need to succeed.*

This API lets you add, delete, update and view products on the Storefront with additional features such as stock and pricing management. 

<!-- theme: warning -->

> ### **Authentication**
>
> A valid SmartBiz API Key is needed to make requests to this API.

* * *
# Endpoints

## _Products_

### Path

/products/{api key}/{category}

### Description

Interacts with the SmartBiz cloud service to manage products on the e-commerce site and mobile applications.

### Required Parameters

-   SmartBiz key
-   Product Category

### Operations
- get_product
- create_product
- update_product
- delete_product

# Schema

<!--
type: tab
title: Products
-->

```yaml json_schema
title: Products
x-tags:
  - Products
type: object
description: Products to be displayed on the storefront.
x-examples: {}
properties:
  products:
    type: array
    items:
      type: object
      properties:
        product_id:
          type: integer
          format: int64
        product_name:
          type: string
        in_stock:
          type: boolean
        price:
          type: number
          format: float
        published:
          type: boolean
        created_at:
          type: string
          format: date-time
        last_update:
          type: string
          format: date-time
        views:
          type: integer
        purchases:
          type: integer
        returns:
          type: integer
      required:
        - product_id
        - product_name
        - in_stock
        - price
        - published
  category:
    type: object
    properties:
      category id:
        type: integer
        format: int64
      category:
        $ref: ./reference/smartbiz/models/category.v1.yaml
  manufacturer:
    type: object
    properties:
      manufacturer id:
        type: integer
        format: int64
      'manufacturer ':
        $ref: ./manufacturer.v1.yaml
```
<!--
type: tab
title: Category
-->
```yaml json_schema
title: Category
type: object
x-tags:
  - Products
description: Categories to organize products displayed on the storefront.
properties:
  category id:
    type: integer
    format: int64
  category_name:
    type: string
  created_at:
    type: string
    format: date-time
  last_update:
    type: string
    format: date-time
required:
  - category id
  - category_name
```
<!--
type: tab
title: Manufacturer
-->
```yaml json_schema
title: Manufacturer
type: object
x-tags:
  - jobs
description: Manufacturer of a product.
properties:
  manufacturer_id:
    type: integer
  manufacturer_name:
    type: string
  created_at:
    type: string
    format: date-time
  updated_at:
    type: string
    format: date-time

```
<!-- type: tab-end -->

* * *
# Samples

How to interact with the Products endpoint.

<!--
type: tab
title: New Product
-->

```javascript
function new_product(limit){
  var id = product_id; 
  var name = product_name;
  var stock = in_stock;
  var new_product;

  new_product = product.create(id, name, stock);
}
```

<!--
type: tab
title: My Second Tab
-->

```javascript
function delete_product(limit){
  var id, name, stock, pub;

  for (id = 0; i < id.length; i++) {
    product.delete();
  }
}
```

<!-- type: tab-end -->

<!--
title: "Sample New Product"
lineNumbers: true
highlightLines: [[1,2], [4,5]]
-->