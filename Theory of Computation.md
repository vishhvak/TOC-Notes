# 	Theory of Computation

## 	Automata: The Methods and the Madness

**Automata** - a machine which performs a range of functions according to a predetermined set of coded instructions.  

Automata theory is the study of abstract computing devices, or "machines".

Finite Automata - Simpler kinds of machines in the 1940s and 1950s.			

### 									**The Central Concepts of Automata Theory**

**Alphabet**

> ***An alphabet is a finite nonempty set of symbols.*** 

Conventionally, we use the symbol Σ for an alphabet.  

Common alphabets include -

- ​     ∑={0,1} - The binary alphabet.
- ​    ∑={a,b,c....,z} - The set of all lower case letters

**String**

A String  or sometimes word  is a finite sequence of symbols chosen from some alphabet. 
For example 01101 is a string from the binary alphabet `∑=`{0,1}

The empty string is the string with zero occurences of symbols. This string, denoted by ε, is a string that maybe chosen from any alphabet whatsoever.

**Length of a String** - number of positions for symbols in the string. For instance, 01101 has length 5. It is common to say that the length of a string is "the number of symbols" in the string; this statement is colloquially accepted but not strictly correct.

> ***Standard notation for the length of a string w is |w|.*** 

For example, |011|=3 &|ε|=0.

**Powers of an alphabet:**

If Σ is an alphabet, we can express the set of all strings of a certain length from that alphabet by using an exponential notation. 

We define (Σ)^k^ to be the set of strings of length k, each of whose symbols is in Σ.

Ex - (Σ)^0^ = {ε}, regardless of what alphabet Σ is. ε is the only string whose length is 0.

If Σ={0,1}, Σ^2^ = {00,01,10,11}, Σ^3^ = {000,001,010,011,100,101,110,111} and so on. 

The set of all strings over an alphabet Σ is denoted by Σ^*^. For instance,

> ​					**Σ={0,1} => Σ^*^ = {ε,0,1,00,01,10,11,000,…}** 
>

> i.e 					**Σ^*^= Σ^0^ U Σ^1^ U Σ^2^ U ...**   			
>

Sometimes we exclude the empty string from the set of strings. The set of nonempty strings from alphabet Σ is denoted by Σ^+^. Thus, two appropriate equivalences are -

> ​							**Σ^+^ = Σ^1^ U Σ^2^ U Σ^3^ ….**							

> ​							**Σ^*^ = Σ^+^ U {ε}** 

**Concatenation of Strings**

Let **x** and **y** be strings. **xy** denotes the concatenation of **x** and **y**, that is the string formed by making a copy of **x** and following it a copy of **y**. More precisely, if **x** is the string composed of **i** symbols

 **x = a~1~ a~2~ a~3~ … a~i~** and **y** is the string composed of **j** symbols **y =  b~1~ b~2~ b~3~ … b~j~** ,
then **xy** is the string of length **i+j** : **xy = a~1~ a~2~ a~3~ … a~i~ b~1~ b~2~ b~3~ … b~j~** .

*<u>ε is the identity for concatenation</u>*, since when concatenated with any string it yields the other string as a result (analogous to 0 for addition). For any string *w*, ε*w* = *wε* = *w* hold.

**Reverse of Strings**

**Languages**

> **A set of strings all of which are chosen from some Σ^*^ , where Σ is a particular alphabet, is called a language.**
>

If Σ is an alphabet, and L $\subseteq$ Σ^*^, then L is a language over Σ. A language over Σ need not include strings with all the symbols of Σ, so once we have established that L is a language over Σ, we also know that it is a language over any alphabet that is a superset of Σ. 

Common languages can be viewed as **sets of strings.** 

An example is **English**, where the colelction of legal English words is a set of strings over the alphabet that consist of collection of legal English words is a set of strings over the alphabet that consists of all the letters. 

Another example is C, or any other **programming language**, where the legal programs are a subset of the possible strings that can be formed from the alphabet of the language, i.e syntax in this case. This alphabet is a subset of the ASCII characters. 

1) The language of all strings consisting of n  0s followed by n  1s  for some
n ≥ 0 : {ε,01,0011,000111,…}.

2) The set of strings of 0's and 1's with an equal number of each: {ε,01,10,0011,0101,1001,...}

3) The set of binary numbers whose value is a prime: {10,11,101,111,1011,...}

4) **Σ^*^** is a language for any alphabet **Σ**.

