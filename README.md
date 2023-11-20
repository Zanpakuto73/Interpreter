# Interpreter
Interpreter Programming Project
CSC 620 Programming Languages
Below is the syntax and semantics for a language that has a (possible empty) simple variable declaration secton followed by a single Boolean expression which is ended by a period. Write a program which prompts the user to input a file name which contains the Boolean expression or simply to input the string to be checked (indicate which input method you will use in your comments). You may assume that no input will be longer than 100 characters in length. Expressions may contain white spaces and white spaces should be considered to be delimiters (i.e. a white space between the − and > of the implication symbol would be a syntax error). The program should check if the input is of valid syntax and (if valid) compute the value of the expression. If syntactically valid, but the expression contains an undefined variable, it should give a runtime “undefinied variable” error rather than a syntax error. The output should either be an error message or a message that gives the value of the expression. You must use the techniques taught in the class - this is a recursive descent interpreter. Syntax: (note: for ∨ use the lowercase letter ”v” and for ∧ use the caret symbol)
                                          Selection Sets
(P) ::= (D)(B)                            {#, ~,T,F,var,(}
(D) ::= #var :=(V);(D)                        {#}
    ::= empty                              {~,T,F,var,(}
(V) ::= T                                      {T}
    ::= F                                      {F}
(B) ::= (IT) .                            {~,T,F,var,(}
(IT) ::= (OT) (IT_Tail)                   {~,T,F,var,(}
(IT_Tail) ::= -> (OT) (IT_Tail)               {->}
          ::= empty                          {.,)}
(OT) ::= (AT)(OT_Tail)                    {~,T,F,var,(}
(OT_Tail)::= v (AT) (OT_Tail)                  {v}
         ::= empty                          {->,.,)}
(AT) ::= (L)(AT_Tail)                      {~,T,F,var,(}
(AT_Tail) ::= ^ (L) (AT_Tail)                  {^}
          ::= empty                         {v,->,.,)}
(L) ::= (A)                                {T,F,var,(}
    ::= ~ (L)                                  {~}
(A) ::= T                                      {T}
    ::= F                                      {F}
    ::= var                                   {var}
    ::= ( (IT) )                               {(}

