# Content Template Engine

[![Build Status](https://travis-ci.org/miya0001/content-template-engine.svg?branch=master)](https://travis-ci.org/miya0001/content-template-engine)

This plugin enables Twig template engine in the WordPress contents.

You can post article like following.

```
{% if post.my_custom_field %}
    Hello {{ post.my_custom_field }}!
{% endif %}
```

http://twig.sensiolabs.org/

## Screenshot

### Editor screen

![](https://www.evernote.com/l/ABX1NGcc6cZKSpJ7p9l93rLkCOMI19_In_UB/image.png)

### On your site

![](https://www.evernote.com/l/ABV8L4Vn8YJM9LWXv5q8bi_lc-bhlLD_uV8B/image.png)

## Requires

* PHP 5.3 or later
* WordPress 4.3 or later

## How to use

1. Install and activate this plugin.
2. Open post screen in your WordPress.
3. Check the "Enable the Twig template engine" in meta box.
4. Write template.

![](https://www.evernote.com/l/ABUZpPc5Xw5HiIEk8sbOlaUQemDl2j2Hj7wB/image.png)

## Template examples

### Custom fields

```
{% if post.my_custom_field %}
    Hello {{ post.my_custom_field }}!
{% endif %}
```

### With [Advanced Custom Fields](http://www.advancedcustomfields.com/)

```
{% if acf.name %}
    Hello {{ acf.name }}!
{% endif %}
```

#### With [The Repeater Field](http://www.advancedcustomfields.com/add-ons/repeater-field/)

```
<ul>
{% for fruit in acf.fruits %}
    <li>{{ acf.fruit.name }}: {{ acf.fruit.price }}</li>
{% endfor %}
</ul>
```

### Conditional tags

```
{% if is_home() %}
This is the Home.
{% endif %}
```

## Filters

There are some cutom filters for WordPress.

* esc_html
* esc_attr
* esc_textarea
* esc_js
* esc_url

```
{{ post.post_title | esc_html }}
```

If you want to output HTML, you have to use `raw`.

```
{{ post.post_title | raw }}
```

See also Twig documentation:

http://twig.sensiolabs.org/doc/filters/index.html

## Note

### Some default functions are disabled by security reason.

* `{{ constant() }}`

### Disable visual editor

Visual editor sometimes breaks template, so we recommend you to disable visual editor.

There is a meta box for disable Visual editor in editing screen. It is allowed only users who can publish posts.

## How to contribute

Clone this repository.

```
$ git@github.com:miya0001/content-template-engine.git
```

Change into plugin.

```
$ cd content-template-engine
```

Run `composer install`.

```
$ composer install
```
