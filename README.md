
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Changer</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            margin-top: 50px;
        }
        img {
            width: 300px;
            height: 500px;
            border-radius: 10px;
            margin: 20px;
        }
        button {
            padding: 10px 15px;
            font-size: 16px;
            margin: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h2>Image Changer</h2>
    <img id="image" alt="Image">
    <br>
    <button onclick="prevImage()">Previous</button>
    <button onclick="nextImage()">Next</button>


    <script>
        const images = [
            "pic1.jpg",
            "pic2.jpg",
        ];

        let currentIndex = 0;
        // Set the default image on page load
        window.onload = function () {
            document.getElementById("image").src = images[currentIndex];
        };
        function nextImage() {
            currentIndex = (currentIndex + 1) % images.length;//1%2=1
            document.getElementById("image").src = images[currentIndex];
        }
        function prevImage() {//0%2=>0
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            document.getElementById("image").src = images[currentIndex];//0
        }
    </script>

</body>
</html>
