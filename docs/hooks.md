---
id: hooks
title: Hooks
---

## Hooks

Hooks are a way for one piece of code to interact/modify another piece of code.
They make up the foundation for how plugins and themes interact with WordPress Core, but they’re also used extensively by Core itself.

Routers can execute hooks using controllers methods just add hook on routes.php file:

```
$router->hook("hook_name", "MyPluginController@my_hook");
```

For example, if you want to append a shipping calculator in woocommerce shop:

```
$router->hook('woocommerce_after_add_to_cart_button', 'ShippingController@shipping_form');
```

In controller:
```
  public function shipping_form() {
    global $product;
    $height = $product->get_height();
    $width = $product->get_width();
    $length = $product->get_length();
    return $this->generateView('shipping-form', [
      'height' => $height,
      'width' => $width,
      'length' => $length
    ]);
  }
```

