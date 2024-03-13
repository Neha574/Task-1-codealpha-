# Task-1-codealpha-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Age Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 50px;
    }

    #result {
      font-size: 18px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <h1>Age Calculator</h1>

  <label for="dob">Date of Birth:</label>
  <input type="date" id="dob" required>

  <button onclick="calculateAge()">Calculate Age</button>

  <div id="result"></div>

  <script>
    function calculateAge() {
      // Get the user's input
      var dobInput = document.getElementById("dob").value;

      // Create a Date object from the input
      var dob = new Date(dobInput);

      // Get the current date
      var currentDate = new Date();

      // Calculate the age
      var age = currentDate.getFullYear() - dob.getFullYear();

      // Check if the birthday has occurred this year
      if (
        currentDate.getMonth() < dob.getMonth() ||
        (currentDate.getMonth() === dob.getMonth() && currentDate.getDate() < dob.getDate())
      ) {
        age--;
      }

      // Display the result
      var resultElement = document.getElementById("result");
      resultElement.textContent = "Your age is: " + age + " years";
    }
  </script>

</body>
</html>
