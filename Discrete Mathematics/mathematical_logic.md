# Discrete Mathematics 8-10 marks

## Introduction to Discrete Mathematics

* Mathematical Logic 2-4 marks
    * Predicate Logic
    * Propositional Logic

### Mathematical Logic

* It gives us power to check the validity of a statement.
* We use only Factual / Propositional Statements in Mathematical Logic.
* A Compound Statement, can be broken down to more than 1 propositional statements
    * Ex: X >= 3; which can also be written as X > 3 or X = 3

* There are words called as connectives that connect 1 or more propositional statements, they consist of Conjunctions, Disjunctions, Single Implication, and double implications.

* Modifier / Negater (~): These words modify the statements.

* Conjunctions :
    * AND/BUT (^) : <table><tr><th>p</th><th>q</th><th>p^q</th></tr>
                    <tr><td>T</td><td>T</td><td>T</td></tr>
                    <tr><td>T</td><td>F</td><td>F</td></tr>
                    <tr><td>F</td><td>T</td><td>F</td></tr>
                    <tr><td>F</td><td>F</td><td>F</td></tr></table>

* Disjunctions :
    * OR (v) : <table><tr><th>p</th><th>q</th><th>pvq</th></tr>
                <tr><td>T</td><td>T</td><td>T</td></tr>
                <tr><td>T</td><td>F</td><td>T</td></tr>
                <tr><td>F</td><td>T</td><td>T</td></tr>
                <tr><td>F</td><td>F</td><td>F</td></tr></table>

* Single Implication :
    * IMPLIES (->) :<table><tr><th>p</th><th>q</th><th>p->q</th></tr>
                    <tr><td>T</td><td>T</td><td>T</td></tr>
                    <tr><td>T</td><td>F</td><td>F</td></tr>
                    <tr><td>F</td><td>T</td><td>T</td></tr>
                    <tr><td>F</td><td>F</td><td>T</td></tr></table>


    if a -> b

    * Converse = b -> a
    * Inverse = ~a -> ~b
    * Contrapositive = ~b -> ~a

* Double implication (Biconditional) : a <-> b
    * (a -> b) ^ (b -> a) : <table><tr><th>a</th><th>b</th><th>a<->b</th></tr>
                    <tr><td>T</td><td>T</td><td>T</td></tr>
                    <tr><td>T</td><td>F</td><td>F</td></tr>
                    <tr><td>F</td><td>T</td><td>F</td></tr>
                    <tr><td>F</td><td>F</td><td>T</td></tr></table>

* If in any expression there is at least 1 true statement, then it is called as a Satisfiable expression

* If all statements in an expression are true, then it is called as a Tautology / Valid.

* If all statements in an expression are false, then it is called as a Contradiction / Fallacy.

* If not all statements are true and not all of them are false, then the statement is a Contingency

* All Satisfiable expressions are not Contingency

#### Type - 1

* Refer Mathematical logic part 1 : 1:35:00. (Amazing logic, beautifully explained!)

#### Type - 2 (Logical Equivalence) ≡

* a->b ≡ ~b->~a : If the expression holds true when LHS and RHS are true, and false when LHS and RHS are false, then it is said that the expression holds logical equivalence.

* If A ≡ B, then A <-> B will always be tautology.

* P ^ P ≡ P
* P v P ≡ P
* P ^ F ≡ F
* P v T ≡ T
* P ^ T ≡ P
* P v F ≡ P
* P v Q ≡ Q v P
* P ^ Q ≡ Q ^ P
* a v (b v c) ≡ (a v b) v c
* a ^ (b ^ c) ≡ (a ^ b) ^ c
* a ^ (b v c) ≡ (a ^ b) v (a ^ c)
* a v (b ^ c) ≡ (a v b) ^ (a v c)

* Absorption Law:
    * a v (a ^ b) ≡ a
    * a ^ (a v b) ≡ a

* De Morgan's laws
    * ~(p ^ q) ≡ ~p v ~q
    * ~(p v q) ≡ ~p ^ ~q

* Negation laws
    * p v ~p ≡ T
    * p ^ ~p ≡ F

* God's law
    * a -> b ≡ ~b -> ~a
    * a -> b ≡ ~a v b
    
    * Example (a -> b) ^ (a -> c) ≡ a -> (b ^ c)
    * Example (a -> c) ^ (b -> c) ≡ (a v b) -> c

#### Tips

1. To tackle large expressions take common terms out.
2. If there are no common terms, use the DeMorgan's law to take negations inside and then take out common terms
3. As soon as common terms are out, use absorption laws to reduce the expressions.

