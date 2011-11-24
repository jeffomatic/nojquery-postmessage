### non-jQuery fork by Jeff Lee

I'm a fan of the minimal interface of this plugin, but for various reasons I didn't want to be forced to include jQuery. Luckily, the dependencies on jQuery were minimal.

This fork consists of the following changes:

1. The `postMessage` and `receiveMessage` functions can now be attached to an arbitrary namespace, rather than just jQuery. This defaults to the global (`window`) namespace. You can change this by modifying the argument passed into the outer namespacing function.
2. I've removed the check for Opera 9.64, which used `$.browser`. There were at least three different GitHub users requesting the removal of this "Opera sniff" on the original project's Issues page, so I figured this would be a relatively safe change.
3. `postMessage` no longer uses `$.param` to serialize messages that are not strings. I actually prefer this structure anyway. `receiveMessage` does not implement a corresponding deserialization step, and as such it seems cleaner and more symmetric to leave both data serialization and deserialization to the client.
4. The use of `$.isFunction` is replaced by a functionally-identical check.
5. The `$:nomunge` YUI option is no longer necessary.

# jQuery postMessage: Cross-domain scripting goodness #

[http://benalman.com/projects/jquery-postmessage-plugin/](http://benalman.com/projects/jquery-postmessage-plugin/)

Version: 0.5, Last updated: 9/11/2009

jQuery postMessage enables simple and easy window.postMessage communication in browsers that support it (FF3, Safari 4, IE8), while falling back to a document.location.hash communication method for all other browsers (IE6, IE7, Opera).

With the addition of the window.postMessage method, JavaScript finally has a fantastic means for cross-domain frame communication. Unfortunately, this method isn't supported in all browsers. One example where this plugin is useful is when a child Iframe needs to tell its parent that its contents have resized.

Visit the [project page](http://benalman.com/projects/jquery-postmessage-plugin/) for more information and usage examples!


## Documentation ##
[http://benalman.com/code/projects/jquery-postmessage/docs/](http://benalman.com/code/projects/jquery-postmessage/docs/)


## Examples ##
This working example, complete with fully commented code, illustrates one
way in which this plugin can be used.

[http://benalman.com/code/projects/jquery-postmessage/examples/iframe/](http://benalman.com/code/projects/jquery-postmessage/examples/iframe/)


## Support and Testing ##
Information about what version or versions of jQuery this plugin has been
tested with and what browsers it has been tested in.

### jQuery Versions ###
1.3.2

### Browsers Tested ###
Internet Explorer 6-8, Firefox 3, Safari 3-4, Chrome, Opera 9.

## Release History ##

0.5 - (9/11/2009) Improved cache-busting
0.4 - (8/25/2009) Initial release


## License ##
Copyright (c) 2009 "Cowboy" Ben Alman
Dual licensed under the MIT and GPL licenses.
[http://benalman.com/about/license/](http://benalman.com/about/license/)
