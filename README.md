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
    var val1 = $(this);
    var val2 = $(this).val();
    var regexVal = /[^[a-zA-Z0-9]]*/gi;
    var newValue = val2.replace(regexVal, '');
    val1.val(newValue);
});
```

