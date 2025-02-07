<!DOCTYPE html>
<html>
    <head>
        <title>Valentine's Day Proposal</title>
    </head>
    <body>
        <div>
            <br />
            <br />
            <br />
            <br />
            <br />
            <br />
            <h1>Will you be my Valentine?</h1>
            <p style="font-family: trebuchet ms; color: black;">
                <img
                    id="valentineImage"
                    src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAoHCBIVFRgWFRUYGBUaGBEYGBgYGBgYERgSGBgZGRgYGBgcIS4lHB4rHxgYJjgmKy8xNTU1GiQ7QDs0Py40NTQBDAwMEA8QHBISGjQhISE0NDQ0NDQxNDQ0NDQ0NDQ0MTQ0NDQ0NDU0NDQ0MTE0NDQ0NDQ0NDQ0NDExNDQxNP/AABEIANQA7gMBIgACEQEDEQH/xAAcAAABBQEBAQAAAAAAAAAAAA... (truncated for brevity)"
                    alt="Valentine's Day Image"
                    style="max-width: 300px; height: auto;"
                />
            </p>
            <br />
            <br />
            <br />
            <button id="yesButton">Yes</button>
            <button id="no">No</button>
        </div>
        <style>
            body {
                background: linear-gradient(to top, rgb(103, 216, 254), rgb(250, 250, 250));
                color: black; /* Default text color */
            }
            div {
                text-align: center;
                vertical-align: middle;
            }
            h1 {
                color: #ff477e; /* Keep pink color for the headline */
            }
            #yesButton, #no {
                color: black; /* Black text for buttons */
                padding: 10px 20px; /* Adjust padding for better spacing */
                font-family: trebuchet ms;
                font-size: 20px; /* Default font size */
                background-color: rgb(247, 44, 91); /* Default background */
                border: none;
                border-radius: 5px;
                cursor: pointer;
                transition: transform 0.3s, width 0.3s, height 0.3s;
                white-space: nowrap; /* Prevent text wrapping */
            }
            #yesButton {
                background-color: rgb(64, 248, 64); /* Green for Yes button */
                margin-right: 10px;
            }
            #no {
                position: absolute;
                background-color: rgb(247, 44, 91); /* Red for No button */
                margin-left: 10px;
            }
        </style>
        <script>
            // Add an index to track the current position in the noTexts array
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

            // Event listener for the "Yes" button
            yesButton.addEventListener("click", showAlert);

            function showAlert() {
                alert("yayyyy shall we schedule 14 March when you are back? <3 <3 <3");
            }

            // Event listener for the "No" button
            no.addEventListener("click", change);

            function change() {
                // Get the current text and update the button
                var randomText = noTexts[currentIndex];
                no.innerText = randomText;

                // Increment the index and wrap around if at the end of the array
                currentIndex = (currentIndex + 1) % noTexts.length;

                // Adjust button size to fit the text
                no.style.width = "auto";
                no.style.height = "auto";

                // Randomly reposition the "No" button
                var i = Math.floor(Math.random() * (window.innerWidth - no.offsetWidth));
                var j = Math.floor(Math.random() * (window.innerHeight - no.offsetHeight));
                no.style.left = i + "px";
                no.style.top = j + "px";
            }
        </script>
    </body>
</html>
