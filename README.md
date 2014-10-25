jquery.detectSwipe
==================

Gives easy access to left/right/up/down swipe events for iOS and other touch devices.

Based on Andreas Waltl's [jQuery TouchWipe](http://www.netcu.de/jquery-touchwipe-iphone-ipad-library).

How to use
----------
````js
$(".selector").on('swipeleft',  function(){ /*...*/ })
        .on('swiperight', function(){ /*...*/ })
        .on('swipeup',    function(){ /*...*/ })
        .on('swipedown',  function(){ /*...*/ });
````
This won't have any effect on non-touch devices. You can rely on:
````js
$.detectSwipe.enabled // true on touch devices, false otherwise
````
Global setting:

````js
$.detectSwipe.threshold // The number of pixels your finger must move to trigger a swipe event.  Defaults is 20.
$.detectSwipe.preventDefault // Should touchmove events be prevented?  Defaults to true.
````
#### What's in this fork?

A new global setting!

````js
$.detectSwipe.scrollExceptionCondition
````
    
In case there are situations where you don't want swipe to be enabled, like you have an overflow container that you want to take the scroll. Pass this a function that returns true when that exception condition is met. Here's an example

````js
$.detectSwipe.scrollExceptionCondition = function(){
	return ($('body').attr('data-side-drawer-open') == 'true' || $('body').attr('data-side-drawer-state') == 'changing' );
}
````