5) **Φ**, the **empty language**, is a language over any alphabet. **{ε}**, the language consisting of only the **empty string**, is also a language over any alphabet. Notice that **Φ ≠ {ε}**; the former has no strings and the latter has one string.

The only important constraint on what can be a language is that **all alphabets are finite.** 

Thus languages, although they can have an infinite number of strings, are restricted to consist of strings drawn from one fixed, finite alphabet.

In automata theory, **a problem is the question of deciding whether a given string is a member of some particular language.** 

### Finite Automata	

A  finite automaton has a set of states and its control  moves from state to state in response to external inputs. 

One of the crucial distinctions among classes of  finite automata is whether that control is **deterministic** meaning that the automaton cannot be in more than one state at any one time or **nondeterministic** meaning that it may be in several states at once.

Adding nondeterminism does not let us define any language that cannot be defined by a deterministic finite automaton, but there can be a substantial efficiency in describing an application using a nondeterministic automaton. 

In effect, nondeterminism allows us to "program" solutions to problems using a higher-level language. The nondeterministic finite automaton is then "compiled", by an algorithm, into a determinstic automaton that can be "executed" on a functional computer.

### Deterministic Finite Automata

A *deterministic finite automaton* consists of:

1. A finite set of states, often denoted Q.

2. A finite set of input symbols, often denoted Σ.

3. A transition function that takes as arguments a state and a n input symbol and returns a state. The transition function will commonly be denoted δ. 

   δ: Q × ∑ → Q

If q is a state, and *a* is an input symbol, then δ(q,a) is a state p such that there is an arc labeled a from q to p. 

4. A start state (q~0~), one of the states in Q. (q~0~ ∈ Q)
5. A set of final or accepting states F, where F $\subset$ Q.

A deterministic finite automaton will often be referred to by its acronym: **DFA**. 

> **Five-tuple notation: A = (Q, Σ, δ, q~0~, F)**
>

Two preferred notations for describing automata:

1. Transition diagram (graph)
2. Transition table (Tabular listing of the δ function)

**Transition Diagrams**

A trlansition diagram for a DFA A = (Q, Σ, δ, q~0~, F) is a graph defined as follows:

a)  For each state in Q there is a node.

b)  For each state q in Q and each input symbol ain b, let δ(q,a) = p.

Then the transition diagram has an arc from node q to node p,labeled a. If there are several input symbols that cause transitions from q to p, then the transition diagram can have one arc, labeled by the list of these symbols.

c)  There is an arrow into the start state q~0~, labeled Start. This arrow does not originate at any node.

d)  Nodes corresponding to accepting states (those in F) are marked by a double circle. States not in F have a single circle.

**Transition Tables**

A transition table is a conventional, tabular representation of a function like δ that takes two arguments and returns a value. The rows of the table correspond to the states , and the columns correspond to the inputs. The entry for the row corresponding to state q and the column corresponding to input a is the state δ(q,a).

**How a DFA Processes Strings**

*The language of the DFA is the set of all strings that the DFA accepts.* 

Suppose a~1~ a~2~ a~3~ … a~n~ is a sequence of input symbols. We start out with the DFA in its start state, q~0~. 

We consult the transition function δ, say δ(q~0~,a~1~) = q~1~ to find a state that the DFA enters after processing the first input symbol a~1~. 

We continute in this manner for the symbols that follow in the sequence, finding states q~3~,q~4~,q~5~,….q~n~ such that δ(q~i-1~,a~i~) = q~i~ for each i. 

If q~n~ is a member of F, then the input sequence is accepted, and if not then it is "rejected".

**Example 2.1:** Let us formally specify a DFA that accepts all and only the strings of 0 and 1 that have the sequence 01 somewhere in the string. We can write this language L as:

> ***{ w | w is of the form x01y for some strings x and y consisting of 0's and 1 's only}***
>

Another equivalent description, using parameters x and y to the left of the vertical bar, is: 

> ***{ x01y | x and y are any strings of 0's and l's}***
>

Examples of strings in the language include 01, 11010, and 100011. 

Examples of strings not in the language include ε, 0, and 111000.

What do we know about an automaton that can accept this language L?

First, its input alphabet is  Σ = {0,1}. It has some set of states, Q, of which one, say q~0~, is the start state. This automaton has to remember the important facts about what inputs it has seen so far. To decide whether 01 is a substring of the input, A needs to remember:

