# Project Responsive Web Design using Bootstrap
# Date:7/12/24
# AIM:
To create a simplified clone of Dribbble (https://dribbble.com/) landing page.

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Insert the necessary CSS and JavaScript files as external in order to use Bootstrap.

## Step 5:
Create a HTML file and include the needed Bootstrap components.

## Step 6:
Publish the website in the LocalHost.

# PROGRAM :
## project.html
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Up - Visual Projects</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&family=Roboto+Slab:wght@700&display=swap">
    <style>
        body {
            background-color: #f5f5dc;
            font-family: 'Raleway', sans-serif;
        }
        .header {
            background-color: #343a40;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        .gallery-title {
            margin: 20px 0;
            font-weight: bold;
        }
        .card {
            border: none;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .card img {
            height: 200px;
            object-fit: cover;
        }
        .card:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        .about-section {
            background-color: #fff;
            padding: 40px;
            margin-top: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
        .about-section h2 {
            text-align: center;
            margin-bottom: 20px;
        }
        .footer {
            background-color: #343a40;
            color: white;
            text-align: center;
            padding: 15px 0;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">
                <img src="https://smartupindia.co/wp-content/uploads/2024/08/WHITE-Logo-scaled.webp" alt="Smart Up Logo" style="height: 70px;">
            </a>
            <div class="collapse navbar-collapse">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" href="#gallery">Gallery</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#aboutUs">About Us</a>
                    </li>
                </ul>
                <div>
                    <a href="login.html" target="_blank" class="btn btn-outline-light">Login</a>
                    <a href="signup.html" target="_blank" class="btn btn-outline-light">Sign Up</a>
                </div>
            </div>
        </div>
    </nav>

    <header class="header">
        <h1 class="gallery-title">Popular Projects</h1>
    </header>

    <div class="container">
        <div id="gallery" class="row g-4">
            <!-- Cards will be dynamically inserted here -->
        </div>
    </div>

    <nav aria-label="Page navigation" class="mt-4 text-center">
        <ul class="pagination justify-content-center">
            <li class="page-item">
                <button id="prevButton" class="page-link" disabled>Previous</button>
            </li>
            <li class="page-item">
                <button id="nextButton" class="page-link" disabled>Next</button>
            </li>
        </ul>
    </nav>

    <div class="modal fade" id="lightboxModal" tabindex="-1" aria-labelledby="lightboxModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="lightboxModalLabel">Image Preview</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <img id="lightboxImage" src="" class="img-fluid" alt="Enlarged Image">
                </div>
                <div class="modal-footer">
                    <button class="btn btn-secondary" onclick="navigateLightbox(-1)">Previous</button>
                    <button class="btn btn-secondary" onclick="navigateLightbox(1)">Next</button>
                </div>
            </div>
        </div>
    </div>

    <div class="about-section" id="aboutUs">
        <h2>About Us</h2>
        <p>
            Smartup Visuals is a London-based studio specializing in visual communication, animation, and infographics. Since 2013, we have been helping businesses engage their audiences by transforming complex ideas into memorable visuals.
        </p>
    </div>

    <footer class="footer">
        <p>&copy; 2024 Smart Up Visuals</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        const projects = [
            { title: "Project 1", designer: "Bivrin", imgSrc: "https://cdn.pixabay.com/photo/2017/02/08/17/24/fantasy-2049567_640.jpg" },
            { title: "Project 2", designer: "Winegar", imgSrc: "https://cdn.pixabay.com/photo/2021/08/25/20/42/field-6574455_640.jpg" },
            { title: "Project 3", designer: "Mihailova", imgSrc: "https://cdn.pixabay.com/photo/2018/01/12/14/24/night-3078326_640.jpg" },
            { title: "Project 4", designer: "Makris", imgSrc: "https://cdn.pixabay.com/photo/2023/06/27/10/51/pier-8091934_640.jpg" },
            { title: "Project 5", designer: "Franklin", imgSrc: "https://cdn.pixabay.com/photo/2021/09/13/08/16/purple-flower-6620617_640.jpg" },
            { title: "Project 6", designer: "Zuidema", imgSrc: "https://cdn.pixabay.com/photo/2018/04/16/16/16/sunset-3325080_640.jpg" },
            { title: "Project 7", designer: "Asplund", imgSrc: "https://cdn.pixabay.com/photo/2018/08/14/13/23/ocean-3605547_640.jpg" },
            { title: "Project 8", designer: "Besliu", imgSrc: "https://cdn.pixabay.com/photo/2018/08/23/07/35/thunderstorm-3625405_640.jpg" },
        ];

        let currentIndex = 0;
        const totalProjects = projects.length;

        function displayProjects() {
            const gallery = document.getElementById('gallery');
            gallery.innerHTML = '';

            projects.forEach((project, index) => {
                const cardHTML = `
                    <div class="col-md-4 col-sm-6">
                        <div class="card">
                            <img src="${project.imgSrc}" class="card-img-top" alt="${project.title}" onclick="openLightbox(${index})">
                            <div class="card-body text-center">
                                <h5 class="card-title">${project.title}</h5>
                                <p class="text-muted">by ${project.designer}</p>
                            </div>
                        </div>
                    </div>
                `;
                gallery.insertAdjacentHTML('beforeend', cardHTML);
            });
        }

        function openLightbox(index) {
            currentIndex = index;
            document.getElementById('lightboxImage').src = projects[currentIndex].imgSrc;
            const lightboxModal = new bootstrap.Modal(document.getElementById('lightboxModal'));
            lightboxModal.show();
        }

        function navigateLightbox(direction) {
            currentIndex = (currentIndex + direction + totalProjects) % totalProjects;
            document.getElementById('lightboxImage').src = projects[currentIndex].imgSrc;
        }

        document.getElementById('prevButton').addEventListener('click', () => {
            navigateLightbox(-1);
        });

        document.getElementById('nextButton').addEventListener('click', () => {
            navigateLightbox(1);
        });

        displayProjects();
    </script>
</body>
</html>
~~~
## signup.html
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Up - Sign Up</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&family=Roboto+Slab:wght@700&display=swap">
    <style>
        body {
            background-color: #e9ecef;
            font-family: 'Raleway', sans-serif;
        }
        .signup-wrapper {
            max-width: 450px;
            margin: 80px auto;
            padding: 30px;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }
        .signup-header {
            text-align: center;
            margin-bottom: 25px;
        }
        .footer {
            text-align: center;
            margin-top: 30px;
            color: #6c757d;
        }
        .form-label {
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="signup-wrapper">
        <h2 class="signup-header">Create Your Account</h2>
        <form id="signupForm">
            <div class="mb-4">
                <label for="name" class="form-label">Full Name</label>
                <input type="text" class="form-control" id="name" placeholder="Enter your full name" required>
            </div>
            <div class="mb-4">
                <label for="email" class="form-label">Email Address</label>
                <input type="email" class="form-control" id="email" placeholder="Enter your email" required>
            </div>
            <div class="mb-4">
                <label for="password" class="form-label">Password</label>
                <input type="password" class="form-control" id="password" placeholder="Create a password" required>
            </div>
            <div class="mb-4">
                <label for="confirmPassword" class="form-label">Confirm Password</label>
                <input type="password" class="form-control" id="confirmPassword" placeholder="Confirm your password" required>
            </div>
            <button type="submit" class="btn btn-primary w-100">Sign Up</button>
        </form>
        <div class="mt-3 text-center">
            <p>Already have an account? <a href="login.html" class="text-decoration-none">Log In</a></p>
        </div>
    </div>

    <footer class="footer">
        <p>&copy; 2024 Smart Up Visuals</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        document.getElementById('signupForm').addEventListener('submit', function(event) {
            event.preventDefault();
            // Placeholder for sign-up logic
            alert('Sign-up functionality is currently not implemented.');
        });
    </script>
</body>
</html>
~~~
## login.html
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Up - User Login</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&family=Roboto+Slab:wght@700&display=swap">
    <style>
        body {
            background-color: #e9ecef;
            font-family: 'Raleway', sans-serif;
        }
        .login-wrapper {
            max-width: 450px;
            margin: 80px auto;
            padding: 30px;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }
        .login-header {
            text-align: center;
            margin-bottom: 25px;
        }
        .footer {
            text-align: center;
            margin-top: 30px;
            color: #6c757d;
        }
        .form-label {
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="login-wrapper">
        <h2 class="login-header">Welcome Back!</h2>
        <form id="loginForm">
            <div class="mb-4">
                <label for="email" class="form-label">Email Address</label>
                <input type="email" class="form-control" id="email" placeholder="Enter your email" required>
            </div>
            <div class="mb-4">
                <label for="password" class="form-label">Password</label>
                <input type="password" class="form-control" id="password" placeholder="Enter your password" required>
            </div>
            <button type="submit" class="btn btn-primary w-100">Log In</button>
        </form>
        <div class="mt-3 text-center">
            <a href="#" class="text-decoration-none">Forgot your password?</a>
        </div>
        <div class="mt-2 text-center">
            <p>New here? <a href="signup.html" class="text-decoration-none">Create an account</a></p>
        </div>
    </div>

    <footer class="footer">
        <p>&copy; 2024 Smart Up Visuals</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault();
            // Placeholder for login logic
            alert('Login functionality is currently not implemented.');
        });
    </script>
</body>
</html>
~~~
# OUTPUT:
![Screenshot 2024-12-25 092659](https://github.com/user-attachments/assets/cd539ec0-d0ff-47cb-a16f-ebd752f9d937)
![Screenshot 2024-12-25 092730](https://github.com/user-attachments/assets/324c76b6-3e6d-4671-a926-72103055c856)
![Screenshot 2024-12-25 092805](https://github.com/user-attachments/assets/885a7bf4-cfaf-4578-9f4a-da598fee452e)
![Screenshot 2024-12-25 092834](https://github.com/user-attachments/assets/360a46ff-0d34-4752-861d-aca604137cb3)
![Screenshot 2024-12-25 092859](https://github.com/user-attachments/assets/5042cf01-2686-43f2-af15-aafffc15253e)

# RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
