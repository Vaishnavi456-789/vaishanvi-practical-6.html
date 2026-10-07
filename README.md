<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Student Grade Calculator</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            background-color: white;
            width: 350px;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 0 10px gray;
        }

        h1 {
            text-align: center;
            color: #333;
        }

        label {
            display: block;
            margin-top: 12px;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            box-sizing: border-box;
            border: 1px solid #aaa;
            border-radius: 5px;
        }

        button {
            width: 100%;
            padding: 12px;
            margin-top: 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        button:hover {
            background-color: #0056b3;
        }

        #result {
            margin-top: 20px;
            padding: 15px;
            background-color: #f0f8ff;
            border-radius: 5px;
            text-align: center;
            font-size: 17px;
        }
    </style>
</head>

<body>

    <div class="container">

        <h1>Grade Calculator</h1>

        <label>Subject 1 Marks</label>
        <input type="number" id="sub1" min="0" max="100">

        <label>Subject 2 Marks</label>
        <input type="number" id="sub2" min="0" max="100">

        <label>Subject 3 Marks</label>
        <input type="number" id="sub3" min="0" max="100">

        <label>Subject 4 Marks</label>
        <input type="number" id="sub4" min="0" max="100">

        <label>Subject 5 Marks</label>
        <input type="number" id="sub5" min="0" max="100">

        <button onclick="calculateGrade()">Calculate Grade</button>

        <div id="result"></div>

    </div>

    <script>

        function calculateGrade() {

            // Get marks from input fields
            let sub1 = Number(document.getElementById("sub1").value);
            let sub2 = Number(document.getElementById("sub2").value);
            let sub3 = Number(document.getElementById("sub3").value);
            let sub4 = Number(document.getElementById("sub4").value);
            let sub5 = Number(document.getElementById("sub5").value);

            // Calculate total marks
            let total = sub1 + sub2 + sub3 + sub4 + sub5;

            // Calculate percentage
            let percentage = (total / 500) * 100;

            // Calculate grade
            let grade;

            if (percentage >= 90) {
                grade = "A+";
            }
            else if (percentage >= 80) {
                grade = "A";
            }
            else if (percentage >= 70) {
                grade = "B";
            }
            else if (percentage >= 60) {
                grade = "C";
            }
            else if (percentage >= 50) {
                grade = "D";
            }
            else {
                grade = "F";
            }

            // Display result
            document.getElementById("result").innerHTML =
                "<strong>Total Marks:</strong> " + total + " / 500<br>" +
                "<strong>Percentage:</strong> " + percentage.toFixed(2) + "%<br>" +
                "<strong>Grade:</strong> " + grade;
        }

    </script>

</body>
</html>
