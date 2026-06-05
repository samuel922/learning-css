# CSS Fundamentals
## Margins & Padding
The spacing between heading elements and paragraph elements are controlled by margin-top and margin-bottom properties.
<br>
By default, they all have a margin-top and buttom that equals their font-size. 

### Margin collapsing
Margin collapsing is when two elements next to each other collapse their margin. For exmaple when the first element has a margin-bottom of 20px and the second element has a margin-top of let's say 40px, the bigger margin in this case wins. <br> Therefore the margin between the two elements will be 40px.<br> Also, there are situations where the margin of the child element collapse with the margin of it's parent element, expecially for the first child of the parent. <br>Therefore, in this case when you increase the margin of the child, the effect is seen increasing the margin of the parent.<br> This is resolved by giving padding to the parent element which creates a buffer between parent and child margins and adding a margin to the child does not impact the parent margin.\
We also need to remove the margin top of elements within a parent like a card to ensure consistency. Also get the last element and remove the margin-bottom manually. This ensures that everything is consistent within the page.

### Inline vs Block level elements
#### Inline elements
Inline elements flow with the content around it and does not push other elements to the next line. Inline elements also have some unique behaviors we need to note:
- You can only nest other inline elements within them.
- They will only respect the margin, padding and border placed on the left or the right side and not top and bottom.

Example of inline elements include -> strong, a, em, img, span etc.
#### Block elements
These are elements that stack on top of each other by default. They push the elements around them to the next line, they take the full viewport horizontal width.
These elements include - header, main, footer, nav, ul, ol, li, div, aside, p, h1 ... h5 etc,
#### Inline-block elements
Sometimes we need elements to stay inline but still be able to apply padding and margin on all sides to it. This is where inline-block elements comes in. They allow inline elements to still be adjacent to each other but still be able to apply a padding and margin in both sides.

---
### Styling Buttons
- Always add class on the link itself and not on the element that wraps over the link.
- Always use padding to size the button and not width and height.
- Always use a rule of applying a padding ratio of 1:2.5 to the button. Making the padding on the left and right 2x or 2.5x bigger that the top and bottom margin to make it look good.
- Using links(a) tag for buttons have an advantage of being able to navigate to the link content by clicking anywhere on the button. On the other hand, in a button, you have to click at the button     text
---
### Specificity
Specificity defines how specfic a selector can be. Element selectors have the lowest specificity, followed by class selector then id selectors have the highest. Specificty overrides position on the file. The **general rule of thumb** is to always use element selectors to select general rules like html, body, headings, paragraphs and everything else given a class.
<br>
<br>
As much as using compound selectors may improve specificity of a selector, we should minimize using compound selector to prevent specificity battles that may arise in future as the css file size becomes bigger. Therefore, we should apply one class to an element and select it using the class to minimize getting into problems caused by compound selector. Example compound selector -> div button

---
### Thinking responsively
There are different type of units that we can use and css comes with a number of them
- Relative units
- Absolute units
- Percentages

Absolute units are the easiest and they include px(pixel), cm, mm, in, etc,.
Percentages are mostly used on widths relative to their parent.
Relative units are further broken down in to:
- Relative to the **fontsize** -> em and rem
- Relative to **viewport** -> browser window -> vw, vh, vmin, vmax

#### Percentage units
The most crirtical quation we ask for percentage units when applied to element is. It is a percentage of what? Percentage units are applied relative to their parents container width. Therefore, we need to be very careful when applying these. Percentage units on width works well with max and min units by setting an absolute max/min width to prevent the content from overstretching or going bellow a certain width.

#### Relative units
As discussed earlier, relative units are called relative because they are relative to either the font size or the viewport of the browser
##### em
em units in particular are relative to their parent font-size. These has an effect of cascading the font-size change to all other elements with em units applied when the font size of the parent is changed. Since font sizes are inherited, em is always relative to the parent's font size when it's set or relative to the root element's font size.
<br>
<br>
em's are convinient for some things but when used on font sizes they have a cascading effect that may result to be problematic.

##### rem
rem are called root em. This is becuase unlike em,  which are relative to thier parents, rem are relative to the root element. Which is the html element itself. They don't have the cascading effect as we saw with em units but the size only increase if the font size of the root elements is also changed.
