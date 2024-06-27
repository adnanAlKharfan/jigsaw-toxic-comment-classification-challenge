# Jigsaw Toxic Comment Challenge

the jigsaw toxic comment challenge is a challenge to make an Ai Model to identify people comment whether it was toxic or sever toxic or obscene or threat or insult or identity hate or all of them.

## Introduction

This repository shows my intake on this task and how i was able to success in it, what accuracy i abtained for this fun challenge.

## Dataset

The [Toxic Comment Classification Challenge Data](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data) consist of train, test, test labels and samples submission.
The Dataset consist of 8 columns: id, comment, toxic, sever toxic, obscene, threat, insult, identity hate.
Each one of them had either the value 0 or 1.

### Example of the train data:

| id | comment_text | toxic |	severe_toxic | obscene | threat | insult | identity_hate |
| --- | --- | --- | --- | --- | --- | --- | --- | 
| 0000997932d777bf | Explanation\nWhy the edits made under my usern... | 0 | 0 | 0 | 0 | 0 | 0 |
| 000103f0d9cfb60f | D'aww! He matches this background colour I'm s...	| 0 | 0 | 0 | 0 | 0 | 0 |
| 000113f07ec002fd | Hey man, I'm really not trying to edit war. It...	| 0 | 0 | 0 | 0 | 0 | 0 |
| 0001b41b1c6bb37e | "\nMore\nI can't make any real suggestions on ...	| 0 | 0 | 0 | 0 | 0 | 0 |
| 0001d958c54c6e35 | You, sir, are my hero. Any chance you remember...	| 0 | 0 | 0 | 0 | 0 | 0 |

## Methodology

  1. used glove 100 dimension for words vector.
  2. padded the data to maxium word in a sentence from the dataset.
  3. loaded glove 100 weights into our embedded layer.
  4. pass the vector of each words in the sentence to three LSTM Layers so every words in the sentence depends on the previous ones.
  5. took the global max values using global max pooling 1d layer since the data is texts.
  6. passed to the final dense layer that have 6 neurons following the number of outputs we have with sigmoid as activation function since we could have multiple combination rather than only one.

## Result

The Experiment was done using google colab gpu for a faster computation than my pc.

- epochs: `10`
- Training loss: `0.0448`
- Training accuracy: `0.9936`
- validation loss: `0.0498`
- validation accuracy: `0.9935`
- Test accuracy: `0.9966`

### Prediction Result

- the sentence `fuck you` was classified as toxic, obscene and an insult.

> [!NOTE]
> I forgot to create requirements.txt file so it could run as expected.

## Usage

The comment classification model can be use in classifying people comment on social media or any platform that texts is used on.

## Contribution

Contributions are welcome! If you have any improvements or new features you would like to add, please submit a pull request. 
