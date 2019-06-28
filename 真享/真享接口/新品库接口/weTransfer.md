### 	WeTransfer-Api

#### request

这个接口主要用于获取WeTransfer的每日库存

| Method | URL                                              |
| :----- | ------------------------------------------------ |
| GET    | lab.modacheva.com/json/json/realshare/stock.json |
| GET    | lab.modacheva.com/json/json/realshare/stock.zip  |

#### response

返回的是一个极大的Json文件，里面包含了每日上新的所有商品

| type        | params        | Values                                   |
| ----------- | ------------- | ---------------------------------------- |
| Json        | Products_date | str:timeStr (2019619)                    |
| Json(Array) | Dettagli      | array:product_list (product detail list) |

**Dettagli**

| type | params        | Values                          |
| ---- | ------------- | ------------------------------- |
| Json | COD           | string (spu of the product)     |
| Json | BRAND         | string (brand name of product)  |
| Json | MODEL         | string (brand_ui_id of product) |
| Json | COD_TEXSTYLE  | string (style of the text)      |
| Json | COD_COLER     | string (color code of text)     |
| Json | DESC_TEXSTYLE |                                 |
| Json | DESC_COLOR    |                                 |
| Json | SEASON        |                                 |
| Json | GENDER        |                                 |
| Json | EXIT          |                                 |
| Json | FAMILY        |                                 |
| Json | SUB-FAMILY    |                                 |
| Json | CAT           |                                 |
| Json | SELLOUT       |                                 |
| Json | DISCOUNT      |                                 |
| Json | PIC1          |                                 |
| Json | COD_TGL       |                                 |
| Json | SUM_STOCK     |                                 |
| Json | BARCODE       |                                 |
| Json | TGL           |                                 |
| Json | STOCK         |                                 |

