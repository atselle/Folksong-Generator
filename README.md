# Folksong-Generator
This project utilizes the Music21 suite in order to generate unique, original folksongs derived from an analysis of any given corpus of XML files the user wants. It was created using German folksongs from the Altdeu project, but would reliably work with any corpus.

The process is Markov-based, and thus a larger corpus will naturally lead to more possible continuations, especially as the Markov order becomes larger. This being said, a larger corpus reults in a much longer processing time, so we recommend using pickle (or some other form of storage) to maintain the date for all possible ngrams.

Note that the main Makemusic function at this time does not analyze rhythm, but rather chooses from a set of predetermiend rhythmic patterns for each bar. Because rhythms in folksongs are fairly predictable, we felt this produced satisfactory results. We have included a rhythmic Markov algorithm if one wanted to adapt the generator to other styles of music.

To run the code, make sure that the directory is set to wherever the XML corpus is stored (at the top of the code). The bottom of the code has two calls to get the pitches based upon whether or not it is the first time running the code (use the first call) or not (use the second call). Finally, call make_music with two arguments: the Music21 stream to fill with notes and rhythms (we have initialized a stream called "test") and the Markov order. 
