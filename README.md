# Tabs with HTML and CSS only

This is an example of HTML page with tabs with CSS only. It highlights current tab and it also handles default tab.

The key is in re-ordering of markup to be able to use `+` CSS selector for our benefit for highlighting default tab when URL has no hash in it. This thing requires your browser to support grid layout. Also pseudo selectors.

If you gonna play with it i assure you naming your tabs "one" "two" "three" isn't a good idea. It will make your head spin.

## Markup

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <style type="text/css" media="all">
nav {
  width: 200px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
nav > a {
  grid-row: 1;
}
nav > a.menu{
  grid-column: 1;
}
nav > a.view{
  grid-column: 2;
}
nav > a.settings{
  grid-column: 3;
}

#menu:not(:target) {
  display: none;
}
#view:not(:target) {
  display: none;
}
#settings:not(:target) {
  display: none;
}
#settings:not(:target) + #view:not(:target) + #menu:not(:target) {
  display: block;
}
    </style>
    <title>CSS only tabs</title>
  </head>
  <body>
    <div class="tabbed-area">
      <div class="box-wrap">
        <div class="tab" id="settings">
          <nav>
            <a class="settings" href="#settings"><b>Settings</b></a>
            <a class="view" href="#view">View</a>
            <a class="menu" href="#menu">Menu</a>
          </nav>

          settings
        </div>

        <div class="tab" id="view">
          <nav>
            <a class="settings" href="#settings">Settings</a>
            <a class="view" href="#view"><b>View</b></a>
            <a class="menu" href="#menu">Menu</a>
          </nav>

          view
        </div>

        <div class="tab" id="menu">
          <nav>
            <a class="settings" href="#settings">Settings</a>
            <a class="view" href="#view">View</a>
            <a class="menu" href="#menu"><b>Menu</b></a>
          </nav>

          menu
        </div>
      </div>
    </div>
  </body>
</html>
```

Or `index.html` in this repo.

## Sources

* https://css-tricks.com/css3-tabs/
* https://www.sitepoint.com/css-selectors-not-target/
* https://webdesign.tutsplus.com/tutorials/a-few-different-css-methods-for-column-ordering--cms-27079

## License

MIT
