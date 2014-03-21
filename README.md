# Mobify Bellows

A responsive, mobile-first accordion UI module for progressive disclosure on the web.

## Docs

You can find docs and examples here: http://mobify.github.io/bellows.

## Usage

    <!-- include bellows.css -->
    <link rel="stylesheet" href="http://cdn.mobify.com/modules/bellows/0.3.3/bellows.min.css">
    <link rel="stylesheet" href="http://cdn.mobify.com/modules/bellows/0.3.3/bellows-style.min.css">

    <!-- the markup -->
    <ul class="bellows">
      <!-- the items -->
      <li class="bellows__item">
        <h3 class="bellows__header">
          <!-- header title -->
          <a>Tab1</a>
        </h3>
        <div class="bellows__content">
          <div class="bellows__inner-content">
            <!-- content for item -->
            <h2>Content 1</h2>
            <h2>Lorem Ipsum</h2>
          </div>
        </div>
      </li>
      <li class="bellows__item">
        <h3 class="bellows__header">
          <a>Tab2</a>
        </h3>
        <div class="bellows__content">
          <div class="bellows__inner-content">
            <h2>Content 2</h2>
            <p>Lorem Ipsum</p>
          </div>
        </div>
      </li>
      <li class="bellows__item">
        <h3 class="bellows__header">
          <a>Tab3</a>
        </h3>
        <div class="bellows__content">
          <div class="bellows__inner-content">
            <h2>Content 3</h2>
            <p>Lorem Ipsum</p>
          </div>
        </div>
      </li>
    </ul>

    <!-- include zepto.js or jquery.js -->
    <script src="http://code.jquery.com/jquery-1.10.2.min.js"></script>
    <!-- include bellows.js -->
    <script src="http://cdn.mobify.com/modules/bellows/0.3.0/bellows.js"></script>
    <!-- construct the bellows -->
    <script>$('.bellows').bellows();
    </script>

## Methods

### bellows()

Initializes the bellows.

    $('.bellows').bellows();

### bellows(options)

Initialize with options.

    $('.bellows').bellows({
      {
        ...
        options (refer below)
        ...
      }
    });

### Storing bellows object for future use

    var $bellows = $(".bellows"); // A Zepto element array is returned
    var bellows = $bellows[0].bellows; // We access the appropriate bellows from the above array

### unbind()

Removes any tap, mouse, and other event handlers from the bellows.

    bellows.unbind();

### bind()

Restores the tap, mouse, and other event handlers for the bellows.

    bellows.bind();

### destroy()

Unbinds the events from the bellows, and removes it from the DOM.

    bellows.destroy(); // destroys the DOM element and the jQuery bindings
    bellows = null; // destroys the Mobify bellows object as well

### open($item)

Open the selected bellows item

    bellows.open($(".bellows__item").eq(2));

### close($item)
    
Close the selected bellows item

    bellows.close($("#some-item"));

### recalculateItemHeight($item)

Recalculate the heights of bellows item elements. This is used when the heights of the content have changed after creation of the bellows.

    bellows.recalculateItemHeight($(".bellows__item"));

## Class names

Set the class names for the different elements, if deviating from the defaults.
  
    $(".bellows").bellows({
      closedClass: 'bellows--closed',
      openedClass: 'bellows--opened',
      activeClass: 'bellows--active',
      contentClass: 'bellows__content',
      innerContentClass: 'bellows__inner-content',
      headerClass: 'bellows__header',
      itemClass: 'bellows__item'
    });

## Event hooks

### onTransitionDone: functionName

Execute this function every time the selected bellows item is opened or closed.

    $(".bellows").bellows({
        onTransitionDone: function() { console.log("Animation done"); }
    });

### onOpened: functionName

Execute this function every time the selected bellows item is opened.

    $(".bellows").bellows({
        onOpened: function() { console.log("Opened"); }
    });

### onClosed: functionName

Execute this function every time an bellows item is closed
    
    $(".bellows").bellows({
        onClosed: function() { console.log("Closed"); }
    });

## Browser Compatibility


| Browser           | Version | Support                    |
|-------------------|---------|----------------------------|
| Safari            | 4.0+    | Supported.                 |
| Firefox           | 3.5-3.6 | Degraded. No transitions.  |
| Firefox           | 4.0+    | Supported                  |
| Chrome            | 9.0+    | Supported                  |
| Opera             | 12.0+   | Supported.                 |
| Internet Explorer | 6-7.0   | Not Supported              |
| Internet Explorer | 8.0     | Degraded. Bellows is not collapsible.  |
| Internet Explorer | 9.0     | Degraded. No transitions.  |
| Internet Explorer | 10.0    | Supported                  |
| Mobile Safari     | 3.1.x   | Degraded. No transitions   |
| Mobile Safari     | 4.0+    | Supported                  |
| Android Browser   | 2.1+    | Supported                  |
| Chrome (Android)  | 1.0+    | Supported                  |
| Firefox (Android) | 1.0+    | Supported                  |
| Windows Phone     | 7.5     | Degraded. No transitions.  |

## Building
### Requirements
* [node.js 0.8.x/npm](http://nodejs.org/download/)

### Steps
1. `npm install -g grunt-cli`
2. `npm install`
3. `grunt`

The build directory will be populated with minified versions of the css and 
javascript files and a .zip of the original source files (for distribution and
use with whatever build system you might use).

