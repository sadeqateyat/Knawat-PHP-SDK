<p align="center"><a href="https://knawat.com/"><img src="https://knawat.com/wp-content/uploads/2017/10/253_77.png" alt="Knawat"></a></p>

[![Join the chat at https://gitter.im/Knawat/Lobby](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Knawat/Lobby)

# Knawat-PHP-SDK
A PHP wrapper for the Knawat Dropshipping REST API. Easily interact with the Knawat Dropshipping REST API using this library.

## Installation

```
composer require knawat/knawat-php-sdk
```

## Getting started

Check out the Knawat Dropshipping REST API endpoints and data that can be manipulated in <https://mp.knawat.io/>.

## Setup

Setup for the new Knawat Dropshipping REST API integration:

```php
require __DIR__ . '/vendor/autoload.php';

use Knawat\MP;

$mp = new MP(
    'consumer_key_XXXXXXXXXXXXXXXXXXXXXXXXXXX',
    'consumer_secret_XXXXXXXXXXXXXXXXXXXXXXXX'
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
$mp->getProducts($limit, $page, $lastupdate, $args);
```
|    Params    |   Type     |                        Description                         |
| ------------ | ---------  | ---------------------------------------------------------- |
| `limit`      | `Integer`  | Number of products to retrieve. `Default: 25`              |
| `page`       | `Integer`  | Number of the page to retrieve. `Default: 1`               |
| `lastupdate` | `TimeStamp` | Optional. UTC Timestamp of last import. for get only updated products after this Timestamp |
| `args`       | `array`    | Optional. More params that you want to pass to API. [More info](https://docs.knawat.io/#tag/My-Products/paths/~1catalog~1products/get) |

### getProductBySku (GET Product By SKU)
```php
$mp->getProductBySku($sku);
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

## Reporting Security Issues
To disclose a security issue to our team, [please submit a report here](https://knawat.com/contact/).

## Support & Chat
Developers are welcome here, please create issue or [chat with us https://gitter.im/Knawat/Lobby](https://gitter.im/Knawat/Lobby). This repository is not suitable for Knawat customers support. Please don't use our issue tracker for support requests, but for Knawat Dropshipping PHP SDK issues only. Support can take place through [Knawat support portal](https://help.knawat.com/hc/en-us/requests/new/) which is available for free.

Support requests in issues on this repository will be closed on sight.

## Contributing to Knawat
If you have a patch or have stumbled upon an issue with Knawat PHP SDK, you can contribute this back to the code. Please create a pull request.

## Check also
* [Knawat RESTful API](https://mp.knawat.io)
* [WooCommerce Dropshipping Plugin](https://github.com/Knawat/dropshipping-woocommerce)
* [Magento 2 Module](https://github.com/Knawat/knawat-dropshipping-magento2)
* [OpenCart Module](https://github.com/Knawat/knawat-dropshipping-opencart)
