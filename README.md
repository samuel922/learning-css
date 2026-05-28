# CSS Fundamentals
## Margins & Padding
The spacing between heading elements and paragraph elements are controlled by margin-top and margin-bottom properties.
By default, they all have a margin-top and buttom that equals their font-size. 

### Margin collapsing
Margin collapsing is when two elements next to each other collapse their margin. For exmaple when the first element has a margin-bottom of 20px and the second element has a margin-top of let's say 40px, the bigger margin in this case wins. Therefore the margin between the two elements will be 40px. Also, there are situations where the margin of the child element collapse with the margin of it's parent element, expecially for the first child of the parent. Therefore, in this case when you increase the margin of the child, the effect is seen increasing the margin of the parent. This is resolved by giving padding to the parent element which creates a buffer between parent and child margins and adding a margin to the child does not impact the parent margin.
