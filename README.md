<!doctype html>
<html>
  <head>
    <title>Cipher Example</title>
    <script type="text/javascript">

      /**
       * This function is called when the encrypt button is pressed. It loops over the
       * letters of the ciphertext and tries to encrypt them by calling encrypt_character.
       */
      function encrypt() {
        var input = plaintext.value.toUpperCase();
        var myAdder = parseInt(adder.value);
        var myMultiplier = parseInt(multiplier.value);

        var output = "";
        for (var i = 0; i < input.length; i = i + 1) {
          // WORK:
          // Call encrypt_character with the arguments input[i], myAdder, myMultiplier
          // and concatenate the returned value to output.

        }
        ciphertext.value = output;
      }

      /**
       * Given a character, an adder, and a multiplier, *encrypt* the character using
       * the adder and the multiplier. E.g.,
       *
       * encrypt_character("B", 3, 9) should return "E" since
       * . "B" -> 1 as a plaintext character,
       * . 1 * 3 = 3
       * . 3 + 9 = 12
       * . 12 % 26 = 12
       * . 12 -> "M"
       *
       * Note that this differs from decrypt_character in the order of operations performed!
       */
      function encrypt_character(character, myAdder, myMultiplier) {
        if (!isAlpha(character)) {
          return character;
        }
        var transformedCharCode = -1;
        // WORK:
        // Encrypt the character. Remember that "A" -> 65 in ASCII, so you'll first need to subtract
        // characterToNumber("A") and then add it back in before calling numberToCharacter.

        return numberToCharacter(transformedCharCode);
      }

      /**
       * This function is called when the decrypt button is pressed. It loops over the
       * letters of the ciphertext and tries to decrypt them by calling decrypt_character.
       */
      function decrypt() {
        var input = ciphertext.value.toUpperCase();
        var myAdder = parseInt(adder.value);
        var myMultiplier = parseInt(multiplier.value);

        var output = "";
        for (var i = 0; i < input.length; i = i + 1) {
          // WORK:
          // Call decrypt_character with the arguments input[i], myAdder, myMultiplier
          // and concatenate the returned value to output.

        }
        plaintext.value = output;
      }

      /**
       * Given a character, an adder, and a multiplier, *decrypt* the character using
       * the adder and the multiplier. E.g.,
       *
       * decrypt_character("B", 3, 9) should return "E" since
       * . "B" -> 1 as a plaintext character,
       * . 1 + 9 = 10
       * . 10 * 3 = 30
       * . 30 % 26 = 4
       * . 4 -> "Y"
       *
       * Note that this differs from encrypt_character in the order of operations performed!
       */
      function decrypt_character(character, myAdder, myMultiplier) {
        if (!isAlpha(character)) {
          return character;
        }
        var transformedCharCode = -1;
        // WORK:
        // Encrypt the character. Remember that "A" -> 65 in ASCII, so you'll first need to subtract
        // characterToNumber("A") and then add it back in before calling numberToCharacter.

        return numberToCharacter(transformedCharCode);
      }

      /**
       * This function replaces a multiplier and adder with their *inverses*. Remember,
       * . The inverse of an adder is the number x such that (adder + x) % 26 == 0
       * . The inverse of a multiplier is the number y such that (multiplier * y) % 26 == 1.
       *
       * In this function, you should loop over all the numbers between 0 and 26 and see if they
       * are the inverse of adder or multiplier. If so, you should set inverseAdder or
       * inverseMultiplier as appropriate.
       */
      function invert() {
        var myAdder = parseInt(adder.value);
        var myMultiplier = parseInt(multiplier.value);
        var inverseAdder = -1;
        var inverseMultiplier = -1;

        // WORK:
        // LOOP OVER THE NUMBERS BETWEEN 0 and 26 here. Once you find the number x such that
        // (myAdder + x) % 26 == 0, set myAdder = x
        //
        // Ditto, when you find the number y such that
        // (myMultiplier * y) % 26 == 1, set myMultiplier = y

        adder.value = inverseAdder;
        multiplier.value = inverseMultiplier;
      }

      /**
       * Returns true if character is a letter between A and Z
       */
      function isAlpha(character) {
        return character >= "A" && character <= "Z";
      }

      /**
       * Turns a character into its ASCII representation. E.g., A -> 65.
       */
      function characterToNumber(character) {
        return character.charCodeAt(0);
      }

      /**
       * Turns a number into the character it represents in ASCII, e.g., 65 -> "A".
       */
      function numberToCharacter(num) {
        return String.fromCharCode(num);
      }

    </script>
  </head>
  <body>
    <h1>ENCRYPTOR!!</h1>
    <h3>Rhymes with TROGDOR!!</h3>
    <p>Instructions
    </p><ol>
      <li>Input a multiplier, i.e., a positive number coprime to 26.</li>
      <li>Input an adder, i.e., a nonnegative number.</li>
      <li>If you want to <i>encrypt</i> text, put the text in the Plaintext box and hit Encrypt.</li>
      <li>If you want to <i>decrypt</i> text, put the text in the Ciphertext box and hit Decrypt.</li>
      <li>If you want to <i>invert</i> the adder and multiplier, click Invert.</li>
    </ol>
    <table>
      <tr><td>Multiplier</td><td><input type="number" id="multiplier"></td></tr>
      <tr><td>Adder     </td><td><input type="number" id="adder"></td></tr>
      <tr><td>Plaintext </td><td><input type="text" id="plaintext"></td></tr>
      <tr><td>Ciphertext</td><td><input type="text" id="ciphertext"></td></tr>
      <tr><td><button onclick="encrypt();">Encrypt</button></td><td><button onclick="decrypt();">Decrypt</button></td></tr>
      <tr><td><button onclick="invert();">Invert</button></td><td></td></tr>
    </table>

  </body>
</html>
