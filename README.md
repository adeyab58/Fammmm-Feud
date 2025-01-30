# Fammmm-Feud
<!DOCTYPE html>
<html>
<head>
    <title>International Students Family Feud</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            text-align: center;
            background-color: #ffebcd;
        }
        .container {
            max-width: 800px;
            margin: auto;
            padding: 20px;
            background: #ffcccb;
            border-radius: 20px;
            box-shadow: 0px 0px 15px rgba(0,0,0,0.2);
        }
        .question {
            font-size: 30px;
            font-weight: bold;
            color: #800000;
            margin-bottom: 20px;
        }
        .answer-box {
            width: 100%;
            padding: 20px;
            background-color: #ff69b4;
            color: white;
            font-size: 22px;
            border-radius: 10px;
            margin: 10px 0;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .answer-box:hover {
            background-color: #ff1493;
        }
        .answer-box.revealed {
            background-color: #32cd32;
            color: white;
        }
        button {
            padding: 12px 25px;
            font-size: 20px;
            margin-top: 20px;
            cursor: pointer;
            background-color: #4682b4;
            color: white;
            border: none;
            border-radius: 10px;
        }
        button:hover {
            background-color: #4169e1;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 style="color: #dc143c;">🎉 International Students Family Feud 🎉</h1>
        <div class="question" id="question">Click below to start!</div>
        <div id="answers"></div>
        <button onclick="nextQuestion()">Next Question ➡️</button>
    </div>

    <script>
        const questions = [
            {
                question: "Which app do international students use most to call home?",
                answers: ["WhatsApp", "FaceTime", "Messenger", "Skype", "Telegram"]
            },
            {
                question: "What’s the first fast-food chain most non-Americans try the minute they land?",
                answers: ["McDonald's", "Chick-fil-A", "Starbucks", "Burger King", "Chipotle"]
            },
            {
                question: "Name a common item international students forget to pack.",
                answers: ["Phone/laptop charger & voltage converters", "Winter Clothes", "Spices", "Copies of I-20", "Water bottle"]
            },
            {
                question: "Something international students do when they miss home.",
                answers: ["Cook home food", "Video call the fam", "Watch home TV shows", "Meet country-mates", "Start hiking to East Rock"]
            },
            {
                question: "What’s the first thing international students Google when they get to Yale?",
                answers: ["OISS address", "Phone plan", "Campus map", "Nearest Target", "Nearest bank"]
            },
            {
                question: "What’s something international students wish Americans understood about them?",
                answers: ["Eating time", "Taking shoes off", "Greeting styles"]
            },
            {
                question: "What’s the hardest part about being an international student at Yale?",
                answers: ["Home sickness", "Time zone difference", "Career planning", "Cultural references", "That god damn internship"]
            },
            {
                question: "What’s a completely normal thing from home that Americans find weird?",
                answers: ["Dating apps", "Casual dating", "Split bills", "DTR talk"]
            },
            {
                question: "What’s a US city that international students visit just to say they went?",
                answers: ["NYC", "Las Vegas", "LA", "Miami", "DC"]
            },
            {
                question: "What is the biggest dating culture shock for international students?",
                answers: ["Dating apps", "Casual dating", "Split bills", "DTR talk"]
            },
            {
                question: "What’s the most annoying thing about staying in the US for your education?",
                answers: ["Taxes", "Healthcare system", "Visa uncertainty", "Expensive tuition", "Internship visa issues"]
            },
            {
                question: "Why is the US like this?",
                answers: ["Tipping culture", "Imperial system", "Student debt", "Healthcare costs", "Gun laws"]
            },
            {
                question: "What is something international students secretly love about America?",
                answers: ["Free refills", "24/7 convenience stores", "Friendly strangers", "Big portions"]
            },
            {
                question: "What’s the best international food spot near Yale?",
                answers: ["House of Naan", "Tibetan Kitchen", "Taste of China", "Habesha", "Pad Thai"]
            },
            {
                question: "What is the most random item international students pack from home that no one else understands?",
                answers: ["Blanket you wore throughout high school", "Lucky charm", "Family Photos", "National flag", "Home Spices"]
            }
        ];

        let currentQuestionIndex = 0;

        function nextQuestion() {
            if (currentQuestionIndex < questions.length) {
                const questionContainer = document.getElementById("question");
                const answersContainer = document.getElementById("answers");
                
                questionContainer.textContent = questions[currentQuestionIndex].question;
                answersContainer.innerHTML = "";
                
                questions[currentQuestionIndex].answers.forEach(answer => {
                    let answerBox = document.createElement("div");
                    answerBox.classList.add("answer-box");
                    answerBox.textContent = "Click to Reveal";
                    answerBox.onclick = function() {
                        answerBox.textContent = answer;
                        answerBox.classList.add("revealed");
                    };
                    answersContainer.appendChild(answerBox);
                });
                
                currentQuestionIndex++;
            } else {
                document.getElementById("question").textContent = "Game Over! 🎊";
                document.getElementById("answers").innerHTML = "";
            }
        }
    </script>
</body>
</html>
