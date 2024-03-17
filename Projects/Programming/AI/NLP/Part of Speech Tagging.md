
In corpus linguistics, part-of-speech tagging (POS tagging or PoS tagging or POST), also called grammatical tagging is the process of marking up a word in a text (corpus) as corresponding to a particular part of speech, based on both its definition and its context. 

A simplified form of this is commonly taught to school-age children, in the identification of words as nouns, verbs, adjectives, adverbs, etc.

Example:

| Lexical Term | tag | example |
| ---- | ---- | ---- |
| noun | NN | something, nothing |
| verb | VB | learn, study |
| determinator | DT | the, a |
| w-adverb | WRB | why, where |

### Markov Chains
- They describe a sequence of possible events in which the probability of each event is depends only on the state of the state of the previous element

- To help identify the parts of speech for every word, you need to build a transition matrix that gives you the probabilities from one state to another:
	![[markov_chain1.png]]

- In hidden markov models you make use of emission probabilities that give you the probability to go from one state (POS tag) to a specific word. 
	  ![[markov_chain2.png]]

### Viterbi Algorithm
The Viterbi algorithm makes use of the transition probabilities and the emission probabilities as follows.

![[va1.png]]

To go from pi to O you need to multiply the corresponding transition probability (0.3) and the corresponding emission probability (0.5), which gives you 0.15. You keep doing that for all the words, until you get the probability of an entire sequence.

![[va2.png]]

Steps of the Algo:
1. Initialize step
	1. Create matrices C (this tells the probabilities - what part of speech a word belongs to) and D (probabilities of next word after current word)
2. Forward pass: https://www.coursera.org/learn/probabilistic-models-in-nlp/supplement/9BigR/viterbi-forward-pass
3. Backword pass: https://www.coursera.org/learn/probabilistic-models-in-nlp/supplement/4OAHP/viterbi-backward-pass