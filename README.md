# ark_tweet_nlp_python

Python wrapper for the [ARK Tweet NLP POS Tagger and Tokeniser](http://www.cs.cmu.edu/~ark/TweetNLP/). This wrapper is similar to [this other wrapper](https://github.com/ianozsvald/ark-tweet-nlp-python), but implements some of the possible improvements outlined there.

### Prerequisites

* The POS tagger .jar file found on [this page](http://www.cs.cmu.edu/~ark/TweetNLP/).
* The ability to run said .jar file.

### Usage

#### POS Tagger
```
>>> from twokeniser import Twagger
>>> T = Twagger('*path to ark-tweet-nlp-0.3.2.jar*')
>>> T.tag('You only lose what you cling to ☸️')
[('You', 'O', 0.9976), ('only', 'R', 0.8539), ('lose', 'V', 0.9944), ('what', 'O', 0.9759), ('you', 'O', 0.9992), ('cling', 'V', 0.9999), ('to', 'P', 0.9824), ('☸️', '^', 0.2319)]
```

or, for a different output format

```
>>> from twokeniser import Twagger
>>> T = Twagger('*path to ark-tweet-nlp-0.3.2.jar*', conll=False)
>>> T.tag('You only lose what you cling to ☸️')
(['You', 'only', 'lose', 'what', 'you', 'cling', 'to', '☸️'], ['O', 'R', 'V', 'O', 'O', 'V', 'P', '^'], [0.9976, 0.8539, 0.9944, 0.9759, 0.9992, 0.9999, 0.9824, 0.2319])
```
#### Tokeniser

```
>>> from twokeniser import Twokeniser
>>> T = Twokeniser('*path to ark-tweet-nlp-0.3.2.jar*')
>>> T.tokenise('You only lose what you cling to ☸️')
['You', 'only', 'lose', 'what', 'you', 'cling', 'to', '☸️']
```

## Things to note

* This has only been tested this on Linux.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

