# SentencePiece tokenizer in python

Ok, let me first say this is nowhere near as efficient and comprehensive as the actual sentencepiece program (written in C++). That is an awesome package and I cannot advocate enough for it.

This repository is meant to demystify the algorithm. It's intimidating to go through the large amount of source code, not to mention that it's written in C++ makes the inner workings slightly harder to distill.

Here, we achieve two things:
1. We are able to train a sentencepiece tokenizer given a set of initial tokens and a corpus. We can also prune down to the desired vocab size by eliminating low probability tokens

2. We are able to both deterministicly tokenize a string, as well as provide a random sampling of different tokenizations. This is set by an nbest size parameter, which we can adjust to allow for a wider variety of tokenizations

## Layout

While it's nice to be able to get the SentencePieceTrainer up and running, it doesn't solve our tokens problem. SentencePiece relies on an auxiliary function to determine a baseline set of tokens. For this, we implement byte-pair encoding, in the module byte_pair_encoder.py The actualy SentencePiece trainer is located in the sentence_piece.py module. The text file good_taste is a short story written by Isaac Asimov that we use as sample text.

## More information with equations and explanations
If you would like to know more about how this works, please see my accompanying article on Medium, where I lay out the theory. Available at this link: [FORTHCOMING]
