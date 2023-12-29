<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OUD & NIEUW QUIZ</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background: #000;
            animation: glitter 5s infinite linear;
            font-family: 'Times New Roman', sans-serif;
            color: gold;
        }

        h1, h2, label, button, p {
            text-shadow: 1px 1px 5px rgba(255, 255, 255, 0.8);
        }

        @keyframes glitter {
            0%, 100% {
                background-position: 0 0;
            }
            25% {
                background-position: 50px 50px;
            }
            50% {
                background-position: 0 0;
            }
            75% {
                background-position: -50px -50px;
            }
        }

        .content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
        }

        button {
            padding: 10px;
            background-color: #f39c12;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #e67e22;
        }
    </style>
    <script src="https://cdn.rawgit.com/davidshimjs/qrcodejs/gh-pages/qrcode.min.js"></script>
</head>
<body>
    <div class="content">
        <h1>OUD & NIEUW QUIZ</h1>
        <h2>Malle boys + aanhang + jelice</h2>
        <label for="name">Vul hier je naam in:</label>
        <input type="text" id="name" required>
        <button onclick="assignRandomTeam()">Assign Team</button>
        <p id="assignedTeam"></p>
	<div id="starshine">
    	<div class="template shine"></div>
</div>
    </div>

    <script>
        function assignRandomTeam() {
            var name = document.getElementById("name").value;

            // Assign a random team number to each person
            var teamNumber = getRandomTeam();

            // Update the HTML content with the assigned team number
            document.getElementById("assignedTeam").innerText = name + ", jij hoort vanaf nu bij Team " + teamNumber;
        }

        function getRandomTeam() {
            // Assuming there are 9 people and each team has 3 members
            var totalPeople = 9;
            var peoplePerTeam = 3;

            // Create an array of team numbers
            var teamNumbers = Array.from({ length: totalPeople / peoplePerTeam }, (_, index) => index + 1);

            // Shuffle the array to randomize team assignment
            teamNumbers.sort(() => Math.random() - 0.5);

            // Get the next team number
            var nextTeam = teamNumbers.pop();

            return nextTeam;
        }
    </script>
</body>

</html>
