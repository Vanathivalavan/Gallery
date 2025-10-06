<img width="1912" height="901" alt="Screenshot 2025-10-06 071000" src="https://github.com/user-attachments/assets/6b00f42d-d49b-487d-a20b-fae26f6efcc7" /># Ex.08 Design of Interactive Image Gallery
# Date:06.10.2025
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
urls.py
from django.contrib import admin
from django.urls import path
from van import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.home),
]

views.py
from django.shortcuts import render

def home(request):

    return render(request, 'home.html') 

home.html

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Photo Showcase</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: rgb(171, 96, 145);
      margin: 0;
      padding: 0;
    }

    header {
      background-color: #538bc8;
      color: white;
      text-align: center;
      padding: 15px;
      font-size: 24px;
      font-weight: bold;
    }

    .gallery {
      display: flex;
      justify-content: center;
      gap: 20px;
      padding: 30px;
      background: #d28b50;
      border-radius: 10px;
      margin: 20px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    .gallery img {
      width: 200px;
      height: 200px;
      object-fit: cover;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.3s;
    }

    .gallery img:hover {
        height: auto;
      transform: scale(1.05);
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 1000;
      padding-top: 80px;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.8);
    }

    .modal-content {
      margin: auto;
      display: block;
      max-width: 80%;
      border-radius: 10px;
    }

    .close {
      position: absolute;
      bottom: 50px;
      left: 50%;
      transform: translateX(-50%);
      background: red;
      color: white;
      border: none;
      padding: 15px;
      padding-bottom: 25px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 16px;
    }

    .close:hover {
      background: rgb(117, 86, 179);
    }
  </style>
</head>
<body>

  <header> Photo Showcase</header>

  <div class="gallery">
    <img src="{% static 'male4.png' %}" alt="Photo 1" onclick="openModal(this)">
    <img src="{% static 'male5.png' %}" alt="Photo 2" onclick="openModal(this)">
    <img src="{% static 'female1.png' %}" alt="Photo 3" onclick="openModal(this)">
    <img src="{% static 'female2.png' %}" alt="Photo 4" onclick="openModal(this)">
    <img src="{% static 'female3.png' %}" alt="Photo 5" onclick="openModal(this)">

  </div>

  
  <div id="myModal" class="modal">
    <img class="modal-content" id="modalImage">
    <button class="close" onclick="closeModal()">Close</button>
  </div>

  <script>
    function openModal(img) {
      document.getElementById("myModal").style.display = "block";
      document.getElementById("modalImage").src = img.src;
    }

    function closeModal() {
      document.getElementById("myModal").style.display = "none";
    }

    
    window.onclick = function(event) {
      let modal = document.getElementById("myModal");
      if (event.target == modal) {
        modal.style.display = "none";
      }
    }
  </script>

</body>
</html>

```
# OUTPUT:
<img width="1912" height="901" alt="Screenshot 2025-10-06 071000" src="https://github.com/user-attachments/assets/00cfd1a8-bfde-4e41-95cd-a603ba4b62af" />

<img width="1919" height="905" alt="Screenshot 2025-10-06 070946" src="https://github.com/user-attachments/assets/6138cfa0-13b4-4e1b-9f2b-d886c10efe02" />




# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
