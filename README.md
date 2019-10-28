# **SmartProducts**

SmartBiz the online storefront that will disrupt e-commerce.

## *SmartProducts API*

1.  Interact with the SmartBiz cloudservice to manage your online storefront.
2.  Get, Create, Update, and Delete product information to be displayed for your account.

<!-- theme: warning -->

> ### **Authentication**
>
> A valid SmartBiz API Key is needed to make requests to this API.

* * *

<!-- theme: info -->
># Endpoints

## _Jobs_

### Path

/products/{api key}/{category}

### Description

Interacts with the SmartBiz cloud service to manage products on the e-commerce site and mobile applications.

### Required Parameters

-   SmartBiz key
-   Product Category

### Operations
- get_jobs
- new_job
- update_job
- delete_job

<!-- theme: info -->
># Schema

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

<!-- theme: info -->
>## Samples

How to interact with the Products endpoint.

<!--
type: tab
title: New Product
-->

```javascript
function new_product(limit){
  var id, name, stock, pub;

  for (id = 0; i < id.length; i++) {
    return product_id, product_name, in_stock;
  }
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
    product.delete;
  }
}
```

<!-- type: tab-end -->

<!--
title: "Sample New Product"
lineNumbers: true
highlightLines: [[1,2], [4,5]]
-->