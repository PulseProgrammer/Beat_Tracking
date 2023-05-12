# Beat_Tracking
Beat tracking is the process of automatically detecting the beat positions or tempo in an audio signal. The project aims to develop an algorithm that accurately estimates the beat positions in music recordings.

This repository contains the implementation and analysis of a beat tracking algorithm based on the approach of Dynamic Programming, as described by Ellis[3] and the FMP Textbook.

## Introduction

A beat refers to the recurring rhythm or pulse in a piece of music, providing timing and pace. Beat tracking is a vital aspect of Music Information Retrieval (MIR) as it involves automatically detecting the temporal positions of musical beats in an audio clip. This project aims to estimate the beat instances in an audio signal, correlating with human perception of beats.

## Implementation

The implemented algorithm follows the principles outlined by Ellis[3] and FMP. It satisfies two main constraints: 

1. The derived beat periods should align with the specified beat times in the audio.
2. The time intervals between onsets should represent a constant inter-beat interval.

The basic approach involves estimating a global tempo for the audio file, constructing a cost function, and utilizing dynamic programming to minimize the cost (or maximize the score) based on high onset strength and estimated tempo. The algorithm maximizes both the onset strength and the consistency of onset intervals, given a pre-estimated tempo.

The implementation is divided into three steps:

1. Computation of the novelty function: The novelty function is a signal processing method that identifies noteworthy characteristics in an audio recording. The onset novelty function, a type of novelty function, detects moments in time when new sound events start. It calculates the probability of an onset occurring at a specific time, based on the audio signal's short-term spectrum characteristics. In this project, the provided novelty function in the FMP notebook C6/C6S1 NoveltySpectral.ipynb is used as a reference.

2. Tracking the optimal beat sequence: Previous beat-tracking algorithms utilized dynamic programming to achieve uniformity in beat interval detection and tempo. The algorithm proposed by Ellis[3] maintains a constant tempo, simplifying the formulation and execution of the algorithm. The beat positions are assumed to be around the strongest onsets locally. The algorithm constructs a score function to measure the beat positions by maximizing the beat sequence score.

3. Evaluating the results: The algorithm's performance is evaluated using music information retrieval accuracy measures.


## License

This project is licensed under the [MIT License](LICENSE). You are free to use the code for academic, research, or commercial purposes.


## References

- [1] Peeters, G. (2010). Music Similarity and Retrieval: An Introduction to Audio- and Web-based Strategies. In Proceedings of the ACM Multimedia 2010 Workshop on Advances in Music Information Research (pp. 1-6).
- [3] Ellis, D. (2007). Beat Tracking by Dynamic Programming. Journal of New Music Research, 36(1), 51-60.
- FMP: Foundations of Music Processing, Meinard Müller, 2019. Available online at: https://www.audi
