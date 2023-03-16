Hello. Welcome to Jury Nullification's Computer Science FAQ. This is a collection of my opinions. 

## What's the difference between computer science and programming?

**Short answer:** They're two sides of the same coin.

Programming, or software development, is about *making* things. Computer science is about *studying* things. They are both *about* the same things: programs.

I will summarize them in terms of what their "fundamental questions" are:
* Programming's fundamental questions are: 
  * "How do I make a product from code?"
  * "How can I make that code fast? How can I make it reliable?"
  * "What can I do now to make my code easier to work with later?"

In short, programming is about principles of architecture and engineering. It is about **getting things done.**

* Computer science's fundamental questions are:
  * "When are two programs equal to each other?"
  * "What properties can I prove about this program?"
  * "How do I ensure that this code actually behaves the way it should?"

In short, computer science is about principles of abstractions. It is about **proving things right.**

The actual work of the programmer is to collaboratively manage abstractions in a messy world. This means that programming often touches on computer science. Likewise, the actual effort of the computer scientist is made more manageable and comprehensible with solid programming fundamentals.

### Does computer science require math?

**Short answer:** Yes, but probably not in the way you think.

The actual number-crunching of programming is important, obviously. However, the operations involved in that number-crunching rarely rise above what can be easily accomplished with a desk calculator. The operations that require heavy number-crunching are going to be abstracted into a nice little function you can call.

I'd like to talk about two different kinds of math: math-as-numbers and math-as-thinking. As previously stated, the math-as-numbers is fundamental but usually a sideshow. Unless your program involves integration, you are unlikely to have to solve an integral.

Then there's math-as-thinking. There tends to be an instinctual pulling-back when people hear the word "proof," and for good reason. A lot of people have had a rough time with "proofs" in school. If that is you, then I'd like to introduce you to the coolest thing in mathematics: the [Curry-Howard Correspondence](https://en.wikipedia.org/wiki/Curry%E2%80%93Howard_correspondence). This is commonly summarized as "proof = program;" I like to include a corollary, "definition = test."

From this perspective, the original question is kind of missing a very fundamental and central point... computer science doesn't **require** math. Computer science **is** math.

That might not be a very satisfying answer. If it isn't, then I'd guess it's not satisfying because this answer might miss a very fundamental and central point... which is that the original question usually underlies some form of math anxiety. So, to rephrase the original question with *that* in mind, it seems the pertinent question might be: "If I have a hard time with math, will I have a hard time with computer science?"

The way math is taught in schools tends to leave very capable people with self-esteem issues, a nagging self-doubt as to whether or not they can "hack it" with math. It is my opinion that there is really only one fundamentally mathematical skill that computer science requires: the ability to think in simple, unambiguous terms.

### Which language should I learn first?

**Short answer:** More is lost to indecision than to the wrong decision.

It really, really doesn't matter in my opinion. You will spend the most time acquiring your first language. After that, your second language will come easier; the third will come easier than the second; and so on. Eventually you might be picking up languages within a weekend and dropping them within a week. That "eventually" might come as quickly as within your first year or two. All of that is to say, it doesn't matter which language you start with. Just pick one and start!

I like recommending these languages as starters (in no particular order):
| Name   | Industry Popularity | Paradigm         | Type System |
|========|=====================|==================|=============|
| Python | 1                   | Object-Oriented  | Dynamic     |
| Elixir | > 50                | Functional       | Static      |
| Java   | 3                   | Object-Oriented  | Static      |
| OCaml  | > 50                | Functional       | Static      |
| Rust   | 26                  | Object-Oriented  | Static      |
| Go     | 13                  | Procedural       | Static      |
| Julia  | 33                  | Object-Oriented  | Static      |
| C      | 2                   | Procedural       | Static      |
| C#     | 5                   | Object-Oriented  | Static      |
| Prolog | 39                  | Logic/Relational | Dynamic     |
| SQL    | 8                   | Query/Relational | Static      |
* [Industry Popularity](https://www.tiobe.com/tiobe-index/)

It's important to keep in mind that programming languages are defined by their implementations. Programmers typically refer to the syntax that is common to these implementations, which is how we can say "yeah, that looks like Python." I recommend not just learning the syntax of a language, but also really digging deep into the technology underlying how the language is implemented.

A final note: the choice to recommend Elixir, OCaml, and Prolog might be controversial. Some people might call these "troll suggestions." I vehemently disagree with these assertions. These are interesting languages. They depart quite far from the "norms" of most programmers' experiences. I think they are still appropriate for the beginner.
