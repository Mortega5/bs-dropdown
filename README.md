# bs-dropdown

Create a dropdown using a polymer element. It's based on boostrap dropdown.

## Example
* Using content

``` html
<bs-dropdown btn_title="Content">
  <div class="menu-content">
    <p>Link 1</p>
    <p>Link 2</p>
    <p>Link 3</p>
  </div>
</bs-dropdown>
```

* Using menu_items Array
```html
<template id="bind" is="dom-bind">
  <bs-dropdown id="complexList" btn_title="Custom list items" menu_items="{{complexList}}"> </bs-dropdown>
</template>

<script>
  var bind = document.querySelector('#bind');
  bind.complexList = [
    {
      name: 'Load',
      onclick: function(){
        console.log('Clicked Load');
      },
      link:'#load',
      icon: 'folder-open'
    },
    {
      name: 'Save',
      onclick: function(){
        console.log('Clicked Save');
      },
      link:'#option2',
      icon: 'floppy-saved'
    },
    {
      name: 'Edit',
      onclick: function(){
        console.log('Clicked Edit');
      },
      link:'#edit',
      icon: 'pencil'
    }
  ]
</script
```
NOTE: menu_items can be a single array with the names of the options fields.
```json
  var option_list = ['Link1','Link2','Link3']
```
  or it can be an object with some camps:

  * Name: name of the field
  * onclick: function which will be invoke when the field is Clicked
  * icon: type of icon


* Using bs-dropdown-item (included in bs-dropdown)

```html
  <bs-dropdown btn_title="Toggle">
    <div class="menu-content">
      <bs-dropdown-item>Example</bs-dropdown-item>
      <bs-dropdown-item>Example</bs-dropdown-item>
      <bs-dropdown-item>Example</bs-dropdown-item>
    </div>
  </bs-dropdown>
```

## Properties

| Attribute  | Description                                            | Type    | Default  |
|------------|--------------------------------------------------------|---------|----------|
| btn_title  | Change the button title                                | Sting   | Dropdown |
| dropup     | Menu list is showed above the button                   | Boolean | false    |
| opened     | If true, menu list is showed                           | Boolean | false    |
| menu_items | If it is defined, all items in the array are menu items | Array   | []       |


## Methods

| Attribute | Description                           | return |
|-----------|---------------------------------------|--------|
| Open      | Open menu list                        |        |
| Close     | Close menu list                       |        |
| Toggle    | If menu list, it is opened, else closed |        |

## Style

### bs-dropdown

| Attribute                                        | Description                                                | Default |
|--------------------------------------------------|------------------------------------------------------------|---------|
| __--bs-dropdown-btn-toggle__              | Mixin applied to bs-dropdown button                 | {}      |
| __--bs-dropdown-btn-toggle-focused__      | Mixin applied to bs-dropdown button when is focused | {}      |
| __--bs-dropdown-box__            | Mixin aplied to menu box that contains menu options        | {}      |
| __--bs-dropdown-menuItem-hover__ | Mixin aplied to menu item when it is hovered               | {}      |
| __--bs-dropdown-divider__                 | Mixin aplied to divider                                    | {}      |

### bs-dropdown-item

| Attribute                                        | Description                                              | Default |
|--------------------------------------------------|----------------------------------------------------------|---------|
| __--bs-dropdown-item__                    | Mixin applied to bs-dropdown-item                 | {}      |
| __--bs-dropdown-item-hovered__            | Mixin applied to bs-dropdown-item when is focused | {}      |

## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install
