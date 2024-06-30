<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smooth Website with Button - Dark Theme and Effects</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #1a1a1a;
            font-family: Arial, sans-serif;
        }
        .button-container {
            position: relative;
            overflow: hidden;
            border-radius: 25px;
        }
        .button {
            padding: 15px 30px;
            font-size: 18px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.3);
            position: relative;
            overflow: hidden;
        }
        .button:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
            box-shadow: 0 6px 8px rgba(0,0,0,0.4);
        }
        .button:active {
            transform: translateY(0);
            box-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }
        .button::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, .5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }
        .button:focus:not(:active)::after {
            animation: ripple 1s ease-out;
        }
        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 1;
            }
            20% {
                transform: scale(25, 25);
                opacity: 1;
            }
            100% {
                opacity: 0;
                transform: scale(40, 40);
            }
        }
        .button:focus {
            outline: none;
            animation: glow 1s ease-in-out infinite alternate;
        }
        @keyframes glow {
            from {
                box-shadow: 0 0 5px #007bff, 0 0 10px #007bff, 0 0 15px #007bff, 0 0 20px #007bff;
            }
            to {
                box-shadow: 0 0 10px #007bff, 0 0 20px #007bff, 0 0 30px #007bff, 0 0 40px #007bff;
            }
        }
    </style>
</head>
<body>
    <div class="button-container">
        <button class="button">Hi</button>
    </div>
    <script>
        document.querySelector('.button').addEventListener('click', function(e) {
            this.blur();
            setTimeout(() => this.focus(), 10);
        });
    </script>
</body>
</html>
