## General design rule
 
Below are some basic rules for creating the HTML newsletters that you send using GetResponse. These rules will help you design responsive messages that look great in every email client.

1. Build your template using tables — not &lt;div&gt;, basic HTML, and the abbreviations that are common in website design.
2. Use inline CSS2 to control style, since most email clients remove the &lt;head&gt; section from HTML code. Avoid abbreviations.
3. Use tag attributes, to make sure your HTML code is interpreted the same way in different email clients.
4. Don’t use colspan or rowspan attributes.
5. Use padding rather than margins to control the position of design elements, to avoid the rendering problems often caused by older email programs.
6. Use absolute paths for images, not relative-path URLs such as "/images/image.gif".
7. Give each image a unique name (a name that relates to the message) to prevent problems when copying a template from one campaign to another.
8. Define each graphic element as a block-level element, to avoid unwanted spaces under images.
9. Don’t use &lt;thead&gt; and &lt;tfoot&gt; tags in your HTML templates. These are reserved for the GetResponse WYSIWYG editor.
9. Define text alignment (left/center/right) using the align attribute, not using style="text-align: center | right | left".
9. Always check your email design using GetResponse Inbox Preview, to make sure it will display properly in all types of email programs, browsers, and devices.

Full guide is available here: http://www.getresponse.com/guides/how-to-code-html-newsletters
If you just want to see an example, look to newsletter folder in this repo.
