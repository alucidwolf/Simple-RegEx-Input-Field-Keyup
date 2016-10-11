# Simple-RegEx-Input-Field-Keyup
Simple starting function to place in doc.ready so on keyup the input field removes any characters other than A-Z. a-z or 0-9

##HTML
```
<input type="text" id="signupCode" placeholder="Sign Up Code">
```

##Javascript
*Put this in your document.ready function and change to the ID to that of your input field*
```
$("#signupCode").on("keyup", function () {
    var start = this.selectionStart;
    var end = this.selectionEnd;
    var val1 = $(this);
    var val2 = $(this).val();
    var regexVal = /[^[a-zA-Z0-9]]*/gi;
    var newValue = val2.replace(regexVal, '');                        
    val1.val(newValue);
    this.setSelectionRange(start, end);
});
```

###This will also keep the cursor in the same spot even after checking for special characters

##If you are using bootstrap and want to trigger a tooltip for the user to indicate what the field requires, you can do it like this
```
$("#signupCode").on("keyup", function () {
...
...
    this.setSelectionRange(start, end);
}).tooltip({
    'trigger'   : 'focus',
    'title'     : 'No Special Characters Allowed'
});
```