1. Has it already seen 01? If so, then it accepts every sequence of further inputs; i.e., it will only be in accepting states from now on.
2. Has it never seen 01, but its most recent input was 0, so if it now sees a 1, it will have seen 01 and can accept everything it sees from here on?
3. Has it never seen 01, but its last input was either non-existent (it just started) or it has last seen a 1? In this case, A cannot accept until it first sees a 0 and then sees a 1 immediately after.

These three conditions can each be represented by a state. Condition (3) is represented by the start state, q~0~. Surely, when just starting, we need to see a 0 and then a 1. But if in state q~0~ we next see a 1, then we are no closer to seeing 01, and so we must stay in state q~0~. 

> i.e, 								**δ(q~0~, 1) = q~0~.**

However, if we are in state q~0~ and we next see a 0, we are in condition (2).

That is, we have never seen 01, but we have our 0. Thus, let us use q~2~ to represent condition (2). Our transition from q~0~ on input 0 is - 

> ​								**δ(q~0~, 0) = q~2~.**

Now, let us consider the transitions from state q~2~. If we see a 0, we are nobetter off than we were, but no worse either. We have not seen 01, but 0 was the last symbol, so we are still waiting for a 1. State q~2~ describes this situation perfectly, so we want δ(q~2~,0) = q~2~. 

If we are in state q~2~ and we see a 1 input, we now know there is a 0 followed by a 1. We can go to an accepting state, which we shall call q~1~, and which corresponds to condition (1) above. 

> i.e, 								**δ(q~2~, 1)=q~1~·**

Finally, we must design the transitions for state q~1~. In this state, we have already seen a 01 sequence, so regardless of what happens, we shall still be in a situation where we've seen 01. 

> i.e, 								**δ(q~1~, 0) = δ(q~1~, 1) = q~1~.**

> Thus, 							***Q = {q~0~, q~1~, q~2~}.*** 

As we said, q~0~ is the start state, and the only accepting state is q~1~;  

> i.e,								***F = {q~1~}.*** 

The complete specification of the automaton A that accepts the language L of strings that have a 01 substring, is

> ​							***A = ({q~0~, q~1~ ,q~2~}, {0,1}, δ, q~0~, {q~1~})***

where δ is the transition function described above.

##### **Transition Diagram:**

![Screen Shot 2018-02-17 at 20.46.02](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Figure 2.4.png)

##### **Transition Table:**

![Screen Shot 2018-02-17 at 20.45.52](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Transition Table.png)

##### **Extending the Transition Function:**

We have explained informally that the DFA defines a language: the set of all strings that result in a sequence of state transitions from the start state to an accepting state. In terms of the transition diagram, the language of a DFA is the set of labels along all the paths that lead from the start state to any 	accepting state. 

Now, we need to make the notion of the language of a DFA precise. To do so,we define anextended transition function that describes what happens when we start any state and follow any sequence of inputs. If δ is our trnasition function, then the extended function contructed from δ will be called ð.

The extended transition function is a function that takes a state *q* and a string *w* and returns a state *p* - the state that the automaton reaches when starting in state *q* and processing the sequence of inputs *w*. We define ð by induction on the length of the input string, as follows:

> **Basis:** ð(q,ε) = q. That is, if we are in state *q* and read no inputs, then we are still in state *q*.

> **Induction**: Suppose *w* is a string of the form *xa*; that is, *α* is the last symbol of *w*, and *x* is the string consisting of all but the last symbol. For example, *w* = 1101 is broken into 
> *x* = 110 and *a* = 1. 

Then,

> ​							**ð(q, w)=δ(ð(q, x), a)**			

To compute ð(q,*w*), first compute ð(q,x), the state that the automaton is in after processing all but the last symbol of *w*. Suppose this state is p; that is ,ð(q,x)=p. Then ð(q,*w*) is what we get by making a transition from state p on input a, the last symbol of *w*. i.e, ð(q,*w*) = δ(p,a).

![Screen Shot 2018-02-17 at 20.34.01](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Example 2.4.png)

![Screen Shot 2018-02-17 at 20.34.58](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Example 2.4 - II.png)

**The Language of a DFA**				

Now, we can define the language of a DFA A = (Q, Σ, δ, q~0~, F). This language is denoted L(A), and is defined by -

> **L(A) = { *w* | ð(q~0~, *w*) is in F }**		

That is, the language of A is the set of strings ω τhat take the start state q~0~ to one of the accepting states.

>  If L is L(A) for some DFA A, then we say L is a **regular language.** 

### Nondeterministic Finite Automata	

