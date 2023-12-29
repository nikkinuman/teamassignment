<!DOCTYPE html>

<html lang="en">
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
