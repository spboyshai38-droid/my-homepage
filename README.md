
   <p>I am building this game for myself to earn a new computer! And for you guys to level up your language skills!</p>

     <!-- THE GAME CONTAINER -->
    <div class="game-box">
        <h2>Language Guessing Game</h2>
        <p>What country speaks this language?</p>
        
        <!-- The language sample text -->
        <h1 id="language-phrase" style="color: #2d3748; background: #edf2f7; padding: 20px; border-radius: 8px;">Bonjour! Comment ça va?</h1>

        <input type="text" id="user-guess" placeholder="Type country name here...">
        <br>
        <button onclick="checkAnswer()">Submit Guess</button>

        <p id="message"></p>
    </div>

    <script>
        const gameData = [
            {phrase: "Bonjour! Comment ça va?", country: "France"},
            {phrase: "Hola! ¿Cómo estás?", country: "Spain"},
            {phrase: "Hallo! Wie geht's?", country: "Germany"},
            {phrase: "Ciao! Come stai?", country: "Italy"},
            {phrase: "Olá! Como você está?", country: "Brazil"},
            {phrase: "Namaste! Aap kaise hain?", country: "India"},
            {phrase: "Konnichiwa! O genki desu ka?", country: "Japan"},
            {phrase: "Nihao! Nǐ hǎo ma?", country: "China"},
            {phrase: "Priyet! Kak dela?", country: "Russia"},
            {phrase: "Hello! How are you doing today?", country: "United States"},
            {phrase: "G'Day Mate! How ya going?", country: "Australia"},
            {phrase: "Annyeonghaseyo!", country: "South Korea"},
            {phrase: "Merhaba! Nasılsın?", country: "Turkey"},
            {phrase: "Ahlan! Kayfa haluk?", country: "Egypt"}, 
            {phrase: "Shalom! Ma shlomcha?", country: "Israel"},
            {phrase: "Sawubona! Unjani?", country: "South Africa"},
            {phrase: "As-salamu alaykum!", country: "Saudi Arabia"},
            {phrase: "Sawadee khrap! Sabai dee mai", country: "Thailand"},
            {phrase: "Halo! Apa kabar?", country: "Indonesia"},
            {phrase: "Jambo! Habari gani", country: "Kenya"},
            {phrase: "Chao ban! Khoe khong", country: "Vietnam"},
            {phrase: "¡Che! ¿Cómo andás? ¿Todo bien?", country: "Argentina"},
            {phrase: "Olá! Como está? Tudo bem?", country: "Portugal"}

        ];
        
        let currentRound = 0;

        function checkAnswer() {
            const guessInput = document.getElementById('user-guess');
            const messageElement = document.getElementById('message');
            const userGuess = guessInput.value.trim().toLowerCase();
            const correctCountry = gameData[currentRound].country.toLowerCase();

            if (userGuess === correctCountry) {
                messageElement.style.color = 'green';
                messageElement.innerText = "🎉 Correct! Awesome job!";
                
                // Wait 2 seconds, then automatically move to the next round!
                setTimeout(nextRound, 2000);
            } else {
                messageElement.style.color = 'red';
                messageElement.innerText = "❌ Not quite! Try again!";
            }
        }

        function nextRound() {
            currentRound = currentRound + 1;

            // Go back to the first language if we run out of rounds
            if (currentRound >= gameData.length) {
                currentRound = 0;
            }

            // Update the screen with the new phrase
            document.getElementById('language-phrase').innerText = gameData[currentRound].phrase;
            document.getElementById('user-guess').value = '';
            document.getElementById('message').innerText = '';
        }
    </script>



















