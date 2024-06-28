https://www.linkedin.com/in/jashmitha-usirikayala?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Landing Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Welcome to Our Product</h1>
        <p>Discover the amazing features of our product!</p>
    </header>

    <section class="features">
        <div class="feature">
            <img src="feature1.jpg" alt="Feature 1">
            <h2>Feature 1</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam vitae dui a nisl varius condimentum.</p>
        </div>
        <div class="feature">
            <img src="feature2.jpg" alt="Feature 2">
            <h2>Feature 2</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam vitae dui a nisl varius condimentum.</p>
        </div>
        <div class="feature">
            <img src="feature3.jpg" alt="Feature 3">
            <h2>Feature 3</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam vitae dui a nisl varius condimentum.</p>
        </div>
    </section>

    <footer>
        <p>Contact us for more information about our product.</p>
    </footer>
</body>
</html>
CSS (styles.css):

css
Copy code
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    text-align: center;
    padding: 20px;
    background-color: #f0f0f0;
}

.features {
    display: flex;
    justify-content: space-around;
    padding: 20px;
}

.feature {
    flex: 1;
    margin: 0 10px;
    padding: 20px;
    background-color: #f9f9f9;
    text-align: center;
}

.feature img {
    max-width: 100%;
    height: auto;
}

footer {
    text-align: center;
    padding: 20px;
    background-color: #333;
    color: #fff;
}
