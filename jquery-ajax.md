# jQuery
CDN

    <script src="https://code.jquery.com/jquery-2.2.4.min.js" integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44=" crossorigin="anonymous"></script>

Don't forget to use a ready event listener if you are including JS at the top of the HTML file:

    $(document).ready(function() {

    });
# jQuery Selectors
Use with HTML/ CSS selectors:
- `$(‘#id’)`
- `$(‘.class’)`
- `$(‘element’)`
- `$(‘selector1, selector2’)`
- `#(‘*’)`
# jQuery Event Listeners
Vanilla JS:

    var ele = document.getElementById(‘myElement’)
    ele.addEventListener(‘click’, function(e) {
        //insert code here
     });
jQuery:

	$(selector).click(function() {
		//insert code here
	});
		
# jQuery Mouse Events
Example:

    $(selector).click(handler)
- `.click`
- `.dblclick`
- `.hover`	or	`.mouseenter` + `.mouseleave`

#  jQuery Keyboard Events
Example:

    $(selector).keydown(handler)
- `.keydown` works for any key
- `.keypress` does not include modifier keys (shift, ctrl, esc)
- `.keyup` triggers when key is released
- `.on`
- `.off`

Don't forget what Justin said:
https://www.pdiniz.com/why-you-should-always-use-jquerys-onclick-instead-of-click/

    .on('click', function()){
    
    });

#  jQuery Attribute Methods
- `.html()`
- `.css()`
- `.addClass()`
- `.removeClass()`
- `.toggleClass()`

Examples:

    $(selector).html('insert text here')
    $(selector).css('color', 'red')
    $(selector).addClass('centered')

# jQuery Traversing Methods
- `.each()`
- `.first()`
- `.last()`
- `.parent()`
- `.child()`
- `.next()`

.each Example:

HTML

    <ul>
        <li>Rio Grande</li>
        <li>Comal</li>
        <li>Frio</li>
        <li>Guadalupe</li>
        <li>San Marcos</li>
    </ul>
    
JS
    
    $('li').each(function(index) {
        $(this).css('color', 'red')
    });
# jQuery Effects
- `.hide()`
- `.show()`
- `.toggle()`

# jQuery Animated Effects
- Fading
    - `.fadeIn()`
    - `.fadeOut()`
    - `.fadeToggle()`
- Sliding
    - `.slideUp()`
    - `.slideDown()`
    - `.slideToggle()`
    
You can put delays (in ms) to increase animation duration:

    $(selector).slideToggle(3000);

#  JavaScript Object Notation (JSON)
`{ }`	empty object
`[ ]`	empty array

Properties must be in double-quoted strings:

    {
		“prop1”: “value1”,
		“prop2”: “value2
	}

Values can be:
- A quoted string:	`“string-here”`
- A number:		    `3.14`
- An object:        `{}`
- An array:		    `[]`
- A boolean:        `true or false`
- Null:			    `null`

# Ajax Requests
Jquery simplifies ajax requests. Here is a basic request:

    $.ajax("/some-url")
Here is an ajax request with options:

    $.ajax("/some-url"), {
        type: "POST",
        data: {
            name: "John",
            location: "Boston"
        }
    }

Options available:
- `type:` GET", "POST", "PUT", or "DELETE".  Defaults to "GET".
- `data:` a JS object (see JSON for formatting external .json files)
- `dataType:` type of data expected
- `url:` can be specified here instead of passing string to $.ajax
- `username / password:` when needed for security purposes
- `headers:` <something complex that needs to be researched>

# Asynchronous AJAX Requests and You
Ajax requests are asynchronous, use methods with callback functions (actually, this is adding an event listener to not run the callback function until the request is processed) like:

    $.ajax("/some-url").done(function(data, status, jqXhr) {

    });

where
- `data` = data from server
- `status` = string indicating status
- `jqXhr` = obj representing ajax request

Code specified in .done executes once the request is processed.

More ajax methods besides .done:
- `.fail` executes if server returns a 404 error
    - `jqXhr`
    - `status`
    - `error`
- `.always`


Can be used separately or chained and used a little like a switch statement:

    $.ajax("/some-url").done(function(data, status, jqXhr) {
        // do this code when a request is successful
    )}.fail(function(jqXhr, status, error) {
        // do this code if the request fails
    )}.always(function () {
        // this code will always run with the ajax request
    });

Can also be used with named functions:
    
    function onSuccess(data, status, jqXhr) {
        // display the requested data to the user
    }

    function onFail(jqXhr, status, error) {
        // tell the user something went wrong, and to try again later
    }

    function stopLoadingAnimation() {
        // the request is no longer pending, hide the loading spinner
    }

    $.ajax("/some-url")
        .done(onSuccess)
        .fail(onFail)
        .always(stopLoadingAnimation);

# REVIEW QUESTIONS
- What is jQuery? Why is it useful?
- What determines if a jQuery method can be chained after another?
- How can an event listener be added to multiple elements using jQuery
where the listener acts upon the specific element the event was trigged on?
- What is the difference between .click(callback) and .on('click', callback)?
- What is a getter and a setter? What are some methods that can be used either way? What is different between a getter and setter version of these methods?
- What is the best way in a single statement to change several style properties for a specific element using jQuery? Why is this the best way?
