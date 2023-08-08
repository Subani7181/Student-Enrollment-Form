# Student-Enrollment-Form
<!DOCTYPE html>
<html>
<head>
    <title>Student Enrollment Form</title>
    <script>
        // Function to enable or disable buttons and fields
        function toggleFormElements(disabled) {
            document.getElementById("saveBtn").disabled = disabled;
            document.getElementById("updateBtn").disabled = disabled;
            document.getElementById("resetBtn").disabled = disabled;
            document.getElementById("rollNo").disabled = !disabled;
            document.getElementById("fullName").disabled = disabled;
            document.getElementById("class").disabled = disabled;
            document.getElementById("birthDate").disabled = disabled;
            document.getElementById("address").disabled = disabled;
            document.getElementById("enrollmentDate").disabled = disabled;
        }

        // Function to reset the form
        function resetForm() {
            document.getElementById("enrollmentForm").reset();
            toggleFormElements(false);
            document.getElementById("rollNo").focus();
        }

        // Function to save data
        function saveData() {
            // Simulate saving data to the database
            alert("Data saved!");
            resetForm();
        }

        // Function to update data
        function updateData() {
            // Simulate updating data in the database
            alert("Data updated!");
            resetForm();
        }
    </script>
</head>
<body>
    <form id="enrollmentForm">
        Roll No.: <input type="text" id="rollNo" required><br>
        Full Name: <input type="text" id="fullName" disabled required><br>
        Class: <input type="text" id="class" disabled required><br>
        Birth Date: <input type="date" id="birthDate" disabled required><br>
        Address: <input type="text" id="address" disabled required><br>
        Enrollment Date: <input type="date" id="enrollmentDate" disabled required><br>
        <button id="saveBtn" type="button" disabled onclick="saveData()">Save</button>
        <button id="updateBtn" type="button" disabled onclick="updateData()">Update</button>
        <button id="resetBtn" type="button" onclick="resetForm()">Reset</button>
    </form>
    <script>
        // Set initial state on page load
        toggleFormElements(false);
        document.getElementById("rollNo").addEventListener("change", function() {
            toggleFormElements(true);
            document.getElementById("fullName").focus();
        });
    </script>
</body>
</html>
