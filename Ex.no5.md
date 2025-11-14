# Ex05 Image Carousel
## Date:

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
intex.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Image Carousel</title>
  <link rel="stylesheet" href="style.css">

</head>
<body >

  <div class="carousel">
    <div class="title-overlay">Image Carousel</div>
    <input type="radio" name="slide" id="s1" checked>
    <input type="radio" name="slide" id="s2">
    <input type="radio" name="slide" id="s3">

    <div class="slides">
      <div class="slide"><img src="8.jpeg" alt="Slide 1"></div>
      <div class="slide"><img src="2.jpeg" alt="Slide 2"></div>
      <div class="slide"><img src="3.jpeg" alt="Slide 3"></div>
    </div>

    <div class="nav">
      <label for="s1"></label>
      <label for="s2"></label>
      <label for="s3"></label>
    </div>
  </div>

</body>
</html>

```

style.css
```
    * {
      box-sizing: border-box;
    }

    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background: #bcbaaa;
    }

    .carousel {
      width: 500px;
      overflow: hidden;
      position: relative;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }

    .slides {
      display: flex;
      width: 300%;
      transition: transform 0.5s ease;
    }

    .slide {
      width: 100%;
      flex-shrink: 0;
    }

    .slide img {
      width: 50%;
      display: block;
    }

    input[name="slide"] {
      display: none;
    }

    .nav {
      text-align: center;
      margin-top: 10px;
    }

    .nav label {
      cursor: pointer;
      padding: 5px;
      margin: 0 3px;
      background: #ccc;
      border-radius: 50%;
      display: inline-block;
      transition: background 0.3s;
    }

    .nav label:hover {
      background: #999;
    }

    #s1:checked ~ .slides { transform: translateX(0); }
    #s2:checked ~ .slides { transform: translateX(-100%); }
    #s3:checked ~ .slides { transform: translateX(-200%); }

    #s1:checked ~ .nav label[for="s1"],
    #s2:checked ~ .nav label[for="s2"],
    #s3:checked ~ .nav label[for="s3"] {
      background: #1e1818;
    }
    .title-overlay {
      position: absolute;
      top: 10px;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(0, 0, 0, 0.5);
      color: #fff;
      padding: 8px 16px;
      border-radius: 8px;
      font-size: 1.2em;
      z-index: 2;
      pointer-events: none;
    }
  
```


## OUTPUT
<img width="1263" height="669" alt="Screenshot 2025-11-14 092023" src="https://github.com/user-attachments/assets/60ce8be3-1c23-4219-b2ca-1b5d5f867d8a" />
<img width="1539" height="813" alt="image" src="https://github.com/user-attachments/assets/b88fcecf-99a6-4e23-87f4-65ccb98800ef" />
<img width="1544" height="813" alt="image" src="https://github.com/user-attachments/assets/fcb4a893-a774-455c-b898-6423c2b321cb" />




## RESULT
The program for creating Image Carousel using React is executed successfully.


