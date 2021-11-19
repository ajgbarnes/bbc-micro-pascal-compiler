# Pascal For Human Beings

This is a manual rekeying of **Jeremy Ruston's** simple [Pascal](https://en.wikipedia.org/wiki/Pascal_%28programming_language%29) compiler in his book [Pascal for Human Beings](file:///C:/Users/Andrew/Downloads/Pascal-for-Human-Beings-1982.pdf) published in 1982.

The original copyright to the book and original code is Copyright (c) Jeremy Ruston, January 1982. But I imagine it's listed in the book with the intention that you type it in and learn from it.

- The compiler is a BASIC programme which is compatible with [BBC BASIC](https://en.wikipedia.org/wiki/BBC_BASIC).
- It contains data statements at the beginning from 1 to 999 - these are used to contain the Pascal program
- The compiler itself resides from 1000 to 4870
- It "compiles" or converts the Pascal code into BBC BASIC compitable code
- The code is not written to a file, just written to the screen

## Restrictions 

It's based on Pascal as it was in 1982 (!) and will convert most Pascal programs of that era into an equivalent BASIC program.  The book lists these limitations:

1. No user defined functions or procedures
2. No user defined data types
3. No sets
4. No arrays/matrices
5. No true integer arithmetic
6. No numerical output formatting
7. No file handling
8. No nest 'IF-THEN' statements
9. No more than one statemetn is allowed the 'THEN' section of an 'IF' statement
10. No spaces are allowed in expressions. Brackets can always be used to make up for this shortcoming.
11. The layout of VAR and CONST section sof a program is crucial, see example program
12. The colon in a  VAR section, the equals sign in a CONST section and the ':=' symbols in an assignment must all be flanked by spaces
13. Very little syntax checking is carried out - you can write an incorrect Pascal program, and the compiler will not tell you, but the error routines in the BASIC interpreter which executes the compiled BASIC program should do
14. The compiler outputs to the screen only, so you need a means to capture the output
15. No case statement
16. Variable names are limited to those accepted by the version of BASIC you are using
17. Notice BEGIN and END are obligatory in WHILE and FOR loops

## Observations

1. The compiler relies heavily on GOTO and GOSUB statements rather than procedures - would be easy to convert and make it a little more understandable
2. It's actually pretty straight forwared to see what it's doing, Jeremy took time to comment the code with REM statements back in the day
3. The code is described in detail on (book) pages 57 - 64 of [Pascal for Human Beings](https://archive.org/download/pascal-for-human-beings/Pascal-for-Human-Beings-1982.pdf)
4. Takes about 20 seconds to complete on a BBC Model B and almost instant on a modern computer


## Running the Code

You can use the compiler.bbc file to generate basic code using a [real BBC Micro](https://en.wikipedia.org/wiki/BBC_Micro), an emulator such as [BeebEm](http://www.mkw.me.uk/beebem/), [beebjit](https://github.com/scarybeasts/beebjit), [B-Em](https://github.com/stardot/b-em (or many others) or a [native BBC BASIC implementation for a modern operating system](https://www.bbcbasic.co.uk/bbcbasic.html)

The [compiler.bbc](https://github.com/ajgbarnes/bbc-micro-pascal-compiler/blob/master/compiler.bbc) and [basic.bbc](https://github.com/ajgbarnes/bbc-micro-pascal-compiler/blob/master/basic.bbc) are pre-tokenised BBC BASIC files that can be loaded into e.g. the [native BBC BASIC tools](https://www.bbcbasic.co.uk/bbcbasic.html)

The [compiler.txt](https://github.com/ajgbarnes/bbc-micro-pascal-compiler/blob/master/compier.txt) and [basic.txt](https://github.com/ajgbarnes/bbc-micro-pascal-compiler/blob/master/basic.txt)] files are untokenised and raw text files. These can be cut and paste in any tool or migrated into an appropriate operating system (not just BBC BASIC).

The [pascal.ssd](https://github.com/ajgbarnes/bbc-micro-pascal-compiler/blob/master/pascal.ssd) file can be loaded into any BBC Micro Emulator and the compiler executed with '''CHAIN "COMPILE"''.  The compiled output is also pre-stored and can be run with '''CHAIN "BASIC"'''

