<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Should You Buy a Boat?</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            text-align: center;
            background: linear-gradient(to bottom, #00aaff, #66ccff);
            color: white;
            margin: 50px;
        }
        #question-container {
            margin-top: 20px;
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
            display: inline-block;
        }
        button {
            margin: 10px;
            padding: 15px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            background-color: #ffcc00;
            color: black;
            transition: 0.3s;
        }
        button:hover {
            background-color: #ff9900;
        }
        h1 {
            text-shadow: 2px 2px 4px #000000;
        }
    </style>
</head>
<body>
    <h1>Should You Buy a Boat?</h1>
    <div id="question-container">
        <p id="question">Do you own a boat?</p>
        <button onclick="nextQuestion('yes')">Yes</button>
        <button onclick="nextQuestion('no')">No</button>
    </div>
    <script>
        const questions = {
            'Do you own a boat?': {
                yes: "Then why are you here? No, you should not buy another boat.",
                no: "Do you want a boat?"
            },
            'Do you want a boat?': {
                yes: "Do you have any friends with a boat?",
                no: "No, you should not buy a boat."
            },
            'Do you have any friends with a boat?': {
                yes: "So you already have access to a boat. No, do not buy a boat",
                no: "Do you live near water?"
            },
            'Do you live near water?': {
                yes: "Can you afford a boat?",
                no: "Boats are useless if you don’t live near water. Do you own a pool big enough for one?"
            },
            'Can you afford a boat?': {
                yes: "Can your car tow 3,500+ lbs?",
                no: "No, you should not buy a boat."
            },
            'Can your car tow 3,500+ lbs?': {
                yes: "Do you want to be a pirate?",
                no: "Are you ready to buy a new car with your new boat?"
            },
            'Are you ready to buy a new car with your new boat?': {
                yes: "Have you ever heard the phrase 'A boat is a hole in the water you throw money into'?",
                no: "No, you should not buy a boat."
            },
            'Do you want to be a pirate?': {
                yes: "Then go steal a boat. No, you should not buy a boat.",
                no: "Have you ever heard the phrase 'A boat is a hole in the water you throw money into'?"
            },
            "Have you ever heard the phrase 'A boat is a hole in the water you throw money into'?": {
                yes: "Do you enjoy constant maintenance and repairs?",
                no: "Google 'boat maintenance horror stories'. Did you change your mind?"
            },
            "Do you enjoy constant maintenance and repairs?": {
                yes: "Do you have a lot of free time?",
                no: "No, you should not buy a boat."
            },
            "Do you have a lot of free time?": {
                yes: "Do you want to spend all your extra time and money fixing a boat?",
                no: "No, you should not buy a boat."
            },
            "Do you want to spend all your extra time and money fixing a boat?": {
                yes: "Have you considered just renting a boat?",
                no: "No, you should not buy a boat."
            },
            "Have you considered just renting a boat?": {
                yes: "Good, you should not buy a boat.",
                no: "What about golf?"
            },
            "What about golf?": {
                yes: "Good choice, don't buy a boat.",
                no: "Are you on track to save enough for retirement?"
            },
            "Are you on track to save enough for retirement?": {
                yes: "Okay, but do you think you could make friends with someone who owns a boat?",
                no: "Then no, you should not buy a boat."
            },
            "Okay, but do you think you could make friends with someone who owns a boat?": {
                yes: "Great, you should not buy a boat.",
                no: "Okay, maybe you should buy a boat?"
            },
            "Okay, maybe you should buy a boat?": {
                yes: "Do you have a lot of friends that will think this is also their boat?",
                no: "That's probably the right decision, don't buy a boat."
            },
            "Do you have a lot of friends that will think this is also their boat?": {
                yes: "No, you should not buy a boat.",
                no: "Do you need the boat to make friends?"
            },
            "Do you need the boat to make friends?": {
                yes: "I think there are some deeper issues here, maybe get some therapy first and come back later. No, you should not buy a boat.",
                no: "Do you have any friends?"
            },
            "Do you have any friends?": {
                yes: "Do you think you could convince any of them to buy a boat?",
                no: "Fuck it, go buy a boat."
            },
            "Do you think you could convince any of them to buy a boat?": {
                yes: "Whew. No, you should not buy a boat.",
                no: "Fuck it, go buy a boat."
            }
        };

        function nextQuestion(answer) {
            let currentQuestion = document.getElementById('question').innerText;
            let next = questions[currentQuestion]?.[answer];
            
            if (!next) {
                document.getElementById('question-container').innerHTML = '<h2>No, you should not buy a boat.</h2>';
            } else if (questions[next]) {
                document.getElementById('question').innerText = next;
            } else {
                document.getElementById('question-container').innerHTML = `<h2>${next}</h2>`;
            }
        }
    </script>
</body>
</html>
