# He168.github.io
<!DOCTYPE html>
<html>

<body>
    <h2>Simple Guessing Game</h2>
    
        <input type="radio" id="over35" name="guess" value="over35">
        <label for="over35">Over 35</label><br>
        <input type="radio" id="below35" name="guess" value="below35">
        <label for="below35">Below 35</label><br><br>
        
        <button onclick="runGame()">RUN</button>
        <button onclick="resetGame()">RESET</button><br><br>
        
		<label for="Simple Guessing Game">Simple Guessing Game:</label>
        <input type="text" id="result" readonly>
<script>
	function runGame() {
    const guessOver35 = document.getElementById("over35").checked;
    const guessBelow35 = document.getElementById("below35").checked;
    const resultBox = document.getElementById("result");

    if (!guessOver35 && !guessBelow35) {
        alert("Please select either 'Over 35' or 'Below 35' option.");
        return;
    }

    const randomNumber = Math.floor(Math.random() * 100);
    resultBox.value = randomNumber;

    if (randomNumber === 35) {
        alert("It was a tie, please try again.");
    } else if ((guessOver35 && randomNumber > 35) || (guessBelow35 && randomNumber < 35)) {
        alert("WIN: Good bet!");
    } else {
        alert("LOSE: Wrong bet.");
    }
}

function resetGame() {
    document.getElementById("result").value = "";
    document.getElementById("over35").checked = false;
    document.getElementById("below35").checked = false;
}
</script>
