# Human Ratings of Transcription/Translation Consistency

This repository accompanies the research paper [Consistent Transcription and Translation of Speech](https://arxiv.org/abs/2007.12741).

It contains transcript/translation consistency ratings for various system outputs as well as for the original references contained in [MuST-C](https://ict.fbk.eu/must-c/)'s English-German testset.

## Documentation

 For each of the 2640 test set utterances, we consider consistency of the original reference transcript/translation, as well as between system outputs for 7 systems described in the paper. For each utterance/system combination, we collect 3 (in some cases 4) annotations, for a total of 63412 annotations. The data is spread among two CSV files, with `sys-consistency-ratings.csv` containing consistency ratings for system outputs, and `ref-consistency-ratings.csv` containing consistency ratings for the  reference transcripts/translations. 

The CSV table contains the following fields:
- `output_idx` is a unique identifier for each utterance/system combination.
- `sent_idx` is the index of the utterance in the original MuST-C test set.
- `model` takes one of 8 values: `casc`,`dirind`,`dirmu`,`dirsh`,`2st`,`tri`,`concat` indicates that this row contains the respective model outputs (see paper). [`sys-consistency-ratings.csv` only]
- `sys_english` is the automatic English transcript [`sys-consistency-ratings.csv` only]
- `sys_german` is the automatic German translation [`sys-consistency-ratings.csv` only]
- `display_english_first`: The annotation UI displayed English transcript and German translation in random order. This field is set to `1` whenever the English was displayed first.
- `rater_idx`: a unique, anonymous identifier for the human evaluator.
- `rating`: the rating itself, an integer value between 1 and 4.
- `rater_comment`: Raters were allowed to optionally explain their choice of rating in free text.
- `adjusted_rating`: The rating, after running the random mixed effects model as described in the paper. This rating is thus adjusted for rater bias and utterance difficulty.

## Annotation Process

Annotators were first asked to familiarize themselves with the annotation guidelines, which can be found under `guidelines.pdf`. These guidelines expand upon the definition presented in the paper and add several examples for each possible score. Annotators were then asked to `Assign a score that evaluates how "CONSISTENT" the above English and German sentences are. Please carefully read the guidelines and examples before answering.`

Four choices were presented:
- 4: OK (near-perfect consistency). Good match of meaning, both sides similarly grammatical or ungrammatical. Minor mismatch in grammaticality or fluency allowed.
- 3: close (minor consistency problems). Meaning consistent, but some mismatch in style, spelling, or sentence structure.
- 2: bad (less consistent). Major mismatch in *meaning* for parts of the sentences
- 1: catastrophic (not at all consistent). Both sides have little in common

## License

This work is licensed under a [Attribution-NonCommercial 4.0 International (CC BY-NC 4.0) license](https://creativecommons.org/licenses/by-nc/4.0/).

## Citation

If you use this data in your project, please consider citing our paper:

*Matthias Sperber, Hendra Setiawan, Christian Gollan, Udhyakumar Nallasamy, Matthias Paulik (2020).* [Consistent Transcription and Translation of Speech](https://arxiv.org/pdf/2007.12741.pdf). Transactions of the Association for Computational Linguistics (TACL).
