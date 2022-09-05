# Frontend Mentor - Chat app CSS illustration solution

This is a solution to the [Chat app CSS illustration challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/chat-app-css-illustration-O5auMkFqY). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- **Bonus**: See the chat interface animate on the initial load

### Screenshot

![](./my-solution/my%20solution%20desktop%20view.png)
![](./my-solution/my%20solution%20mobile%20view.png)

### Links

- Solution URL: [solution URL](https://your-solution-url.com)
- Live Site URL: [ live site URL](https://aemrobe.github.io/chat-app-css-illustration-challenge/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

in this challenge I learn new skill which is how to make a custom radio button. here is a way to do it.
first the usual way we follow to make the radio buttons is:

```html
<input type="radio" name="price" id="1-hour" value="$49" />
```

inorder to customize it first we should wrap the radio button inside the inline element this is because if the input element is put inside inline element when we click the container inline element it will select our radio button.

this is how we wrap our radio button inside a label(inline)element

```html
<label class="custom-radio-btn">
  <input type="radio" name="price" id="1-hour" value="$49" />
</label>
```

we will use this label element as the outer circle of the new custom radio btn.

next we will create a span element with a class of checkmark inside the label element. this span element is the small dot inside the circle of the new created radio button.

```html
<label class="custom-radio-btn">
  <input type="radio" name="price" id="1-hour" value="$49" />
  <span class="checkmark"> </span>
</label>
```

finally in our code we have the label element which will be formatted as our outer circle which contains two elements the our usual radio button and the span element which will be formatted as small dot so, we will format the elements as follows.

first we will format our label element as our outer circle since it is inline element when we click this outer circle it will click our usuall radio button.

```css
.custom-radio-btn {
  display: inline-block;
  height: 15px;
  width: 15px;
  border: 1px solid black;
  border-radius: 50%;
}
```

this will create outer circle with a border-width of 1px. the reason why we give it a property of display: inline-block; is inorder to make the width and height property to work because height and width doesn't work on inline elements and this element will contain our two elements the usual radio button and span element.
we will format this span element as small dot inside label element.

```css
.custom-radio-btn {
  display: inline-block;
  height: 15px;
  width: 15px;
  border: 1px solid black;
  border-radius: 50%;
}

.checkmark {
  width: calc(100% - 4px);
  height: calc(100% - 4px);
  background: black;
}
```

this will create a small dot inside of the label element with a width and height of 4px less than the width and height of it's parent element. the reason why we use 4(even number) inside our calc function is when we try to center this dot next inside it's parent it will put equal space in either side of this dot element. but this doesn't create our dot because we don't put a property of display: inline-block since this is an inline element. so we will add this property of display: inline-block but we want this dot only visible when our radio button is checked so we will write the code as follows.

```css
.custom-radio-btn {
  display: inline-block;
  height: 15px;
  width: 15px;
  border: 1px solid black;
  border-radius: 50%;
}

.checkmark {
  width: calc(100% - 4px);
  height: calc(100% - 4px);
  background: black;
  display: none;
}

.custom-radio-btn input:checked .checkmark {
  display: inline-block;
}
```

finally we have made it when we select a label element the usual radio-btn will be selected then when input(usual-radio-btn) is checked our .checkmark will be visible. so we don't need our usuall radio button anymore we have our label element which is formatted as our outer circle and our .checkmark(inner dot) which is selected as we select our label element.so, will we hide our usual radio-btn.

```css
.custom-radio-btn {
  display: inline-block;
  height: 15px;
  width: 15px;
  border: 1px solid black;
  border-radius: 50%;
}

.checkmark {
  width: calc(100% - 4px);
  height: calc(100% - 4px);
  background: black;
  display: none;
}

.custom-radio-btn input:checked .checkmark {
  display: inline-block;
}

.custom-radio-btn input {
  display: none;
}
```

finally the newly created circle which is our label element and the inner dot which is the span element are only visible but the innder dot(span element) is not positioned to the center of the circle so we will center it as follows:

```css
.custom-radio-btn {
  display: inline-block;
  height: 15px;
  width: 15px;
  border: 1px solid black;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.checkmark {
  width: calc(100% - 4px);
  height: calc(100% - 4px);
  background: black;
  display: none;
}

.custom-radio-btn input:checked .checkmark {
  display: inline-block;
}

.custom-radio-btn input {
  display: none;
}
```

### Continued development

I want to master my skill of using flexbox and grid for responsive webdesign and I want to learn javascript.

### Useful resources

- [Styling radio buttons](https://youtu.be/MZq5zFSpUlo) - This helped me to understand how can I style radio buttons.

## Author

- Frontend Mentor - [@aemrobe](https://www.frontendmentor.io/profile/aemrobe)
- Twitter - [@Aemro112](https://www.twitter.com/Aemro112)

## Acknowledgments

I want to say thanks to my team members who always helped me in fixing the bugs which I encounter whey I make this challenges.
