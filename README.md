## MWAD_EX05_image-carousel-in-react
## NAME: Praveena M
## REG NO: 212223040153
## Date: 09/05/2025
## AIM
To create a Image Carousel using React

## ALGORITHM
## STEP 1 Initial Setup:
## Input: A list of images to display in the carousel.

## Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

## Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

## Step 3 Navigation Controls:
## Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo: currentIndex = (currentIndex + 1) % images.length;

## Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image: currentIndex = (currentIndex - 1 + images.length) % images.length;

## Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

## Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
## Img.jsx
```
import React, { useState } from 'react';
import './an.css';

import img1 from './assets/img1.png';
import img2 from './assets/img2.png';
import img3 from './assets/img3.jpeg'; 

const images = [img1, img2, img3];

function App() {
  const [index, setIndex] = useState(0);

  const showPrevious = () => {
    setIndex((prevIndex) => (prevIndex === 0 ? images.length - 1 : prevIndex - 1));
  };

  const showNext = () => {
    setIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  };

  return (
    <div className="app">
      <h1 className="title">Flowers Carousel</h1>
      <div className="carousel">
        <img src={images[index]} alt="Flowers" className="carousel-image" />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>
      <footer className="footer">Praveena M 212223040153</footer>
    </div>
  );
}

export default App;









```

## Img.css

```
.app {
  text-align: center;
  margin-top: 40px;
  background-color: #102d49;  /* light background color */
  width: 600px;               /* set fixed width */
  height: 600px;              /* set fixed height */
  margin-left: auto;          /* center horizontally */
  margin-right: auto;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 15px rgba(0,0,0,0.2);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.title {
  font-size: 2rem;
  margin-bottom: 20px;
}

.carousel {
  width: 500px;
  height: auto;
  margin: 0 auto; /* centers the carousel horizontally */
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 0 10px #aaa;
}

.carousel-image {
  width: 100%;
  height: auto;
  display: block;
  margin: 0 auto; /* centers the image if needed */
}

.buttons {
  margin-top: 20px;
}

button {
  margin: 0 10px;
  padding: 10px 20px;
  font-size: 1rem;
  cursor: pointer;
}

/* New footer style */
.footer {
  margin-top: 30px;
  font-size: 1rem;
  color: #f8f0f0;
  font-style: italic;
}
.carousel {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 0 10px #aaa;
  margin: 0 auto; /* centers carousel itself */
}

.carousel-image {
  max-width: 100%;
  max-height: 400px;
  object-fit: contain;
  display: block;
}
/* index.css */
body, html {
  height: 100%;
  margin: 0;
  display: flex;
  justify-content: center; /* center horizontally */
  align-items: center;     /* center vertically */
  background-color: #1e1e1e; /* optional: dark background like your screenshot */
  font-family: sans-serif;
}



```
## OUTPUT
![Screenshot 2025-05-20 233732](https://github.com/user-attachments/assets/62baac2b-fae8-4cff-9688-e44d8bef6a06)
![Screenshot 2025-05-20 233740](https://github.com/user-attachments/assets/1173a4a8-aac0-45b0-9b97-ee8032c48d73)
![Screenshot 2025-05-20 233747](https://github.com/user-attachments/assets/05f5e6e1-6418-4a1a-8e48-cecbc890bb76)

## OUTPUT:
The Program was executedd successfully
