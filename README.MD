# Password Generator

Simple but funny and flexible password generator.

---

###Features:

#####Password generation:

- It allows you to specify the character set:
  - by enabling/disabling character classes:
    - emojis (Using this charset:
      😀🤣🤑😐🥵🥶🤮🤯😷👻👾🤖🐵🙈🙉🙊🐕🦊
      🐢🐸🦈🐳🌞🌈🍒🍋🥝🍉🍌🍇🍩🥨🧁🥚🍺🍬
      🍫🍯🌭🌮🍔🥓🍕🍪🛹⚽🏀🏈🎳🏓🎱🎸🎨🥋
      🎮🎲🏇🍄🥑🍅🎉🔥💈💣⏰🎈🧸💾💡📷🔒💎)
    - uppercase ASCII letters `A-Z`
    - lowercase ASCII letters `a-z`
    - digits `0-9`
    - punctuation ```!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~```
    - space ` `
  - by adding custom characters
  - by blacklisting custom characters
- It allows you to specify any desired length of the password.
- It allows you to limit the maximum allowed number of occurrences of the same character, but still takes care that the password length can be reached.

#####Usage

- ######Interactive mode:

    Run the script without any arguments and you get to the interactive mode which looks like this example:

    ```
    $ ./pwgen.py
    ***** Password Generator - © 2016 ByteCommander *****

    The default character set to generate passwords is this (not including the arrows):
    → !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~⏰⚽🌈🌞🌭🌮🍄🍅🍇🍉🍋🍌🍒🍔🍕🍩🍪🍫🍬🍯🍺🎈🎉🎨🎮🎱🎲🎳🎸🏀🏇🏈🏓🐕🐢🐳🐵🐸👻👾💈💎💡💣💾📷🔒🔥😀😐😷🙈🙉🙊🛹🤑🤖🤣🤮🤯🥋🥑🥓🥚🥝🥨🥵🥶🦈🦊🧁🧸← 
    Do you want to change the character set? (y/N) y
    Do you want to allow emoji characters '😀🤣🤑😐🥵🥶🤮🤯😷👻👾🤖🐵🙈🙉🙊🐕🦊🐢🐸🦈🐳🌞🌈🍒🍋🥝🍉🍌🍇🍩🥨🧁🥚🍺🍬🍫🍯🌭🌮🍔🥓🍕🍪🛹⚽🏀🏈🎳🏓🎱🎸🎨🥋🎮🎲🏇🍄🥑🍅🎉🔥💈💣⏰🎈🧸💾💡📷🔒💎'? (Y/n) y
    Do you want to allow uppercase letters 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'? (Y/n) y
    Do you want to allow lowercase letters 'abcdefghijklmnopqrstuvwxyz'? (Y/n) y
    Do you want to allow digits '0123456789'? (Y/n) y
    Do you want to allow punctuation '!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~'? (Y/n) n
    Do you want to allow space ' '? (Y/n) n
    Please enter additional characters you want to allow (if any): -_
    Please enter characters you want to blacklist (if any): Xx0🍌💣
    The default password length is 12 characters.
    Enter your desired length or leave it blank to use the default: 20
    By default, there is no limit how often a character may appear in the password.
    Enter your desired maximum duplicate character limit or leave it blank to use the default.
    A value of 0 means no limit: 1
    And your new password is:
    +----------------------+
    | jJ-USo🍫Dig7🤖3eO2🦊REd |
    +----------------------+
    Generate another password with the same settings? (Y/n)
    And your new password is:
    +----------------------+
    | VZC😀KuQFI🐢HjqSB🍒gN9M |
    +----------------------+
    Generate another password with the same settings? (Y/n) n
    Thank you for using this password generator. Have a nice day!
    ```

- ######Command-line mode:

    Run the script with the command-line arguments described in its help (type `pwgen.py --help` or `pwgen.py -h` or see the block below) and you use it in command-line mode. This is useful to embed this tool into your own scripts, create your personal shortcuts for it or quickly launch it with a specific configuration.

    Help screen:

    ```
    $ ./pwgen.py -h
    usage: pwgen.py [-h] [-n AMOUNT] [-m LIMIT] [-e] [-q] [-u] [-l] [-d] [-p] [-s]
                    [-a ADDITIONAL] [-b BLACKLIST]
                    length

    usage: Highly customizable random password generator.
    🤖 Try the emoji mode to generate random emoji-passwords 🌈.

    positional arguments:
      length                length of the password to generate

    optional arguments:
      -h, --help            show this help message and exit
      -n AMOUNT, --amount AMOUNT
                            how many passwords to create
      -m LIMIT, --max-duplicate-chars LIMIT
                            limits how often the same character may occur in a
                            password at most
      -e, --emoji           Use the emoji mode to generate passwords with emojis 😍
      -q, --quiet           print only one password per line, nothing else

    Character set specification:
      -u, --uppercase       include uppercase letters A-Z into the available
                            character set
      -l, --lowercase       include lowercase letters a-z into the available
                            character set
      -d, --digits          include digits 0-9 into the available character set
      -p, --punctuation     include punctuation into the available character set
      -s, --space           include the standard space into the available
                            character set
      -a ADDITIONAL, --additional ADDITIONAL
                            additional characters to include into the available
                            character set
      -b BLACKLIST, --blacklist BLACKLIST
                            characters to exclude from the available character set

    Run it without any arguments for interactive mode.
    ```

    Example run:

    ```
    $ ./pwgen.py 10 -ulde -a'-_' -n6
    .----------------------------------------.
    | 🌈💪😷 Emoji Password Generator 🇮🇹💗🇻🇪 |
    | 🄯 2020 Chococoin Powered by Ethturin   |
    *----------------------------------------*

    Using this character set (excluding the arrows):
    →-0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ_abcdefghijklmnopqrstuvwxyz⏰⚽🌈🌞🌭🌮🍄🍅🍇🍉🍋🍌🍒🍔🍕🍩🍪🍫🍬🍯🍺🎈🎉🎨🎮🎱🎲🎳🎸🏀🏇🏈🏓🐕🐢🐳🐵🐸👻👾💈💎💡💣💾📷🔒🔥😀😐😷🙈🙉🙊🛹🤑🤖🤣🤮🤯🥋🥑🥓🥚🥝🥨🥵🥶🦈🦊🧁🧸←
    There are no duplicate character limits.

    Generating 6 passwords of length 10:

    🐢X6🙉🤯V3H🍄f
    U👾FA🥑8kF8p
    💎O5Z🎈iAb🔒👾
    0🎮hLU🙊q💎🙉🥨
    g🎲🍄e🐸M🤣⚽I🥨
    gcH🏀💾😷atv🌭
    ```

    A Project inspired by Password Generator © 2016 of ByteCommander [https://github.com/ByteCommander/PasswordGenerator]