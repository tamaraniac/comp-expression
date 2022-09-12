=======================================
Chapter 1: Language
=======================================

Section 1: Generating Sentences
::::::::::::::::::::::::::::::::

We have generated language in several ways in this class already.

One way was with the `simple language generator <https://teaspoon.livecodehosting.com/sentences-html/generator.lcß>`_. We typed in a model (a sentence pattern) and a dictionary of words by parts.

.. image:: figures/SentenceGenerator.png

We have also done sentence generation in Snap. We have a `language generation project <https://snap.berkeley.edu/project?username=guzdial&projectname=language%20generation>`_ that lets us generate sentences by parts, just like in the simple language generator.

.. image:: figures/picking-words-from-variables.png


The Python Version
----------------------

The below program does the same thing in Python.  Click 'Run' to generate a random sentence.

.. activecode:: pysentencegen
   :language: python
   
   import random
   
   nouns = ["dog","cat","bat"]
   verbs = ["jumps", "runs", "shouts"]
   adverbs = ["slowly", "quickly", "lazily"]
   articles = ["The","A"]
   
   noun = random.choice(nouns)
   verb = random.choice(verbs)
   adverb = random.choice(adverbs)
   article=random.choice(articles)
   
   print(article,noun,verb,adverb)

Try answering these questions about the code above.

.. mchoice:: PyGen1
    :correct: a
    :answer_a: They are both variables. `nouns` is a list of nouns, and `noun` is a randomly chosen noun
    :answer_b: Just the `s`.  They mean the same thing.
    :answer_c: Both are variables, which hold data in Python
    :feedback_a: Yes, exactly right.
    :feedback_b: No, the names of the variables are just chosen to inform the reader.
    :feedback_c: That's true, but that doesn't get at the purpose of the words.

    What's the difference between `nouns` and `noun` above?