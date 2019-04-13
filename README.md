### scrollMonitor
---
https://github.com/stutrek/scrollMonitor

```js
var scrollMonitor = require();
var myElement = document.getElementById("itemToWatch");
var elementWatcher = scrollMonitor.create( myElement );
elementWatcher.enterViewport(function(){
  console.log( 'I have entered the viewport' );
});
elementWatcher.exitViewport(function(){
  console.log(  'I have left the viewport' );
});

var containerElement = document.getElementById("container");
var containerMonitor = scrollMonitor.createContainer(containerElement);
var childElement = document.getElementById("child-of-container");
var elementWatcher = containerMonitor.create(childElement);
elementWatcher.enterViewport(funciton(){
  console.log( 'I have entered the viewport' );
});
elementWatcher.exitViewport(function(){
  console.log( 'I have left the viewport' );
});

var watcher = scrollMonitor.create( $element );
watcher.lock();
watcher.exitViewport(function(){
  $element.addClass('fixed');
});
watcher.eneterViewport(function(){
  $element.removeClass( 'fixed' );
});

scrollMonitor.create( element, 200 )
scrollMonitor.create( element, -200 )
scrollMonitor.create( element, {top: 200, bottom: 50})
scrollMonitor.create( element, {top: 200})
```

```sh
npm install
npm test
curl http://localhost:7357
```

```js
// src/container.js
var { isOnServer, isInBrowser, eventTypes } = require('./constants');
var Watcher = require('./watcher');

function getViewportHeight (element) {
  if (isOnServer) {
    return 0;
  }
  if (element === document.body) {
    return window.innerHeight || document.documentElement.clientHeight;
  } else {
    return element.clientHeight;
  }
}



```

