==========================================
How To Use JSBin For Testing AJAX Requests
==========================================

Set up 2 bins:

Bin 1: JSON
-----------

Create a new bin. Paste the JSON response that you'd like to test against in JS. 

Delete the HTML. You should see Output change to be identical to the JSON in JS.

The URL for the simulated JSON response is now the URL of the bin, e.g. http://jsbin.com/ipamut/.

Bin 2: Your Code
----------------

Create a 2nd bin. Code as usual.

In your AJAX request in JS, use the URL from earlier. For example::

    d3.json("http://jsbin.com/ipamut/", function(json) {
      ...
    }

That's it.
