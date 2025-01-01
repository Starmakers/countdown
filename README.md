<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countdown Timer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f3f4f6;
        }
        .countdown {
            text-align: center;
            background: #ffffff;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .countdown h1 {
            font-size: 2em;
            margin-bottom: 20px;
        }
        .time {
            font-size: 1.5em;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="countdown">
        <h1>Special Offer Ends In:</h1>
        <div class="time" id="countdown-timer"></div>
    </div>

    <script>
        // Set the target date and time for the countdown
        const targetDate = new Date("2025-01-07T23:59:59").getTime();

        // Update the countdown every second
        const countdownInterval = setInterval(() => {
            const now = new Date().getTime();
            const distance = targetDate - now;

            if (distance < 0) {
                clearInterval(countdownInterval);
                document.getElementById("countdown-timer").innerHTML = "Offer Expired!";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("countdown-timer").innerHTML =
                `${days}d ${hours}h ${minutes}m ${seconds}s`;
        }, 1000);
    </script>
</body>
</html>
# countdown
