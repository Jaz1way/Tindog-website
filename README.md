## Bootstrap

### Introduction

​		One of the many **external** CSS layout systems, it contains pre-made CSS files, which we can simply include into our project in order to use their pre-built components and styling.

​		*(There are more CSS Frameworks such as Animate, Foundation, MUI, Tailwind...)*

​		Bootstrap has a **12 column layout system** built on top of Flexbox, this makes it very easy to create responsive websites and websites that simply just work and look great on mobile or desktop. *(Mobile First)* 

```html
<ul>
    <li>
        <button>Home</button>
    </li>
</ul>
```

* Let’s say we have a button on our website.
* But this button has nothing special.

```html
<ul class="nav nav-pills">
    <li>
        <button class="nav-link active rounded-5">Home</button>
    </li>
</ul>
```

```css
.nav{...}
.nav-pills{...}
.nav-link{...}
.active{...}
.rounded-5{...}
```

* If we included 5 classes from Bootstrap(booststrap.css), and included those pre-built CSS into our project.
* All we have to do is to add these styling and components to our HTML.
* *We don’t have to worry about writing all of the CSS code, all we need to know is which classes we need to add to our HTML.*

---

### Something to know...

**Pros of using CSS Frameworks**

1. Easy and Fast to use.
2. A ton of pre-built components.
3. Consistent styling across our website.

**Cons of using CSS Frameworks**

1. Class bloat: a lot of styling going into the HTML file.
2. Customization: Not full control in every pixel.

**When to use CSS Frameworks?**

1. Building a ***Mobile First*** responsive website that you want to put online very quickly. 
2. Access beautiful components designed by professional designers.

**When NOT to use CSS Frameworks?**

1. Simple website where you just need HTML and CSS.
2. Building a really complex custom design website.

**How to use Bootstrap?**

1. Go to [GetBootstrap.com](https://getbootstrap.com/) 
2. Include bootstrap file via CDN link
    1. Include the link we need into the <head> of our HTML
3. Then go to the **Docs** section find whatever pre-build CSS components you need, and paste it into <body> section
4. Modify the pre-build component based on your need

---

### Bootstrap Layout

​		Understanding the **12-columns Bootstrap layout system**.

The *12-columns Bootstrap layout system* is made of 3 components

1. A <div> that has a class of container
2. Another <div> of class row
3. Inside the row, is where the items be laid out.

```html
<div class="container">
    <div class="row">
        <div class="col">Hello</div>
    </div>
</div>
```

* When we have **multiple** columns laid out inside the rows, Bootstrap will **automatically** try to give every column inside the row **equal spacing** and space them across the **entire width** of the container.

```html
<div class="container">
    <div class="row">
        <div class="col-2">Hello</div>
        <div class="col-4">Hello</div>
        <div class="col-6">Hello</div>
    </div>
</div>
```

* We can also specify how many of these columns does the item would occupy.
* In this case, `col-2` means this item will take 2/12 of the columns in the row.
* In other words, we are sizing the container without going to write CSS code, we can simply do it in HTML.

---

#### Breakpoint

​		Bootstrap has 6 default breakpoints:

| Breakpoint        | Class Infix | Dimension | Device           |
| ----------------- | ----------- | --------- | ---------------- |
| Extra Small       | None        | <576px    | Longer than wide |
| Small             | sm          | >=576px   | Mobile           |
| Medium            | md          | >=768px   | iPad             |
| Large             | lg          | >=992px   | Laptop           |
| Extra Large       | xl          | >=1200px  | Desktop          |
| Extra Extra Large | xxl         | >=1400px  | TV...            |

```html
<div class="container">
    <div class="row">
        <div class="col-sm-2">Hello</div>
        <div class="col-md-4">Hello</div>
        <div class="col-lg-6">Hello</div>
    </div>
</div>
```

* Here is an example of using breakpoint.
* Given this, we don’t need *Media Queries* as much, because this already covers a lot of device dimensions.

```html
<div class="container">
    <div class="row">
        <div class="col-sm-12 col-md-8 col-lg-4">Hello</div>
    </div>
</div>
```

* We can have **multiple breakpoints** in a single <div>.
* On *large* size devices, this column will take 4/12 of the width.
* On *medium* size devices, this column will take 8/12 of the width.
* On *small* size devices, this column will take 12/12 of the width OR full width.

---

#### Mix & Match

```html
<div class="container">
    <div class="row">
        <div class="col-2">Hello</div>
        <div class="col-4">Hello</div>
        <div class="col">Hello</div>
    </div>
</div>
```

* In this case, we only assigned value to the first 2 columns, and the last column would automatically adjust in size in order to take up whatever proportion remains.

---

### Bootstrap Components

​		You can find all kinds of components from https://getbootstrap.com/docs/5.3/getting-started/introduction/

1. We need to include the CDN link for stylesheet
2. We need to include the script link for the scripting code that gives us all of the functionality.

```html
/*CDN link for Bootstrap*/
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous">
```

```html
/*Scripting code link for Bootstrap*/
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm" crossorigin="anonymous"></script>
```

* We would have to put the CDN link in <head> 
* put the scripting link just before the closing tag of <body>

---

#### Spacing

​		The classes are named using the format: {property}{sides}-{size} for xs and {property}{sides}-{breakpoint}-{size} for sm, md, lg, xl, xxl.

*Property:*

* m - for classes that set *margin*
* p - for classes that set *padding*

*Sides*

* t - margin-top or padding-top
* b - margin-bottom or padding-bottom 
* s - (start) for classes that set margin-left or padding-left in LTR, margin-right or padding-right in RTL
* e - (end) for classes that set margin-right or padding-right in LTR, margin-left or padding-left in RTL
* x - for classes that set both *-right and *-left
* y - for classes that set both *-top and *-bottom
* blank - margin and padding on all 4 sides of the element

*Size*

* 0 - eliminate the margin or padding
* 1 - set margin or padding to $spacer * 0.25
* 2 - set margin or padding to $spacer * 0.5 
* 3 - set margin or padding to $spacer * 1
* 4 - set margin or padding to $spacer * 1.5
* 5 - set margin or padding to $spacer * 3
* auto - for classes that set the margin to auto

```css
mt-5
```

* margin - top -size 5

```css
my-2
```

* margin - top and bottom - size 2

---

**Dark Mode**

​		Change the website to Dark Mode

```html
<html lang="en" data-bs-theme="dark"></html>
```

* Simply adding `data-bs-theme=“dark”` to the html tag
