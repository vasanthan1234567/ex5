# Ex.05 Design a Website for Server Side Processing
# Date:27.04.2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lamp Filament Power Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f4f9;
            color: #333;
        }
        h1 {
            text-align: center;
            color: #444;
        }
        .calculator {
            max-width: 400px;
            margin: 0 auto;
            padding: 20px;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        input[type="number"] {
            width: calc(100% - 22px);
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            color: #007BFF;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Lamp Filament Power Calculator</h1>
    <div class="calculator">
        <form id="powerForm">
            <label for="intensity">Intensity (I) in Amperes:</label>
            <input type="number" id="intensity" name="intensity" step="0.01" required>
            
            <label for="resistance">Resistance (R) in Ohms:</label>
            <input type="number" id="resistance" name="resistance" step="0.01" required>
            
            <button type="button" onclick="calculatePower()">Calculate Power</button>
        </form>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculatePower() {
            const intensity = parseFloat(document.getElementById('intensity').value);
            const resistance = parseFloat(document.getElementById('resistance').value);
            
            if (isNaN(intensity) || isNaN(resistance) || intensity <= 0 || resistance <= 0) {
                document.getElementById('result').textContent = "Please enter valid positive numbers.";
                return;
            }

            const power = Math.pow(intensity, 2) * resistance;
            document.getElementById('result').textContent = Power (P): ${power.toFixed(2)} Watts;
        }
    </script>
</body>
</html>

url.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrectangle/',views.rectarea,name="areaofrectangle"),
    path('',views.rectarea,name="areaofrectangleroot")
]

views.py

from django.shortcuts import render

def rectarea(request):
    context={}
    context['area'] = "0"
    context['l'] = "0"
    context['b'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        l = request.POST.get('length','0')
        b = request.POST.get('breadth','0')
        print('request=',request)
        print('Length=',l)
        print('Breadth=',b)
        area = 2*(int(l)**2) + 4*int(l)*int(b)
        context['area'] = area
        context['l'] = l
        context['b'] = b
        print('Area=',area)
    return render(request,'mathapp/math.html',context)

# OUTPUT

![WhatsApp Image 2024-12-19 at 2 14 06 PM](https://github.com/user-attachments/assets/bed9b597-8f30-45ff-9c25-e2273a43e21b)
![WhatsApp Image 2024-12-19 at 2 14 13 PM](https://github.com/user-attachments/assets/ff93a96b-37b4-48c1-aa5e-03397c54176e)

# RESULT
The program for performing server side processing is completed successfully.
