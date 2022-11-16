=======================================
Chapter 1: Language
=======================================

Section 1: Generating Sentences
::::::::::::::::::::::::::::::::

We have generated language in several ways in this class already.

One way was with the `simple language generator <https://teaspoon.livecodehosting.com/sentences-html/generator.lc>`_. We typed in a model (a sentence pattern) and a dictionary of words by parts.

.. image:: figures/SentenceGenerator.png

We have also done sentence generation in Snap. We have a `language generation project <https://snap.berkeley.edu/project?username=guzdial&projectname=language%20generation>`_ that lets us generate sentences by parts, just like in the simple language generator.

.. image:: figures/picking-words-from-variables.png


The Python Version V1
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

.. mchoice:: PyGen1_2
    :correct: c
    :answer_a: Tells Python that it is going to make a choice among these items
    :answer_b: Creates a variable
    :answer_c: Define a list, like our multiline or list blocks in Snap.
    :feedback_a: No -- the choice comes later
    :feedback_b: No, the variable name with `=` does that.
    :feedback_c: That's right.

    What do you think the square brackets [] do in the above Python code?

.. mchoice:: PyGen1_3
    :correct: c
    :answer_a: It generates a random number
    :answer_b: It's a fairly arbitrary variable name
    :answer_c: It's the name of the library that contains the function `choice`
    :feedback_a: No -- the random library can generate a random number, but that's not what random means
    :feedback_b: No, it's pre-defined in Python.
    :feedback_c: That's right.

    Take a guess what the word `random` is above?

The Python Version V2
----------------------

The below program does the same thing in Python.  Click 'Run' to generate a random sentence.

.. activecode:: pysentencegen2
   :language: python
   
   import random
   
   nouns = ["bee","bird","bat"]
   adjectives = ["curious", "small", "majestic"]
   verbs = ["flies", "explores", "roams"]
   adverbs = ["slowly", "cautiously", "urgently"]
   articles = ["The","A"]
   
   noun = random.choice(nouns)
   adjective = random.choice(adjectives)
   verb = random.choice(verbs)
   adverb = random.choice(adverbs)
   article = random.choice(articles)
   
   print(article,adjective,noun,verb,adverb)

Try answering these questions about the code above.

.. mchoice:: PyGen2_1
    :correct: b
    :answer_a: A list of adjectives
    :answer_b: A randomly selected string from the 'adjectives' list.
    :answer_c: A first string from the 'adjectives' list.
    :feedback_a: Not quite, 'adjectives' holds the list not 'adjective'.
    :feedback_b: Yes, exactly right.
    :feedback_c: Not always, it may return the first string, but it can also return any other string in the list.

    What does the variable 'adjective' hold in the above snippet?

.. mchoice:: PyGen2_2
    :correct: a
    :answer_a: "A bee explores cautiously"
    :answer_b: "The curious bird roams slowly"
    :answer_c: "A small bat flies urgently"
    :feedback_a: Yes, this answer is missing an adjective.
    :feedback_b: No, this answer contains all the required components.
    :feedback_c: No, this answer contains all the required components.

    Which of the following is a sentence that could NOT be produced from the code above?

.. mchoice:: PyGen2_3
    :correct: a
    :answer_a: nouns = ["bee","bird","bat"]
    :answer_b: verbs = ["flies", "explores", "roams"]
    :answer_c: adjective = random.choice(adjectives)
    :answer_d: print(article,adjective,noun,verb,adverb)
    :feedback_a: No,you will need to add "boat"
    :feedback_b: No, you will need to add "floats"
    :feedback_c: Yes, this line stays the same
    :feedback_d: No, you will need to remove the final ",adverb"

    Let's say that you want to make it possible for to generate "A curious boat floats."  Which of the lines below do you *not* have to change?

Section 2: Creating a little Python chatbot
::::::::::::::::::::::::::::::::::::::::::::

You have built Chatbots in Snap!.
Here's an example of a little one:

.. image:: figures/Snap-kinda-chatbot.png

Here is a (very) little Python chatbot.  This one is a little more sophisticated than our Snap chatbot -- it can pick out a name from an input sentence, and it can do the equivalent of **respond randomly** that we saw in Charla-bot.

Python here in a Runestone ebook can't receive user input, so let's just change the `inputSentence` variable to represent
what the user says. Press Run to see what the chat bot responds.

.. activecode:: pysentencegen3
   :language: python
   
   import random
   
   inputSentence = "Hi, my name is Elijah"
   wordsInSentence = inputSentence.split()
   
   greetings = ["Hi", "Hello", "Howdy", "Sup"];
   
   questions = ["What is your favorite color?", "Where do you like to eat?", "How is your day going?", "Do you have any siblings?", "What are your hobbies?"]

   if "name" in wordsInSentence:
      nameIndex = wordsInSentence.index("name");
      if "is" == wordsInSentence[nameIndex + 1]:
        yourName = wordsInSentence[nameIndex + 2]
        print("Hi", yourName, "how are you?")
   else:
      found = False
      for greetingWord in greetings:
         if greetingWord in wordsInSentence:
           print("Hi, how are you?")
           found = True
           break
      if not found:
          print(random.choice(questions))


This code is recognizing words in the `inputSentence` then deciding what to `print` in response.

- `inputSentence.split()` breaks up the input into distinct words.
- The first block that starts with `if` is asking if the input sentence contains the word "name".

  - If the word "name" is there, the function `index` tells us where "name" appears. That goes in `nameIndex`.
  - If the word "is" is just after "name", then we guess that the next word is the user's name. Put that in `yourName`.
  - Then, print out a greeting for the specific name. (Remember that bots often focus on one word the user says.)

- If the word "name" isn't there, we check all the possible `greetings` words.

  - If one of those greeting words is in the input sentence, then `print` a basic "Hi, how are you?"
  - If we do find a greeting word, we set a variable that we `found` one. We `break` out of the loop checking the greeting words.   
  - If we did not find a greeting word (`not found`), then we print a random question back to the user.


.. mchoice:: PyGen3_1
    :correct: a
    :answer_a: Checks to see if the input sentence has the word "name" in it.
    :answer_b: Puts the word "name" into the output
    :answer_c: Asks the user what their name is
    :feedback_a: Exactly. `wordsInSentence` is the list of words in the input sentence
    :feedback_b: No, output is generated with print()
    :feedback_c: No, nothing here does that.

    What do you think `if "name" in wordsInSentence` does?

.. mchoice:: PyGen3_2
    :correct: b
    :answer_a: Lists the questions that the user might ask.
    :answer_b: Provide possible responses like *respond randomly* in Charla-bots.
    :answer_c: Makes it possible for the computer to respond to questions.
    :feedback_a: No, that isn't happening here.
    :feedback_b: Exactly. Each question is a like another line in *respond randomly*.
    :feedback_c: No, those aren't questions that the computer can respond to.

    What do you think the variable `questions` is doing?

.. mchoice:: PyGen3_3
    :correct: b
    :answer_a: How are you?
    :answer_b: Hey, Sup
    :answer_c: Hola, Dude
    :feedback_a: No, that doesn't contain any of the words in `greetings`
    :feedback_b: Yes, because "Sup" is in `greetings`.
    :feedback_c: No, that sentence doesn't contain any of the words in `greetings`

    Which of these `inputSentence` options (and you're welcome to try them!) would generate the chatbot saying "Hi, how are you?"

.. mchoice:: PyGen3_4
    :correct: a
    :answer_a: True
    :answer_b: False

    `found` in this program is just a variable, that could be named anything, but it's purpose is to track if we found a greeting word.

