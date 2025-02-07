
<html>
    <head>
        <title>Valentine's Day Proposal</title>
        <style>
            html, body {
                height: 100%; /* Ensures the background covers the full screen */
                margin: 0;
                overflow: hidden; /* Prevent scrollbars */
            }
            body {
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                background: linear-gradient(to top, rgb(103, 216, 254), rgb(250, 250, 250));
                color: black;
                font-family: trebuchet ms;
            }
            h1 {
                color: #ff477e;
            }
            #yesButton, #no {
                color: black;
                padding: 10px 20px;
                font-size: 20px;
                background-color: rgb(247, 44, 91);
                border: none;
                border-radius: 5px;
                cursor: pointer;
                transition: transform 0.3s, width 0.3s, height 0.3s;
                white-space: nowrap;
            }
            #yesButton {
                background-color: rgb(64, 248, 64);
                margin-right: 10px;
            }
            #no {
                position: absolute;
                background-color: rgb(247, 44, 91);
                margin-left: 10px;
            }
            #message {
                display: none;
                font-size: 30px;
                font-weight: bold;
                color: #ff477e;
                margin-top: 20px;
                text-align: center;
            }
            .confetti {
                position: absolute;
                width: 10px;
                height: 10px;
                background-color: #ff477e;
                animation: fall linear infinite;
            }
            @keyframes fall {
                0% {
                    transform: translateY(-100vh);
                }
                100% {
                    transform: translateY(100vh);
                }
            }
        </style>
    </head>
    <body>
        <h1>Will you be my Valentine?</h1>
        <button id="yesButton">Yes</button>
        <button id="no">No</button>
        <div id="message">Yayyyy! Shall we schedule 14 March when you are back? 💖</div>
        <script>
            var currentIndex = 0;

            var noTexts = [
                "naurrrr?",
                "really naur?",
                "wait really naur?",
                "really really naur?",
                "really really really naur???",
                "ok wait gimme a chance",
                "please?",
                "pretty please?",
                "pretty please with a cherry on top?",
                "this is gonna be the last naur I coded so you have to click yes next",
                "ok I lied but this is really the last naur I coded",
                "why are you still clicking?",
                "please stop clicking",
                "please say yes :'(",
                ":C",
                "I'm not gonna code any more naurs",
                "really this time",
                "really really this time",
                "this is the last naur you get",
                "if you got this far, call me and tell me I'm a smelly poo poo",
                "ok stop",
                "WHYYYYY",
                "WHY DO YOU REJECT ME",
                "*CRY*",
                "Ok nowww can you please click yes?",
                "there's really no more no's after this",
                "last chance",
                "last last chance",
                "last last last chance",
                "if you click no one more time you've officially broken my heart",
                "REALLY?",
                "ok you won, no valentine's day :'C"
            ];

            var yesButton = document.getElementById("yesButton");
            var no = document.getElementById("no");
            var message = document.getElementById("message");

            // Event listener for the "Yes" button
            yesButton.addEventListener("click", function () {
                message.style.display = "block"; // Show the message
                startConfetti(); // Trigger the confetti effect
            });

            // Event listener for the "No" button
            no.addEventListener("click", change);

            function change() {
                // Check if the texts in the array are exhausted
                if (currentIndex < noTexts.length) {
                    no.innerText = noTexts[currentIndex];
                    currentIndex++;
                } else {
                    // Remove both buttons after all texts are exhausted
                    no.style.display = "none";
                    yesButton.style.display = "none";
                    message.style.display = "block"; // Show the message
                    message.innerText = "You have officially exhausted all 'No' texts. 😭"; // Change the final message
                }

                // Adjust button size to fit the text
                no.style.width = "auto";
                no.style.height = "auto";

                // Randomly reposition the "No" button
                if (currentIndex < noTexts.length) {
                    var i = Math.floor(Math.random() * (window.innerWidth - no.offsetWidth));
                    var j = Math.floor(Math.random() * (window.innerHeight - no.offsetHeight));
                    no.style.left = i + "px";
                    no.style.top = j + "px";
                }
            }

            // Function to start the confetti effect
            function startConfetti() {
                for (let i = 0; i < 100; i++) {
                    let confetti = document.createElement("div");
                    confetti.classList.add("confetti");

                    // Randomize confetti colors
                    confetti.style.backgroundColor =
                        ["#ff477e", "#64f840", "#ffa500", "#00d4ff"][Math.floor(Math.random() * 4)];

                    // Randomize position and animation speed
                    confetti.style.left = Math.random() * 100 + "vw";
                    confetti.style.animationDuration = Math.random() * 3 + 2 + "s";

                    document.body.appendChild(confetti);

                    // Remove confetti after the animation ends
                    confetti.addEventListener("animationend", function () {
                        confetti.remove();
                    });
                }
            }
        </script>
    </body>
</html>
