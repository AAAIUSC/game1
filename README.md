# Game 1

1. To send a request to the server, you send a post request to http://www.aaaiusc.com/games/game1.php

  1. First send a post request with your email parameter to add your email to our server. You will get a output where you can parse to get the number of digits

    * curl --data "email=yourEmail@something.com" http://www.aaaiusc.com/games/game1.php

  2. Afterwards, you can send a request with an email and an answer parameter. Each request will add a point to your score.

    * curl --data "email=yourEmail@something.com&answer=123456" http://www.aaaiusc.com/games/game1.php

2. Based on the number of digits returned(6, 7, or 8), you try to guess the number stored in the server. The number is made up of characters from 0-9 as the digits, no repeating characters. For example, for 6 digits, 093658 is a valid number, but 101234 is not as there is a repeating number of a 1. Based on your guess, you will get an output in the format (a,b)

  1. a is the number of characters you have guessed correctly in the exact position. If 5123097 is the number associated with your email and you guess 1623907, you will get an a of 3, since 2, 3, and 7 are in the correct positions. b is the number of characters you guess that match the true number, but in the incorrect position. So in he previous example, b would be 3, since 1, 0, and 9 are in the incorrect positions but are in both numbers.

  2. Invalid comparisons will result an error output rather than something in the form (a,b). Each time you guess exactly correctly, you will get a new number associated with your email in your database. That will output a different number of digits.

3. Based on the number of guesses you guessed, you will get a score. The more guesses you needed before you guessed correctly, the higher your score. The lower your score, the better.

  * Winners will have a higher seeding for the next game and will have a better opportunity for prizes.

  * Check the python script for sample code
