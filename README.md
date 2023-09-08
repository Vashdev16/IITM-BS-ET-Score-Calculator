# IITM-BS-ET-Score-Calculator


<!DOCTYPE html>
<html lang="en">
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f4f4f4;
    }

    .container {
        max-width: 600px;
        margin: 0 auto;
        padding: 20px;
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    h1 {
        text-align: center;
    }

    label {
        display: block;
        font-weight: bold;
        margin-top: 10px;
    }

    input[type="number"] {
        width: 97.67%;
        padding: 10px;
        margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 3px;
    }

    button {
        width: 90.00%;
        background-color: #000000;
        color: #fff;
        border: none;
        padding: 10px;
        cursor: pointer;
    }

    button:hover {
        background-color: #555555;
    }

    #result {
        font-weight: bold;
        margin-top: 10px;
        text-align: center;
    }
</style>

<div class="container">
    <h1>IITM BS Data Science Final End Term Score Calculator</h1>
    <label for="GAA">GAA:</label>
    <input type="number" id="GAA" placeholder="Enter GAA" step="0.01">

    <label for="Qz1">Qz1 Score:</label>
    <input type="number" id="Qz1" placeholder="Enter Qz1" step="0.01">

    <label for="Qz2">Qz2 Score:</label>
    <input type="number" id="Qz2" placeholder="Enter Qz2" step="0.01">

    <label for="F">Endterm Score:</label>
    <input type="number" id="F" placeholder="Enter Endterm Marks" step="0.01">

    <label for="activityMarks">Activity Marks if stats2 else ignore it:</label>
    <input type="number" id="activityMarks" placeholder="Enter Activity Marks" step="0.01" value="0">

    <label for="bonusMarks">Bonus Marks:</label>
    <input type="number" id="bonusMarks" placeholder="Enter Bonus Marks" step="0.01" value="0">

    <button onclick="calculateT()">Calculate Score</button>
    <p id="result"></p>
</div>

<script>
    function calculateT() {
        const GAA = parseFloat(document.getElementById("GAA").value);
        const F = parseFloat(document.getElementById("F").value);
        const Qz1 = parseFloat(document.getElementById("Qz1").value);
        const Qz2 = parseFloat(document.getElementById("Qz2").value);
        const activityMarks = parseFloat(document.getElementById("activityMarks").value);
        const bonusMarks = parseFloat(document.getElementById("bonusMarks").value);

        let T = 0.1 * GAA + Math.max(0.6 * F + 0.2 * Math.max(Qz1, Qz2), 0.4 * F + 0.2 * Qz1 + 0.3 * Qz2) + activityMarks;

        if (T > 39) {
            T += bonusMarks;
        }
        if (T > 100) {
            T = 100;
        }

        document.getElementById("result").textContent = `Final Marks = ${T.toFixed(2)}`;
    }
</script>



        </main>


    </div>

    <script src="/static/scripts/index.js"></script>

</body>


</html>
