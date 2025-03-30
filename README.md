# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript DOM Manipulation & Animations</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }

        button {
            padding: 10px;
            margin: 10px;
            cursor: pointer;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s ease-in-out;
        }

        button:hover {
            background-color: #0056b3;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .animated {
            animation: fadeIn 1s ease-in-out;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to JavaScript DOM Manipulation & Animations</h1>
    </header>
    <main>
        <p id="text">Click the button to change this text!</p>
        <button id="changeTextBtn">Change Text</button>
        <button id="toggleElementBtn">Add Element</button>
        <button id="animateBtn">Animate Element</button>
        <button id="savePreferenceBtn">Save Preference</button>
        <button id="loadPreferenceBtn">Load Preference</button>
        <div id="elementContainer"></div>
    </main>
    <script>
        document.addEventListener("DOMContentLoaded", function () {
            const textElement = document.getElementById("text");
            const changeTextBtn = document.getElementById("changeTextBtn");
            const toggleElementBtn = document.getElementById("toggleElementBtn");
            const animateBtn = document.getElementById("animateBtn");
            const savePreferenceBtn = document.getElementById("savePreferenceBtn");
            const loadPreferenceBtn = document.getElementById("loadPreferenceBtn");
            const container = document.getElementById("elementContainer");
            changeTextBtn.addEventListener("click", function () {
                textElement.textContent = "Text has been changed!";
                textElement.style.color = "blue";
                textElement.style.fontWeight = "bold";
            });
            toggleElementBtn.addEventListener("click", function () {
                if (container.innerHTML === "") {
                    const newElement = document.createElement("p");
                    newElement.textContent = "A new paragraph has been added!";
                    newElement.style.color = "green";
                    container.appendChild(newElement);
                    toggleElementBtn.textContent = "Remove Element";
                } else {
                    container.innerHTML = "";
                    toggleElementBtn.textContent = "Add Element";
                }
            });
            animateBtn.addEventListener("click", function () {
                textElement.classList.add("animated");
                setTimeout(() => textElement.classList.remove("animated"), 1000);
            });
            savePreferenceBtn.addEventListener("click", function () {
                localStorage.setItem("preferredText", textElement.textContent);
                alert("Preference saved!");
            });
            loadPreferenceBtn.addEventListener("click", function () {
                const savedText = localStorage.getItem("preferredText");
                if (savedText) {
                    textElement.textContent = savedText;
                    alert("Preference loaded!");
                } else {
                    alert("No saved preference found.");
                }
            });
        });
    </script>
</body>
</html>

