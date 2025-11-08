
# QE Custom Tags:
- In `Admin Panel` and `XWebsite` front-end e have some `custom tags` that are actually custom HTML tags and they are fully defined on `global.css` and we use them for building our fully customized apps. here is the custom tags list:

## Button custom tags:
- `b-100`: it is a button with `height: 30px`, it's `display: flex` and `min-width: 100px`
- we also have `b-30`, `b-50`, `b-150`,`b-200`, `b-300`, `b-400` and they are different in `min-width`. their `min-width` respectively are: `30px`, `50px`, `150px`, `200px`, `300px`, `400px`.
- the `b-[num]` that we mentioned above are useful for responsive design.
For example:
	```html
	<div style="display:flex; flex-wrap:wrap">
	  <b-100>button1</b-100>
	  <b-100>button1</b-100>
	  <b-100>button1</b-100>
	</div>
	```
	in the above code, if page's width is greater than 300px the 3 buttons will align horizontally but if page's width gets smaller they will be placed on new lines below together.
## Font size custom tags:
all font size custom tags that we show here has below CSS properties:
``` CSS
	text-align: justify;
	word-spacing: -0.5px;
	margin-block-start: 0px;
	margin: 0;
	padding: 0;
```
the custom font size tags format is like `f-[num]`, and `[num]` indicates the font size and starts from 5 to 40. for example we have `<f-5>` to `<f-40>` tags here is some examples:
```html
<f-5>Hello</f-5>
<b-200><f-15>Hi</f-15></b-200>
<span><f-18>Wow im a font with 18px font-size</f-18></span>
```
## Horizontal spacing custom tags:
Horizontal spacing custom tags are for making horizontal space between two elements. for example assume that we have two images and we need some horizontal space between them.
The Horizontal spacing custom tags format is `sp-[num]` and `[num]` can be `1` for `10px`  , `2` for `5px` ,  `3` for `3px` or `4` for `1px`.
Here is an example: 
```html
<div style="display:flex">
<img src="/ex.jpg" />
<sp-1/> <!-- 20px Horizontal space -->
<img src="/ex.jpg" />
<sp-2/> <!-- 10px Horizontal space -->
<img src="/ex.jpg" />
<sp-3/> <!-- 6px Horizontal space -->
<img src="/ex.jpg" />
<sp-4/> <!-- 2px Horizontal space -->
<img src="/ex.jpg" />
</div>
```


## Vertical spacing custom tags:
Vertically spacing custom tags are for making vertical space between two elements. for example assume that we have two images and we need some vertical space between them.
The vertical spacing custom tags format is `br-[num]` and `[num]` can be `1` for `10px`  , `2` for `5px` ,  `3` for `3px` or `4` for `1px`.
Here is an example: 

```html
<div>
<img src="/ex.jpg" />
<br-1/> <!-- 0.5rem vertical space -->
<img src="/ex.jpg" />
<br-2/> <!-- 0.25rem vertical space -->
<img src="/ex.jpg" />
<br-3/> <!-- 0.15rem vertical space -->
<img src="/ex.jpg" />
<br-4/> <!-- 0.05rem vertical space -->
<img src="/ex.jpg" />
</div>
```

## Flex  custom tags:
We have 3 group of useful custom tags that has `display:flex` CSS property. The format of these groups are `f-[n][m]` , `w-[n][m]` , `c-[n][m]` while `[n]` , `[m]` is parametric and depends on other CSS properties. 
- The first group `f-[n][m]` has `flex-direction: row` .
- The second group `w-[n][m]` has `flex-direction: row` and `flex-wrap: wrap`.
- The third group `c-[n][m]` has `flex-direction: column`.
- We use first group when we need to place some children horizontally.
- We use second group when we need to place some children horizontally but we also need it to be responsive and children go to next line while parent's width is lower that sum of children's sum with.
- We use third group when we need to lace some children vertically.

Now lets explain `[n]` and `[m]` parameters:
- `[n]` actually determine the `align-item` and it can be 4 values: 
-- `x` for `align-item: stretch`
-- `s` for `align-item: start`
-- `e` for `align-item: end`
-- `c` for `align-item: center` 

Now lets explain `[m]` parameter:
- `[m]` actually determine the `justify-content` and it can be 4 values: 
-- `s` for `justify-content: start`
-- `e` for `justify-content: end`
-- `c` for `justify-content: center` 
-- `sa` for `justify-content: space-around` 
-- `sb` for `justify-content: space-between` 
-- `se` for `justify-content: space-evenly` 

It's important to know that is we want use `DaisyUI` on custom tags we use `class` instead of `className`.

Now lets do some examples:

