# Knawat-PHP-SDK
A PHP wrapper for the Knawat REST API. Easily interact with the Knawat REST API using this library.

## Installation

```
composer require knawat/knawat-php-sdk
```

## Getting started

Check out the Knawat REST API endpoints and data that can be manipulated in <https://mp.knawat.io/>.

## Setup

Setup for the new Knawat REST API integration:

```php
require __DIR__ . '/vendor/autoload.php';

use Knawat\MP;

$mp = new MP(
    'consumer_key_XXXXXXXXXXXXXXXXXXXXXXXXXXX',
    'consumer__XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX'
);
```

### Options

|       Option      |   Type   | Required |                Description                 |
| ----------------- | -------- | -------- | ------------------------------------------ |
| `consumer_key`    | `string` | yes      | Your Store's API consumer key              |
| `consumer_secret` | `string` | yes      | Your Store's API consumer secret           |

# Methods
## Product Methods

### getProducts (GET Products)
```php
$mp->getProducts($limit, $page, $lastupdate);
```
|    Params    |   Type     |                        Description                         |
| ------------ | ---------  | ---------------------------------------------------------- |
| `limit`      | `Integer`  | Number of products to retrieve. `Default: 25`              |
| `page`       | `Integer`  | Number of the page to retrieve. `Default: 1`               |
| `lastupdate` | `TimeStamp` | Optional. UTC Timestamp of last import. for get only updated products after this Timestamp |

### getProductBySku (GET Product By SKU)
```php
$mp->getProducts($sku);
```
|    Params  |   Type    |                        Description                         |
| ---------- | --------  | ---------------------------------------------------------- |
| `sku`      | `string`  | SKU of Product you want to get                             |

## Order Methods
### getOrders (GET Orders)
```php
$mp->getOrders($limit, $page);
```
|    Params    |   Type     |                        Description                         |
| ------------ | ---------  | ---------------------------------------------------------- |
| `limit`      | `Integer`  | Number of orders to retrieve. `Default: 10`                |
| `page`       | `Integer`  | Number of the page to retrieve. `Default: 1`               |


### getOrderById (GET Order By Knawat Order Id)
```php
$mp->getOrderById($order_id);
```
|    Params  |   Type   |                        Description                         |
| ---------- | -------- | ---------------------------------------------------------- |
| `order_id` | `string` |  Knawat Order ID                                           |



### createOrder (Create Order)
```php
$mp->createOrder($order_data);
```
|    Params    |   Type     |                        Description                         |
| ------------ | ---------  | ---------------------------------------------------------- |
| `order_data` | `array`    |  Array of Order Data for create order                      |


### updateOrder (Update Order)
```php
$mp->updateOrder($order_id, $order_data);
```
|    Params    |   Type     |                        Description                         |
| ------------ | ---------  | ---------------------------------------------------------- |
| `order_id`   | `string`   |  Knawat Order ID                                           |
| `order_data` | `array`    |  Array of Updated Order Data for create order              |



## REST Methods

|    Params    |   Type   |                         Description                          |
| ------------ | -------- | ------------------------------------------------------------ |
| `endpoint`   | `string` | WooCommerce API endpoint, example: `catalog/products` or `orders/{order_id}` |
| `data`       | `array`  | Only for POST and PUT, data that will be converted to JSON   |

### GET

```php
$mp->get($endpoint)
```

### POST

```php
$mp->post($endpoint, $data)
```

### PUT

```php
$mp->put($endpoint, $data)
```

### DELETE

```php
$mp->delete($endpoint)
```
