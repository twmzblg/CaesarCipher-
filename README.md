CaesarCipher++
Here is a simple text encryption/decryption mechanism (for printable ascii characters [#32-126]) that presumably is uncrackable without accurately guessing the password used. Without the correct password any 'decryption' could be accurate thereby defying certainty that it was accurately decrypted. I.e., it would be a waste of time and computing power to brute force it, as there would be infinite readable results.

Technique:
The password text will be repeated/cropped to match the length of the encryption/decryption text. Each character will be shifted by the distance from the password character at the same index.

Example: 
  text 'happy' [104, 97, 112, 112, 121] 
  with password '12345' [49, 50, 51, 52, 53]
  will shift to 'YbUWP' [89, 98, 85, 87, 80]

Following the formula with the first char 'h' [104], and first password '1' [49]:
  2 * 49 - 104 = -6 
  -6 + 95 = 89 // 'Y' [89]
  
The printable ascii characters are #32-126. If the result '-6' is less than 32, 95 will be added. If the result is greater than 126, 95 will be subtracted. This keeps the shifted result to printable ascii characters.

REQUIREMENTS:
- angular.js 1.6.9 (this single page app pulls it from https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js)
- w3-css v4 (if you care about responsivity of the page. Aka. not really 'required')