**Example 1**: Assume that we need a 100px x 100px rectangle with a `Hi` in the center of it. 
**Answer 1**: There is two way to make it by flex custom tags, one of them is to use `f-cc` or `w-cc` and another way is to use `c-cc`.
First way:
``` html
<f-cc style="width:100px; height:100px">Hi</f-cc>
``` 
or
``` html
<w-cc style="width:100px; height:100px">Hi</w-cc>
``` 
in the above examples `f-cc` indicates `display:flex; align-item:center; justify-content:center` and it is all we need to place `Hi` in the center of it.
Second way:
``` html
<c-cc style="width:100px; height:100px">Hi</c-cc>
``` 
in the above examples `c-cc` indicates `display:flex; flex-direction: column; align-item:center; justify-content:center` and it is all we need to place `Hi` in the center of it.

---

**Example 2**: Assume that we need a 100px x 100px rectangle with a `Hi` and `Bye` with 15px font-size. and both inside this rectangle and be horizontally beside each other and both be in the center of the parent. 

**Answer2**:
``` html
<f-cc style="width:100px; height:100px">
	<f-15>Hi</f-15>
	<f-15>Bye</f-15>
</f-cc>
```

---
**Example 3**: Assume that we need a 100px x 100px rectangle with 3 Hi with the font size as: (the first one 15px, the second one 18px and the last one 20px) and we want all he horizontally besides together and maximum space between them.

**Answer 3**: For this question we need 3 elements to be be vertically centered and horizontally space-between so we need `display:flex; flex-diretion: row` so we have to use `f-[n][m]` and `align-items: center` to be vertically center aligned so `[n]-> c` and horizontally space between them so `[m] -> sb` finally we should use `<f-csb>` to solve this question below is the code:

``` html
<f-csb style="width:100px; height:100px">
	<f-15>Hi</f-15>
	<f-18>Hi</f-18>
	<f-20>Hi</f-20>
</f-csb>
```
---
**Example 4**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-item:end; justify-content:space-evenly"></div>
```

**Answer 4**: Here is the QE custom tags equivalent:
```html
<f-ese></f-ese>
```
---
**Example 5**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-item:start; justify-content:space-evenly"></div>
```

**Answer 5**: Here is the QE custom tags equivalent:
```html
<f-sse></f-sse>
```


**Example 6**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-item:center; justify-content:space-around">
	<span style="font-size:19px">Hi</span>
	<span style="font-size:25px">Hi</span>
</div>
```

**Answer 6**: Here is the QE custom tags equivalent:
```html
<f-csa>
	<f-19>Hi</f-19>
	<f-25>Hi</f-25>
</f-csa>
```
---

**Example 7**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-item:stretch; justify-content:center">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</div>
```

**Answer 7**: Here is the QE custom tags equivalent:
```html
<f-xc>
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</f-xc>
```
---

**Example 8**: Convert below code to the QE custom tags version:
``` html
<div>
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</div>
```

**Answer 8**: Here is the QE custom tags equivalent:
```html
<c-ss>
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</c-ss>
```
---

**Example 9**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-items:start; justify-content:center; flex-direction:column">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</div>
```

**Answer 9**: Here is the QE custom tags equivalent:
```html
<c-sc>
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</c-sc>
```
---

**Example 10**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-items:start; justify-content:space-between; flex-direction:column">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</div>
```

**Answer 10**: Here is the QE custom tags equivalent:
```html
<c-ssb>
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</c-ssb>
```

---

**Example 11**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-items:start; justify-content:space-between; flex-direction:row; flex-wrap:wrap; gap:5px">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</div>
```

**Answer 11**: Here is the QE custom tags equivalent:
```html
<w-ssb style="gap:5px">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</w-ssb>
```
---

**Example 12**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-items:stretch; justify-content:space-evenly; flex-wrap:wrap; row-gap:5px; column-gap:10px; padding:10px">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</div>
```

**Answer 12**: Here is the QE custom tags equivalent:
```html
<w-xse style="row-gap:5px; column-gap:10px; padding:10px">
	<img src="/ex.jpg" />
	<img src="/ex.jpg" />
</w-xse>
```

---

**Example 13**: Convert below code to the QE custom tags version:
``` html
<div style="display:flex; align-items:stretch; justify-content:space-evenly; flex-direction:column; row-gap:5px; column-gap:10px; padding:10px">
  <span style="font-size:20px">Hi &nbsp;&nbsp; Bye </span>
	<div style="height:30px; width:30px; background-color:pink"></div>
	<span style="font-size:25px">Hi</span>
	<div style="minHeight: 0.25rem"></div>
	<img src="/ex.jpg" />
	<div style="minHeight: 0.5rem"></div>
	<img src="/ex.jpg" />
</div>
```

**Answer 13**: Here is the QE custom tags equivalent:
```html
<c-xse style="row-gap:5px; column-gap:10px;">
  <f-20>Hi<sp-2/>Bye</f-20>
	<c-ss style="height:30px; width:30px; background-color:pink"></c-ss>
	<f-25>Hi</f-25>
	<br-2/>
	<img src="/ex.jpg" />
	<br-1/>
	<img src="/ex.jpg" />
</c-xse>
```