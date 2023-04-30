Download Link: https://assignmentchef.com/product/solved-csc446-mini-java-compiler-assignment-1
<br>
This project consists of writing a Lexical Analyzer for a subset of the Java programming language.  The Lexical Analyzer is to be a module written in the high level language of your choice that exports the following:




procedure GetNextToken

global variables             Token

Lexeme

Value               {for integer tokens}

ValueR            {for real tokens}

Literal              {for quoted strings}




The following are the reserved words in the language (all are case sensitive):




class, public, static, void, main, String, extends, return, int,

boolean, if, else, while, System.out.println, length, true,

false, this, new.




The notation for specifying tokens is as follows:




Comments begin with the symbol // and continue to the end of the line or are delimited by /* and */ and may not be nested.  Comments may appear after any token.




Blanks between tokens are optional, with the exception of reserved words.  Reserved words must be separated by blanks, newlines, the beginning of the program or the final semicolon.




Token idt for identifiers matches a letter followed by letters, underscore and/or digits having a maximum length of 31 characters.  Java identifiers are case sensitive.




letter                -&gt; [‘a’-‘z’,’A’-‘Z’]

digit                 -&gt; [‘0’-‘9’]

underscore       -&gt; ’ _’

idt                    -&gt; letter(letter | digit | underscore )*







Token numt matches unsigned integers or real numbers and has attribute Value for integers and ValueR for real numbers.




digits                        -&gt; digit digit*

optional_fraction      -&gt; . digits |   e

num                          -&gt; digits optional_fraction




String literals begin with a “ and end with a “ and should be stored in the literal variable.  Strings must begin and end on the same line.




The relational operators (Token relop) are:




= =, !=, &lt;, &lt;= ,&gt;, &gt;=




The addop’s are: +, -, and ||




The mulop’s are: *, /,  and &amp;&amp;.




The assignop is:  =




The following symbols are also allowed in the language:




( ) { } ,  ; . “ [ ]

<u>A sample Java subset program looks like this:</u>

class factorial {

public static void main (String[] a) {

System.out.println(new Fac().ComputeFac(10));

}

}

class Fac{

public int ComputeFac(int num) {

int num_aux;

if (num &lt; 1)

num_aux=1;

else

num_aux= num * (this.ComputeFac(num-1));

return num_aux;

}

}

The tokens for each possible symbol (or type of symbol) should be defined using an enumerated data type.




To test your project write a short program that imports (uses) module LexicalAnalyzer to read a source program and output the tokens encountered and the associated attributes (lexeme for identifiers and reserved words, the numeric value for token num, and the symbol itself for all others).




Source code for this and all other assignment must be submitted in a single zip file to the appropriate D2L dropbox on or before the due date. In class you are to submit a high quality (laser or ink jet) printed copy of your assignment. The printed copy must print two pages per sheet as shown in the following example:





