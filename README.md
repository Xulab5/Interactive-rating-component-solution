# Frontend Mentor - Interactive rating component solution

This is a solution to the [Interactive rating component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Select and submit a number rating
- See the "Thank you" card state after submitting a rating

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it. 

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- Javascirpt

### What I learned

- Form Elements
- Form Validations

- Survey code
```html
  <!-- Rating state start -->
<div class="survey">
  <div class="survey__star">
    <img src="/images/icon-star.svg" alt="Star icon">
  </div>
  <div class="survey__description">
    <h1 class="survey__title">How did we do?</h1>
    <p>Please let us know how we did with your support request. All feedback is appreciated 
      to help us improve our offering!</p>
  </div>
  <form action="/thank-you.html" class="survey__form" onsubmit=" return validate()" method="Get">
    <div class="form__rate">
      <div class="rating">
        <input type="radio" id="rate__1" value="1" name="rating">
        <label for="rate__1">1</label>
      </div>       
      <div class="rating">
        <input type="radio" id="rate__2" value="2" name="rating">
        <label for="rate__2">2</label>
      </div>
      <div class="rating">
        <input type="radio" id="rate__3" value="3" name="rating">
        <label for="rate__3">3</label>
      </div>
      <div class="rating">
        <input type="radio" id="rate__4" value="4" name="rating">
        <label for="rate__4">4</label>
      </div>
      <div class="rating">
        <input type="radio" id="rate__5" value="5" name="rating">
        <label for="rate__5">5</label>
      </div>
    </div>
    <div class="form__button">
      <!-- <button class="btn" type="submit">Submit</button> -->
      <input type="submit" class="btn"value="Submit">
    </div>
  </form>
</div>
  <!-- Rating state end -->
  
  <div class="attribution">
    Coded by <a href="https://github.com/Xulab5">Steven Sub</a>.
  </div>
```

- Survey Thank you page
```html
   <!-- Thank you state start -->
<div class="survey survey-thank-you">
  <div class="survey-thank-you__headerimg">
    <img src="images/illustration-thank-you.svg" alt="Thank you image">
  </div>
  <div class="survey__description">
    <div class="survey__rating">You selected  <span class="rate"></span>  out of 5</div>
    <h1 class="survey__title">Thank You!</h1>
    <p>  We appreciate you taking the time to give a rating. If you ever need more support, 
        don't hesitate to get in touch!</p>
  </div>
</div>
  <!-- Thank you state end -->
```

```js
//Thank you page code
 const params = new Proxy(new URLSearchParams(window.location.search), {
            get: (searchParams, prop) => searchParams.get(prop),
        });    
    let rating = params.rating;
    window.onload = (event) => {
        console.log(rating)
        document.querySelector('.rate').innerHTML=rating;
    };    
}
```
```js
//Survey code - form validation
 function validate(){
      let rated = false;
      let ratings = document.getElementsByName('rating');
      ratings.forEach(rating => {
        if(rating.checked){          
          rated = true;
          break;
        }        
      });
      if(!rated){
        alert("Please select a rate before submitting.")
        return false;
      }
    }
```

### Useful resources

- [Radio Button](https://stackoverflow.com/questions/1423777/how-can-i-check-whether-a-radio-button-is-selected-with-javascript) - This assisted me in solving how to determine if a radio button has been selected
- [URL Query Selector](https://stackoverflow.com/questions/901115/how-can-i-get-query-string-values-in-javascript) - This question form Stackoverflow assisted me in getting the ratings value from the url after the form has been submitted. I'd recommend it to anyone still learning this concept.



## Author

- Website - [Steven Sub](https://stevensub.netlify.app/)
- Frontend Mentor - [@Xulab5](https://www.frontendmentor.io/profile/Xulab5)
- Facebook - [@Steven.Sub](https://www.facebook.com/Steven.Sub)
- Instagram - [@xulab05](https://www.instagram.com/xulab05/)


## Acknowledgments

I'd like to give thanks to Frontend Mentor for this great short and amazing project. This project was done solely by me without any assist. However, without some of the resource I have used online I would not have done it. 
