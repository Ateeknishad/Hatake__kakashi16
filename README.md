<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
        <style>
            /* Use the image from the URL as the background and set text color to white */
            body {
                background-image: url('https://i.postimg.cc/0MsktC0j/image.jpg');
                background-size: cover; /* This makes the image cover the entire background */
                background-repeat: no-repeat; /* This prevents the image from repeating */
                background-position: center; /* This centers the background image */
                color: white; /* Set text color to white */
                font-family: Arial, sans-serif; /* Set a simple font */
            }

            .button {
                background-color: #4CAF50; /* Green background */
                border: none; /* Remove border */
                color: white; /* White text */
                padding: 10px 20px; /* Some padding */
                text-align: center; /* Centered text */
                text-decoration: none; /* Remove underline */
                display: inline-block; /* Make the link look like a button */
                font-size: 16px; /* Increase font size */
                margin: 10px 5px; /* Add some space around buttons */
                cursor: pointer; /* Add a pointer on hover */
            }

            .dislike-button {
                background-color: #f44336; /* Red background */
            }

            .comment-section {
                margin-top: 20px;
            }

            textarea {
                width: 100%;
                padding: 10px;
                margin-top: 10px;
                border: none;
                border-radius: 5px;
            }

            .submit-button {
                background-color: #008CBA; /* Blue background */
            }

            .counter {
                margin-left: 10px;
                font-size: 18px;
                vertical-align: middle;
            }

            .comments {
                margin-top: 10px;
            }
        </style>
    </head>
    <body>
        <h1>Welcome to the Kakashi Insta Web</h1>
        <h1>Name</h1>
        <h1>Sharingan Kakashi</h1>
        <h2>Username: hatake__kakashi16</h2>
        <p>0 posts | 92 followers | 2 following <br> Bio:<br>
        "🌪️ Lord Sixth Hokage<br>
        🎭 Masked wisdom, hidden scars<br>
        📚 Leaf’s Protector | Copy Ninja<br>
        💫 Mentor, leader, legend<br>
        💪 Strength from pain<br>
        🌌 Calm in chaos<br></p>

        <!-- Instagram link -->
        <p><a href="https://www.instagram.com/hatake__kakashi16/" target="_blank" style="color: white;">Visit my Instagram Profile</a></p>
        
        <!-- Image -->
        <img src="https://i.postimg.cc/dhP5dkN0/kakashi.jpg" alt="Kakashi Image" style="width:190px;">

        <!-- Like and Dislike buttons with counters -->
        <div>
            <button class="button" id="likeButton" onclick="increaseLike()">Like</button>
            <span id="likeCount" class="counter">0</span>
            <button class="button dislike-button" id="dislikeButton" onclick="increaseDislike()">Dislike</button>
            <span id="dislikeCount" class="counter">0</span>
        </div>

        <!-- Comment section -->
        <div class="comment-section">
            <h3>Leave a Comment:</h3>
            <textarea id="commentText" rows="4" placeholder="Write your comment here..."></textarea>
            <button class="button submit-button" id="submitButton" onclick="submitComment()">Submit</button>
            <p><span id="commentCount">0</span> comments</p>
        </div>

        <!-- Displayed Comments -->
        <div class="comments" id="comments"></div>

        <p>Thanks for visiting!</p>

        <script>
            var likeCount = 0;
            var dislikeCount = 0;
            var commentCount = 0;
            var likeClicked = false;
            var commentSubmitted = false;

            function increaseLike() {
                if (!likeClicked) {
                    likeCount++;
                    document.getElementById("likeCount").innerText = likeCount;
                    likeClicked = true;
                    document.getElementById("likeButton").disabled = true;
                    document.getElementById("dislikeButton").disabled = true;
                }
            }

            function increaseDislike() {
                if (!likeClicked) {
                    dislikeCount++;
                    document.getElementById("dislikeCount").innerText = dislikeCount;
                    likeClicked = true;
                    document.getElementById("likeButton").disabled = true;
                    document.getElementById("dislikeButton").disabled = true;
                }
            }

            function submitComment() {
                if (!commentSubmitted) {
                    var commentText = document.getElementById("commentText").value.trim();
                    if (commentText !== "") {
                        commentCount++;
                        document.getElementById("commentCount").innerText = commentCount;
                        var commentsDiv = document.getElementById("comments");
                        var newComment = document.createElement("p");
                        newComment.textContent = commentText;
                        commentsDiv.appendChild(newComment);
                        document.getElementById("commentText").value = ""; // Clear the textarea
                        commentSubmitted = true;
                        document.getElementById("commentText").disabled = true;
                        document.getElementById("submitButton").disabled = true;
                    }
                }
            }
        </script>
    </body>
</html>
