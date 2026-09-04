# Theory of Computation 7 - 10 marks

* Scoring subject

## DFA

* The problems faced in real worlds that can be solved using a computer are called as decidable problems.
  * Algorithm Exists
* The problems that cannot be solved using the computer are called undecidable problem
  * Algorithm does not exists
* It is the study of automata and formal languages
    * Finite Automata -> Regular Languages
    * Push down Automata -> Context free languages
    * Linear bounded automata -> Context sensitive Languages
    * Turing Machine -> Recursive Enumerable languages

### Terminologies

* Alphabet(∑) -> Finite non-empty set of symbols
  * Ex: {a, b}, {a, 1, 2}
* String -> Finite sequence of symbols over the given alphabet ∑, ε is a valid 0 length string
  * Ex: Given {a, b} -> ab, aaba, ababab
* Formal Language -> Any set of strings over the given alphabet ∑.
  * Ex: Given {a, b} Language = {aa, aba, abbba, baba, ε}
  * If the set of sentences are finite, then it is called as finite language. If the set of sentences are infinite, then it is called as a infinite language. If the set is empty, then it is called as empty language.
* Complete Language: An infinite language, having all possible strings that can be constructed using the alphabet, including ε.
  * Ex: Given {a, b} -> {ε, a, b, ab, aab, ....}