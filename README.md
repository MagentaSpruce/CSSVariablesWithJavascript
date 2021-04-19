# CSSVariablesWithJavascript
30 day JS Projects challenge

This project shows how to manipulate CSS variables using JavaScript.

This project helped me to learn and understand better:
1) The spacing property
2) using this.
3) dataset
4) DOM Manipulation

There are no known bus assiciated with this project. No improvements are slated. It is mostly conceptual in purpose, although, it could be retooled and repurposed with relative ease in various use cases.


A simple walkthrough and explanation of the code is below:

First select the inputs which you want to be able to change with JavaScript. Then loop over the node-list with forEach() 
```JavaScript
const inputs = document.querySelectorAll('.controls input');
```

Next create the function handeUpdate to show the changes to the inputs and then listen for a change event on the inputs. To trigger a change in the input slider a mousemovelistener is also needed but this only triggers a movement when the mouse is let go. To make the values shift along with the slider 
```JavaScript
function handleUpdate(){
  console.log(this.value);
}

inputs.forEach(input => input.addEventListener('change', handleUpdate));
inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));
```

Need to know the suffix of the variables being worked with. Base doesnt have a suffix as it is hexcoded but spacing and blur do. To do this a data attribute is used, data-sizing.
```JavaScript
function handleUpdate(){
  const suffix = this.dataset.sizing || '';
}
```

Now need to update the variables by selecting the root and setting a property of base, spacing, or blur which are the variables we set in the CSS and setting their property dynamically.
```JavaScript
function handleUpdate(){
  const suffix = this.dataset.sizing || '';
  console.log(suffix);
  document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix)
}
```

***End walkthrough
