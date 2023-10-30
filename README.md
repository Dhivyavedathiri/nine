<!DOCTYPE html>
<html>
<head>
    <script>
        // Function to store data in localStorage
        function storeData() {
            // Get the input values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;

            // Create an object to store the user's data
            const userData = {
                name: name,
                email: email
            };

            // Convert the object to a JSON string
            const userDataJSON = JSON.stringify(userData);

            // Store the data in localStorage
            localStorage.setItem('userData', userDataJSON);

            alert('Data has been stored in local storage.');
        }

        // Function to retrieve data from localStorage
        function retrieveData() {
            // Get the data from localStorage
            const userDataJSON = localStorage.getItem('userData');

            if (userDataJSON) {
                // Parse the JSON string to get the object
                const userData = JSON.parse(userDataJSON);

                // Display the data
                alert('Name: ' + userData.name + '\nEmail: ' + userData.email);
            } else {
                alert('No data found in local storage.');
            }
        }
    </script>
</head>
<body>
    <h1>Store and Retrieve User Data</h1>
    <label for="name">Name:</label>
    <input type="text" id="name">
    <br>
    <label for="email">Email:</label>
    <input type="email" id="email">
    <br>
    <button onclick="storeData()">Submit</button>
    <button onclick="retrieveData()">Retrieve Data</button>
</body>
</html>
