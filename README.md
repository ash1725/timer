<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Time Spent Together</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f8f8;
            color: #333;
            text-align: center;
            padding-top: 50px;
        }
        h1 {
            color: #e91e63;
        }
        p {
            font-size: 20px;
        }
        .time {
            font-size: 24px;
            font-weight: bold;
        }
        .date {
            font-size: 18px;
            color: #888;
        }
    </style>
</head>
<body>
    <h1> Time Spent Together</h1>
    <p>i love you so much this is a small timer!</p>
    <div class="time" id="timeSpent">Calculating...</div>
    <div class="date" id="startDate"></div>

    <script>
        // Set the start date of your relationship
        const startDate = new Date("2023-10-07T00:00:00"); // Change the year if needed
        document.getElementById('startDate').textContent = `Started on: ${startDate.toDateString()}`;

        function calculateTimeSpent() {
            const currentDate = new Date();
            const timeDifference = currentDate - startDate;
            
            const days = Math.floor(timeDifference / (1000 * 3600 * 24));
            const hours = Math.floor((timeDifference % (1000 * 3600 * 24)) / (1000 * 3600));
            const minutes = Math.floor((timeDifference % (1000 * 3600)) / (1000 * 60));
            const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);

            document.getElementById('timeSpent').textContent = `${days} days, ${hours} hours, ${minutes} minutes, and ${seconds} seconds.`;
        }

        setInterval(calculateTimeSpent, 1000); // Update every second
    </script>
</body>
</html>
