# natural-brain

[![Build Status](https://travis-ci.org/daffl/natural-brain.png?branch=master)](https://travis-ci.org/daffl/natural-brain)

A natural language classifier using [Node Natural](https://github.com/NaturalNode/natural) using a [BrainJS](https://github.com/harthur/brain) neural network:

Note: This classifier passes the same tests as the [Node Natural Bayes classifier](https://github.com/NaturalNode/natural/blob/a79254585f2e381378f788de5168f6a906e037e8/spec/bayes_classifier_spec.js).

```js
var BrainJSClassifier = require('natural-brain');
var classifier = new BrainJSClassifier();

classifier.addDocument('my unit-tests failed.', 'software');
classifier.addDocument('tried the program, but it was buggy.', 'software');
classifier.addDocument('tomorrow we will do standup.', 'meeting');
classifier.addDocument('the drive has a 2TB capacity.', 'hardware');
classifier.addDocument('i need a new power supply.', 'hardware');
classifier.addDocument('can you play some new music?', 'music');

classifier.train();

console.log(classifier.classify('did the tests pass?')); // -> software
console.log(classifier.classify('did you buy a new drive?')); // -> hardware
console.log(classifier.classify('What is the capacity?')); // -> hardware
console.log(classifier.classify('Lets meet tomorrow?')); // -> meeting
console.log(classifier.classify('Can you play some stuff?')); // -> music
```
