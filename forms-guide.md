### GetResponse WebForm template

Every form template have 5 types which describe amount of columns in the form.
Every form template should be create in all those variants.
Example structure of a template is in forms/example-form-structure
 
Sizes for each of the variants is shown below:

1-column

```css
form {
    width:220px;
    height:300px;
}
```

2-column

```css
form {
    width:460px;
    height:250px;
}
```

3-column

```css
form {
    width:700px;
    height:200px;
}
```

4-column

```css
form {
    width:940px;
    height:150px;
}
```

5-column

```css
form {
    width:440px;
    height:600px;
}
```

Thank You Page should have the same size as the column in which is put.


The main form html file should be called index.html
Index html contains simple html code that is divided in static section and custom fields

Custom field list:

1. email
1. first_name
1. last_name
1. birthdate
1. country
1. state
1. city
1. postal_code
1. street
1. age
1. gender
1. name
1. mobile_phone
1. home_phone
1. work_phone
1. fax
1. company
1. ip
1. comment
1. url


```html
<form data-editable="form">
    <div>
        <div data-editable="static-text" style="width:320px;left:40px;top:90px;">
            <div style="font-family:Helvetica, 'Helvetica Neue', Arial, sans-serif;font-size:24px;font-weight:bold;color:#fff;">Type your headline here...</div>
        </div>
        <div data-editable="static-image" style="width:125px;height:125px;left:290px;top:180px;">
            <img src="1/thp/img/well_done.png" width="125" height="125" alt="">
        </div>
       
        <div data-editable="static-line" style="left: 189px; top: 31px; height: 100px;" class="vertical">
            <div style="border-top-color: rgb(200, 213, 50); border-left-color: rgb(200, 213, 50); border-top-width: 4px; border-left-width: 4px;"></div>
        </div>
 
        <div data-editable="static-line" style="width: 100px; left: 189px; top: 31px;">
            <div style="border-top-color: rgb(200, 213, 50); border-left-color: rgb(200, 213, 50); border-top-width: 4px; border-left-width: 4px;"></div>
        </div>
 
        <!-- BOX simple -->
        <div data-editable="static-box" style="width:100px; height:100px; left: 153px; top: 125px; border:2px solid #29951B; border-radius:14px; background-color:#712E2E;"></div>
 
        <!-- BOX with IMG -->
        <div data-editable="static-box" style="background-color:#fff; background-image:(1/img/3.png); background-repeat:no-repeat; background-position:50% 50%; left:14px; top:178px; width:31px; height:36px; box-shadow:0 2px 0 0 rgba(0,0,0,0.2);"></div>
 
        <div data-editable="custom" style="width:320px;">[[email]]</div>
        <div data-editable="custom" class="submit" style="left:10px; width:120px;">submit</div>
    </div>
</form>
```
    
* [data-editable=“form”] - main form wrapper
* [data-editable=“custom”] - custom field 
 * [data-editable=“static-text”] - static text element
 * [data-editable=“static-image”] - static image element
*  [data-editable=“static-line”] - static line element
* [data-editable=“static-box”] - static box element
* [data-editable=“static-counter”] - badge counter
* [data-editable=“static-trustseal”] - badge trust seal
* [data-editable=“static-privacybadger”] - badge privacy policy


[data-editable]="custom" Can have more complex form. Here is example where we change more properties at once:

```html
<div data-editable="custom" style="width:160px;top:100px;">
[[
    getresponse_email|
        label: email address:, 
        placeholder: you@domain.com, 
        labelPosition: top|left|right|inside, 
        info: some informational text, 
        error: some error message, 
        minLength: 2, 
        maxLength: 10, 
        required: true,
        rows: 2 //textarea rows
]]
</div>
```

#### Thank you page html preview:

thp/index.html

```html
<div data-editable="container.thp">
    <div>
        <div data-editable="static-image" style="width:60px;height:60px;left:80px;top:90px;">
            <img src="1/thp/img/well_done.png" width="60" height="60" alt="">
        </div>
        <div data-editable="static-text" style="width:120px;left:50px;top:185px;">
            <div style="font-family:Helvetica, Arial;font-size:25px;font-weight:bold;color:#46b234;">Well done</div>
        </div>
        <div data-editable="custom" class="download" style="left:30px; width:130px;">download</div>
    </div>
</div>
```
