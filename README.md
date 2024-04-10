A/	The full name of the developers (teammates of the team) and the contribution of each to the developed program.

1) Pillay Vythilingum Darshini - Log In, Sign Up, CSS, testing, and file integration.

2) Chiu Lim Mike Jun Yang - Completed Ajax mainly and contributed to database integration with Ajax.

3) Jia Changru - Successfully designed the whole game with the codes.

4) Sun Wentao - Ensured website functionality, file integration, and game history.

5) Tran Ba Minh Huy - Developed the whole database, integrated files, conducted testing, and managed GitHub

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
B/	The game's release date : 09/04/2024

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
C/ 	Enumeration and description of all features of the Website (see section 1), including additional features added

There are 13 files: Edit, LogIn, LogOut, Redirect, SignUp, audio, image, template, Game.php, 
Index.php, game_history.php, style.css, style2.css

1/ Edit :

2/ LogIn :

3/ LogOut :

4/ Redirect :

5/ SignUp :

6/ audio :

7/ image :

8/ template :

9/ Game.php :

10/ Index.php :

11/ game_history.php :

12/ style.css :

13/ style2.css:




Ajax Part: 

Real-time validation of information entered by the user in the user account creation form with AJAX. 

Accessing the AJAX JavaScript file 

/*
<script language="javascript" src="fname-ajax.js"></script> 

<label for="firstname">First Name:</label> 

        <input id="firstname" type="text" name="firstname"  onkeyup="validateFName()" required> 

        <span id="firstname-error"></span> 
*/
 

In the first name input field, onkeyup="validateFName()" will access the function situated in the JavaScript file.  

JavaScript file (fname-ajax.js) for first name validation 

/*

function validateFName(){ 

    var firstNameInput = document.getElementById("firstname"); 

    var firstName = firstNameInput.value; 

    var xmlhttp = new XMLHttpRequest(); 
 
    xmlhttp.open("POST", "flname-ajax.php", true); 

    xmlhttp.setRequestHeader("Content-Type", "application/x-www-form-urlencoded"); 

    xmlhttp.onreadystatechange = function() { 

        if (xmlhttp.readyState == 4 && xmlhttp.status == 200) { 

            // Update the error message span with the response 

            document.getElementById("firstname-error").innerText = xmlhttp.responseText; 

        } 

    }; 

    // Send the AJAX request with the username data 

    xmlhttp.send("firstname=" + firstName); 

} 
*/
 

By taking the input form the same id from the index.html file document.getElementById("firstname");  

i. The function will create an XMLHttpRequest object 

ii. Send the request off to a php file (flname-ajax.php) on the server.  

/*

if (xmlhttp.readyState == 4 && xmlhttp.status == 200) { 

            // Update the error message span with the response 

            document.getElementById("firstname-error").innerText = xmlhttp.responseText; 

 */

if the xmlhttp.readyState == 4, the request is finished and response is ready AND if the xmlhttp.status == 200, the status is ok, thus will display the error message next to the input field.  

PHP AJAX file (flname-ajax.php) 

/*

<?php 

if(isset($_POST['firstname'])){ 

    $firstname= $_POST['firstname']; 

    //$firstname = "abcd"; 

    // Perform validation (e.g., check if username already exists in the database) 

    // For demonstration purposes, let's assume a simple validation 

    if(!preg_match("/[a-zA-Z]/", $firstname)){ 

        echo "Must start with a letter a-z or A-Z"; 

    } else { 

        // Username is valid 

        echo ""; // Empty string means no error 

    } 

} 

 */

The $_POST will collect the value from the input’s name: “firstname”. Then we will use Regular Expression to check the element in the $firstname variable. 
If !preg_match, meaning if it doesn’t match the regex, a string message will be displayed.  

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
D/ 	How the game works, such as the description of levels and the number of lives allocated.

Game Description and Mechanics 

Levels: The game consists of 6 levels, each with a unique challenge based on sorting or identifying elements 
within a sequence. Levels transition from working with letters to numbers as the player progresses. 

Challenges by Level: 

Level 1 & 2: Sort letters in ascending (A to Z) or descending (Z to A) order. 

Level 3 & 4: Sort numbers in ascending or descending order. 

Level 5 & 6: Identify the first (smallest) and last (largest) elements in a sequence of letters or numbers. 

Lives: Players start with 6 lives. Each incorrect answer reduces the life count by 1. 
The game ends when a player exhausts all lives. 

Winning Condition: Successfully completing all 6 levels results in winning the game. 
If a player loses all lives before completing all levels, they lose the game. 

Game Status: Can be 'active', 'incomplete', or 'gameOver'. 
The game starts in an active state and changes based on the player's actions or outcomes. 

Technical Details 

Programming Language: The game is developed using PHP, evident from the PHP code snippets 
and server-side logic handling sessions, user inputs, and game progress. 

Session Management: PHP sessions are used to track the game state, including current level, lives remaining, 
game status, and the current sequence to sort or identify. 

Random Sequence Generation: 
A function generateRandomSequence generates a random sequence of numbers or letters, depending on the level. 
This function showcases the use of basic PHP functions like rand, range, shuffle, and array manipulations. 

Form Handling: 
The game uses HTML forms to capture user input, with PHP processing the submitted data to determine game progress. 

Outcome Recording: 
The game includes a simple mechanism to display outcomes to the player using echo statements within the PHP code. 

Database Management System (DBMS): 
The provided code does not explicitly mention or utilize a DBMS for storing or retrieving game data. 
All game state management is handled through PHP sessions, which are stored on the server temporarily. 

Version Information: 
The exact versions of PHP used and other software details are not specified in the provided code. 
Typically, PHP 7.x or higher is required for session management features and newer array functions. 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
E/      5.	Any other relevant technical information on the programme developed, including the programming languages and 
database management system used, their version and other relevant information.  
