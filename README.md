# Ex05 Image Carousel
## Date:28-05-2026

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
```
import { useState } from "react";

import img1 from "./assets/img2.jpeg";
import img2 from "./assets/naveen.jpeg";
import img3 from "./assets/madhav.jpeg";

export default function App() {
  const images = [img1, img2, img3];

  const [currentIndex, setCurrentIndex] = useState(0);

  const nextImage = () => {
    setCurrentIndex(
      currentIndex === images.length - 1 ? 0 : currentIndex + 1
    );
  };

  const prevImage = () => {
    setCurrentIndex(
      currentIndex === 0 ? images.length - 1 : currentIndex - 1
    );
  };

  return (
    <div style={styles.container}>
      <h1>Image Carousel</h1>

      <div style={styles.carousel}>
        <button onClick={prevImage}>◀</button>

        <img
          src={images[currentIndex]}
          alt="carousel"
          style={styles.image}
        />

        <button onClick={nextImage}>▶</button>
      </div>
    </div>
  );
}

const styles = {
  container: {
    textAlign: "center",
    marginTop: "30px",
  },

  carousel: {
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
    gap: "20px",
  },

  image: {
    width: "600px",
    height: "400px",
    objectFit: "cover",
    borderRadius: "10px",
  },
};

```

## OUTPUT
<img width="1919" height="1007" alt="image" src="https://github.com/user-attachments/assets/ba911373-8ec9-4594-b2df-05ed59fe65d2" />

<img width="1919" height="1015" alt="image" src="https://github.com/user-attachments/assets/886c933a-250d-4f19-9562-a2bbe2794552" />

<img width="1919" height="1012" alt="image" src="https://github.com/user-attachments/assets/f390bbb2-072a-4f19-998d-23bda85131cd" />




## RESULT
The program for creating Image Carousel using React is executed successfully.
