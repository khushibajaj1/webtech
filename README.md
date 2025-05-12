<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guess the Brainrot Character</title>
    <style>
        body {
            text-align: center;
            font-family: 'Arial', sans-serif;
            background-color: #f7f7f7;
            color: #333;
            padding: 20px;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            color: #FF6347;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
        }

        img {
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            margin-bottom: 30px;
            transition: transform 0.3s ease;
        }

        img:hover {
            transform: scale(1.1);
        }

        button {
            background-color: #FF6347;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 5px;
            font-size: 1.2rem;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.3s;
        }

        button:hover {
            background-color: #FF4500;
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(2px);
        }

        #resultMessage {
            font-size: 1.5rem;
            font-weight: bold;
            margin-top: 20px;
            color: #28a745;
        }

        /* For larger screens */
        @media (min-width: 768px) {
            h1 {
                font-size: 4rem;
            }

            button {
                font-size: 1.5rem;
            }

            img {
                width: 300px;
            }
        }
    </style>
</head>
<body>

    <h1>Guess the Brainrot Character!</h1>
    <img id="characterImage" src="" width="200" alt="Brainrot Character" />
    <br><br>

    <!-- Buttons for guessing -->
    <button onclick="checkGuess('Bellariana Cappuchina')">Bellariana Cappuchina</button>
    <button onclick="checkGuess('Tun Tun Tun sahur')">Tun Tun Tun Sahur</button>
    <button onclick="checkGuess('Brr Brr Patapim')">Brr Brr Patapim</button>
    <button onclick="checkGuess('Tralalelo Tralala')">Tralalelo Tralala</button>
    <button onclick="checkGuess('Lirili Larila')">Lirili Larila</button>
    <button onclick="checkGuess('Bombardino Crocodilo')">Bombardino Crocodilo</button>

    <p id="resultMessage"></p>

    <script>
        // List of 6 characters with their name and image
        const characters = [
            { name: "Bellariana Cappuchina", image: "https://images.genius.com/a3e0a0feb6afd4f19c0c68817ee75238.718x718x1.png" },
            { name: "Tun Tun Tun sahur", image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQF0Bi9fCwrQBhZBgrnMl5F60rnNaXC6CbEvg&s" },
            { name: "Brr Brr Patapim", image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS440Zig25xFF48T8Rnds52qZF4lQqdtlLfRA&s" },
            { name: "Tralalelo Tralala", image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQhRSBihyxJZa9ntpLZVHc_xHMCKwCHDPUnDg&s" },
            { name: "Lirili Larila", image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSUclYZgE3Aqs6M-9PqCKUow3FWQMlYxx0Kyw&s" },
            { name: "Bombardino Crocodilo", image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7oBex_gwatjeJ1D1ZX3mVXEQujKe8qPYwzg&s" }
        ];

        // Get a random character from the list
        let currentCharacter = characters[Math.floor(Math.random() * characters.length)];
        document.getElementById("characterImage").src = currentCharacter.image;

        // Function to check the user's guess
        function checkGuess(userChoice) {
            if (userChoice === currentCharacter.name) {
                document.getElementById("resultMessage").textContent = "🎉 Correct!";
                document.getElementById("resultMessage").style.color = "#28a745";  // Green color for success
            } else {
                document.getElementById("resultMessage").textContent = "❌ Wrong. Try again!";
                document.getElementById("resultMessage").style.color = "#dc3545";  // Red color for failure
            }

            // Load a new random character after each guess
            currentCharacter = characters[Math.floor(Math.random() * characters.length)];
            document.getElementById("characterImage").src = currentCharacter.image;
        }
    </script>

</body>
</html>