> ***A "nondeterministic" finite automaton (NFA) has the power to be in several states at once.*** 

This ability is often expressed as an ability to "guess" something about its input. 

For instance, when the automaton is used to search for certain sequences of characters (e.g., keywords) in a long text string, it is helpful to "guess" that we are at the beginning of one of those strings and use a sequence of states to do nothing but check that the string appears, character by character.	

The NFA's accept exactly the regular languages, just as DFA's do. However, there are reasons to think about NFA's. They are often more succinct and easier to design than DFA's. Moreover,while we can always convert an NFA to a DFA, the latter may have exponentially more states than the NFA; fortunately, cases of this type are rare.	

Like the DFA, an NFA has a finite set of states, a finite set of input symbols, one start state and a set of accepting states. It also has a transition function, which we shall commonly call δ . 

> ***The difference between the DFA and the NFA is in the type of δ.*** 

For the NFA, δ is a function that takes a state and input symbol as arguments (like the DFA's transition function), but *returns a set of zero ,one ,or more states (rather than returning exactly one state,as the DFA must).*

An NFA is represented essentialy like a DFA:

> ​								**A = (Q, Σ, δ, q~0~, F)**
>

where:

1.  Q is a finite set of states.

2. Σ is a finite set of input symbols.

3. q~0~, a member of Q, is the start state.

4. F, a subset of Q, is the set of final or accepting states.

5. δ, the transition function that takes a state in Q and an input symbol in Σ as arguments and returns a subset of Q. (returns a single state in the case of a DFA)

   ![Screen Shot 2018-02-17 at 20.36.52](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Figure 2.9.png)

Given figure shows a nondeterministic finite automaton, whose job is to accept all and only the strings of 0's and 1's that end in 01. State q~0~ is the start state, and we can think of the automaton as being in state q~0~ (perhaps among other states) whenever it has not yet "guessed" that the final 01 has begun. It is always possible that the next symbol does not begin thefinal 01, even if that symbol is 0. Thus, state q~0~ may transition to itself on both 0 and 1.

However, if the next symbol is 0, this NFA also guesses that the final 01 has begun. An arc labeled 0 thus leads from q~0~ to state q~1~. Notice that there are two arcs labeled 0 out of q~0~. The NFA has the option of going either to q~0~ or to q~1~, and in fact it does both, as we shall see when we make the definitions precise. In state q~1~, the NFA checks that the next symbol is 1, and if so, it goes to state q~2~ and accepts.

Notice that there is no arc out of q~1~ labeled 0, and there are no arcs at all out of q~2~. In these situations, the thread of the NFA's existence corresponding to those states simply "dies," although other threads may continue to exist. 

While a DFA has exactly one arc out of each state for each input symbol, an NFA has no such constraint; we have seen in the figure cases where the number of arcs is zero, one, and two, for example.

![Screen Shot 2018-02-17 at 20.38.06](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Figure 2.10.png)


Above figure suggests how an NFA processes inputs. We have shown whathappens when the automaton of the given NFA receives the input sequence 00101. It starts in only its start state, q~0~. When the first 0 is read, the NFA may go toeither state q~0~ or state q~1~, so it does both. 

Then, the second 0 is read. State q~0~ may again go to both q~0~ and q~1~. However, state q~1~ has no transition on 0, so it "dies." When the third input, a~1~, occurs, we must consider transitions from both q~0~ and q~1~. 

We find that q~0~ goes only to q~0~ on 1, while q~1~ goes only to q~2~. Thus, after reading 001, the NFA is in states q~0~ and q~2~. Since q~2~ is an accepting state, the NFA accepts 001.

However, the input is not finished. The fourth input, a 0, causes q~2~'s thread to die, while q~0~ goes to both q~0~ and q~1~. The last input, a 1, sends q~0~ to q~0~ and q~1~ to q~2~. Since we are again in an accepting state, 00101 is accepted.

The given NFA can be specified formally as **({q~0~,q~1~,q~2~},{0, 1},δ,q~0~, {q~2~})** where the transition function δ is given by the transition table below: 

![Screen Shot 2018-02-17 at 20.40.03](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Figure 2.11.png)

Notice that transition tables can be used to specify the transition function for an NFA as well as for a DFA. The only difference is that each entry in the table for the NFA is a set, even if the set is a singleton (has one member). Also notice that when there is no transition at all from a given state on a given input symbol, the proper entry is 0, the empty set.

As for DFA's, we need to extend the transition function δ of an NFA to a function ð that takes a state q and a string of input symbols ω, and returns the set of states that the NFA is in if it starts in state q and processes the string ω.

The idea was suggested by the previous diagram, in essence ð(q,ω) is the column of states
found after reading ω, lf q is the lone state in the first column. 

For instance, it suggests that  ð(q~0~, 001) = {q~0~, q~2~}. Formally, we define ð for an NFA's transition function ð by: 


**BASIS:**  δ(q, ε) = {q}. That is, without reading any input symbols, we are only in the state we began in.

**INDUCTION:** Suppose *w* is of the form ω=xa, where a is the final symbol of *w* and x is the rest of *w*. Also suppose that ð(q, x) = {p~l~, p~2~, …, p~k~}. 

Let ![Screen Shot 2018-02-17 at 20.49.45](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Union I.png)

Then ð(q,ω)= {r~1~,r~2~,. . . ,r~m~}. Less formally, we compute ð(q,ω) by first computing ð(q,x), and by then following any transition from any of these states that is labeled a.

Let us use ð to describe the processing of input 00101 by the NFA 			

1. ð(q~0~, e) = {q~0~}.
2. ð(q~0~, 0) = δ(q~0~, 0) = {q~0~, q~1~}.
3. ð(q~0~, 00) = δ(q~0~, 0)  ∪ δ(q~1~, 0) = {q~0~, q~1~}  ∪ ø = {q~0~, q~1~}.
4. ð(q~0~, 001) = δ(q~0~, 1)  ∪ δ(q~1~, 1)= {q~0~}  ∪ {q~2~} = {q~0~, q~2~}.
5. ð(q~0~, 0010) = δ(q~0~, 0)  ∪ δ(q~2~, 0) = {q~0~, q~1~}  ∪ ø = {q~0~, q~1~}.
6. ð(q~0~, 00101) = δ(q~0~, 1)  ∪ δ(q~1~, 1) = {q~0~}  ∪ {q~2~} = {q~0~, q~2~}.

##### **The Language of an NFA**

As we have suggested, an NFA accepts a string ω if it is possible to make any sequence of choices of next state, while reading the characters of ω, and go from the start state to any accepting state. The fact thtat other choices using the input symbols of ω lead to a non-accepting state, or do not lead to any state at all (i.e, the sequence of states "dies"), does not prevent ω from being accepted by the NFA as a whole. Formally, if  A = (Q, Σ, δ, q~0~, F) is an NFA, then

> ​						***L(A) = { ω |ð(q~0~, w) ∩ F ≠ ø }***

That is, L(A) is the set of strings in Σ^*^ such that ð(q~0~, *w*) contains at least one acceptìng state.

Note: Make sure you go through Example 2.9, to understand proof of acceptance of a language by an NFA through mutual induction.

### Finite Automata with Epsilon-Transitions

The new feature is that we allow a transition on ε, the empty string. In effect, an NFA is allowed to make a transition spontaneously, without recieveing an input symbol. It is known as ε-ΝFA. As mentioned before in the case of comparing NFAs and DFAs, ε-NFAs don't expand the class of languages that can be accepted, but rather offers extra programming convenience. 

Each ε along a path is invisible, i.e, it contributes nothing to the string along the path. 

> *When you supply ε as an input to a state, the state does not change and control remains in the same state, unless a specified transition for ε is defined in the automata.*

We may represent an ε-ΝFA exactly as we do an NFA, with one exception: the transition function ust include information about transitions on ε. 

Formally, we represent an ε-NFA A by -

> ​						A = (Q, Σ, δ, q~0~, F) 

where all components have their same interpretation as for an NFA, except that δ is now a function that takes as arguments:

1. A state in Q, and
2. A member of Σ  ∪ {ε}, that is, either an input symbol or the symbol ε. 

We require that ε cannot be a member of the alphabet Σ, to avoid any confusion.

Example: ε-ΝFA that accepts decimal numbers consisting of: 

 	1. An optional + or - sign,
	2. A string of digits,
	3. A decimal point, and
	4. Another string of digits. Either this string of digits, or the string in (2) can be empty, but at least one of the two strings of digits must be nonempty.

![Screen Shot 2018-02-20 at 12.57.56](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Figure 2.18.png)

Note the transition from q~0~ to q~1~ on any of ε, + or —. The state q~1~ represents the situation in which we have seen the sign if there is one, and perhaps some digits, but not the decimal point. State q~2~ represents the situation where we have just seen the decimal point, and may or may not have seen prior digits. In q~4~, we have definitely seen at least one digit, but not the decimal point. 

At q~3~, we have seen a decimal point and at least one digit, either before or after the decimal point. We may stay in q~3~ reading whatever digits there are, and also have the option of "guessing" the string of digits is complete and going spontaneously to q~5~, the accepting state. 

##### ε-closure

Informally, we ε-close a state q by following all transitions out of q that are labelled ε. However, when we get to other states by following ε, we follow the ε-transitions out of those states and so on, eventually finding every state that can be reached from q along any path whose arcs are all labelled ε.

> *ε-closure of a state is the set of all the states that can be reached on providing the input symbol ε to the state, recursively.*

Formally, we define the (ε-closure) ECLOSE(q) recursively, as follows: 

BASIS: State q is in ECLOSE(q).

INDUCTION: If state p is in ECLOSE(q), and there is a transition from state p to state r labelled ε, then r is in ECLOSE(q). More precisely, if δ is the transition function of the ε-NFA involved, and p is in ECLOSE(q), then ECLOSE(q) also contains all the states in δ(p, e).

In the above figure (2.18), each state is its own ε-closure, with two exceptions: 
ECLOSE(q~0~) ={q~0~, q~1~} and ECLOSE(q~3~) = {q~3~, q~5~}, as there are two ε-transitions defined for q~1~ and q~3~ that adds q~1~ to ECLOSE(q~0~) and  q~5~ to ECLOSE(q~3~). 

*ε-closure of a set of states S, is equal to the union of ε-closures of the individual states.* 

##### **Extended Transitions and Langues for ε-ΝFAs** 

The ε-closure basically tells you what the transition of an ε-NFA looks like when given a sequence of non-ε inputs. From there, you can contemplate what it means for an ε-ΝFA to accept its input.

Suppose that E = (Q, Σ, δ, q~0~, F) is an ε-ΝFA. We first define ð, the extended transition function, to reflect what happens on a sequence of inputs. The intent is that ð(q,*w*) is the set of states that can be reached along a path whose labels, when concatenated, form the string *w*. 

As always, ε along the paths do not contribute to the *w*. The appropriate recursive definition of ð is -

BASIS: ð(*q, ε*) = ECLOSE(*q*), i.e - if the label of the path is ε, then we can follow only ε-labelled arcs extending from state q; exactly what ECLOSE does.

INDUCTION: Suppose *w* is of the form *xa*, where *a* is the last symbol of *w*. (Note that *a* is a member of Σ), it cannot  be ε, which is not in Σ. ð(*q,w*) is  computed as follows -

1. Let {p~1~, p~2~, p~3~, … , p~k~} be ð(*q,x*). That is, the p~i~'s are all and only the states that we can reach from *q* following the path labelled *x*. This path may end with one or more transitions labeled ε, and may have other ε-transitions, as well. 
2. Let ![Screen Shot 2018-02-25 at 00.04.55](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Union.png) be the set {r~1~, r~2~, … r~m~}. That is, follow all transitions labeled *a* from states we can reach from *q* along paths labeled x. The r~i~'s are *some* of the states we cna reach from *q* along the paths labeled *w*. The additional states we can reach are found from r~j~'s by following ε-labeled arcs in step(3), below.
3. Then ð(q,w) = ECLOSE({r~1~, r~2~, … r~m~}). This additional closure step includes all the paths from *q* labelled *w*, by considering the possibility that there are additional ε-labeled arcs that we can follow after making a transition on the final "real" symbol, *a*.

Basically, you can infer the following from the above steps -

> ð(*q, ε*) = ECLOSE(*q*)
>
> For a symbol '*a*',  ð(*q*, *a*) = ECLOSE(δ(ð(*q, ε*), *a*))
>
> For a sequence of symbols *w* = *xa*,  ð(*q*, *w*) = ð(*q*, *xa*) = ECLOSE(δ(ð(*q, x*), *a*))

![Screen Shot 2018-02-25 at 00.25.10](/Users/vishhvaksrinivasan/Stuff/Course Stuff/TOC-Notes/Diagrams/Example 2.20.png)

> L(E) = { *w* | ð(*q~0~, w*) **∩** F ≠ φ }

That is, the language of E is the set of strings *w* that take the start state to at least one accepting state. 

​					


​			
​		
​	

​	
​	
​	
​		
​			
​				
​					


​				
​			
​		
​	


​			
​		
​	






​			


​		
​	