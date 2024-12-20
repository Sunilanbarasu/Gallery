# Ex.08 Design of Interactive Image Gallery
# Date:17-12-2024
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MY GALLERY</title>
    <style>
        body {
            font-family:Georgia, 'Times New Roman', Times, serif;
            margin: 0;
            padding: 0;
            background-color: rgb(230, 14, 14);
            display: flex;
            flex-direction: column;
            align-items: center;
            height: 100vh;
        }

        .title {
            position: absolute;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 42px;
            font-style: oblique;
            color: rgb(231, 255, 12);
            text-shadow: 2px 2px 4px rgba(10, 9, 241, 0.6);
        }

        .gallery-container {
            display:grid;
            grid-template-columns: repeat(auto-fill, minmax(370px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            width: 100%;
            margin-bottom: auto;
            margin-top: 10%;
        }

        .gallery-item {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .gallery-item img {
            max-width: 110%; 
            height: 300px; 
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .gallery-item img:hover {
            transform: scale(1.40);
            cursor: pointer;
        }

        .slider {
            display: none;
            position: fixed;
            z-index: 2;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 100%;
            text-align: center;
        }

        .slider img {
            width: 90%;
            max-width: 800px;
            border-radius: 10px;
            transition: opacity 0.5s ease;
        }

        .arrow {
            cursor: pointer;
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 40px;
            color: rgb(17, 249, 67);
            user-select: none;
            padding: 10px;
        }

        .arrow.left {
            left: 10px;
            color: rgb(198, 240, 13);
        }

        .arrow.right {
            right: 10px;
            color: rgb(218, 241, 17);
        }

        .arrow:hover {
            color: rgb(211, 211, 211);
        }

        .close-btn {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(219, 241, 19, 0.6);
            color: rgb(213, 9, 9);
            border: none;
            padding: 10px;
            cursor: pointer;
            font-size: 30px;
            border-radius: 5px;
            display: none; /* Initially hidden */
        }

        .close-btn:hover {
            background-color: rgba(22, 232, 7, 0.8);
        }

        footer {
            width: 100%;
            background-color: rgb(181, 233, 9);
            color: rgb(19, 3, 90);
            text-align: center;
            padding: 10px;
            font-size: 25px;
            position: absolute;
            font-weight: 600;
            font-style:inherit;
            bottom: 0;
        }
    </style>
</head>
<body>
    <div class="title">MY GALLERY</div> 
    
    <div class="gallery-container">
        <div class="gallery-item">
            <img src="vijay.jpeg" alt="Image 1">
        </div>
        <div class="gallery-item">
            <img src="Msd.jpeg" alt="Image 2">
        </div>
        <div class="gallery-item">
            <img src="kohli.jpeg" alt="Image 3">
        </div>
        <div class="gallery-item">
            <img src="r&j.jpeg" alt="Image 4">
        </div>
        <div class="gallery-item">
            <img src="Shinchan.jpeg" alt="Image 5">
        </div>
        <div class="gallery-item">
            <img src="Doraemon.jpeg" alt="Image 6">
        </div>
    </div>

    <div class="slider" id="slider">
        <button class="close-btn" id="close-btn">&#10006;</button>
        <span class="arrow left" id="prev">&#10094;</span>
        <img src="" alt="Slider Image" id="slider-img">
        <span class="arrow right" id="next">&#10095;</span>
    </div>

    <footer>
        Designed by Sunil A
    </footer>

    <script>
        const images = document.querySelectorAll('.gallery-item img');
        const slider = document.getElementById('slider');
        const sliderImg = document.getElementById('slider-img');
        const prevBtn = document.getElementById('prev');
        const nextBtn = document.getElementById('next');
        const closeBtn = document.getElementById('close-btn');

        let currentIndex = 0;
        images.forEach((image, index) => {
            image.addEventListener('click', () => {
                slider.style.display = 'block';
                sliderImg.src = image.src;
                currentIndex = index;
                closeBtn.style.display = 'block';
            });
        });

        prevBtn.addEventListener('click', (e) => {
            e.stopPropagation(); 
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            sliderImg.src = images[currentIndex].src;
        });

        nextBtn.addEventListener('click', (e) => {
            e.stopPropagation(); 
            currentIndex = (currentIndex + 1) % images.length;
            sliderImg.src = images[currentIndex].src;
        });

        closeBtn.addEventListener('click', (e) => {
            e.stopPropagation(); 
            slider.style.display = 'none';
            closeBtn.style.display = 'none'; 
        });

        slider.addEventListener('click', () => {
            slider.style.display = 'none';
            closeBtn.style.display = 'none'; // Hide the close button
        });
    </script>
</body>
</html>







```
# OUTPUT:

![alt text](<vijay/im 1.png>)

![s](<vijay/im 2.png>)


# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
