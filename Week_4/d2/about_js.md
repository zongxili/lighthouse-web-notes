# Day 2 JavaScript

## JS in browser

Js in NODE is different with JS in browser (although they are all JavaScript)
eg: "process" is bulit-in variable in NODE but not browser JS


#### examples
JS came out to make the brwoser programable: enable interact with some actions like "click / move mouse eg"

document something here  --> a DOM object
eg. get the H1 tag bu queryselecter 
assign it to a const 
GEt the tille by inner text

---

.style can see to all the styles properties

eg: if we get a const with a tag; when we do the click function with Object, it will lead to another page


---

Overall, can chagne the website layout by changing its porperties

## jQuery
a JS library
event handing, animation, Ajax etc

some website have but some not: jsut type jQeury in browser.
  in the site, its a function
  its equal to a "$"
  dont have to loop througn
  
  

Download JS:
  compree version: less size 
  also can use online jaquery --> the site may be down
Its better look at the API than w3schools


`
this allow 
the string have multi
 lines with ``
`

"But this can be only one line"

a function: serialize --> get all the data together

Challenge:
- Find the Selector
- Delete dom.node in JS

Some note for the project:
I had this code in my Jquery file.
It did do its job, but it stopped there for a moment.
```js
  $("#arrow-down-button").click(function() {
    $(".new-tweet").animate({
      height: 'toggle'
    });
  });
```
Still no clue about this. Nothing do with the height / display.

Instead of implementing this, I used 
```js
$(".error-msg-section").toggle(400);
```
Inside the `toggle`, the value is for duration which can be "fast", "slow" and 400 is its default value.

In addition, an alternative way to make this effect is to write CSS codes, and do "appendClass" for it. But my concern is this may apply a lot work.

## NEED TO KNOW: 
1. !important
2. Opacity VS display
  1. Usage:
    - Opacity: 0 (disappear) / 1 (appear);
    - display: none / block;
  - Opacity wont move the elements from the screen, oppontsently, the display will. Once it is set to another value, it squuze tge bottom space.
3. 
