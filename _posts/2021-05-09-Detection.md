---
layout: post
title:  "Scene Text Detection and Recognition"
info: "A deep network for scene text detection and recognition on a subset of ICDAR 2013"
tech : "PyTorch"
type: Project
---
<h2><center>A deep network for Scene Text Detection</center></h2>

Click here to see the [code](https://github.com/XUANTONG1999/Scene-Text-Detection).

Based on RNN and CTC decoding, complete scene text recognition tasks

## Introduction to CTC

![detection-1](/imgs/Projects/detection-1.jpg)

Temporal Classification task: The input is a sequence, and the output is the result of classification on the sequence. For example, speech recognition, given a speech sequence sample and the corresponding speech content label, train a model to predict the speech content (character sequence) through the speech sequence.

#### Difficulties

How does the output character sequence align with the input sequence?
For example, which short waveform of the speech sequence corresponds to the "j" character?

For traditional classification tasks, temporal classification is more difficult.

To be a bit more formal, let’s consider mapping input sequences $$X = [x_1, x_2, \ldots, x_T]$$, such as audio, to corresponding output sequences $$Y = [y_1, y_2, \ldots, y_U]$$, such as transcripts. We want to find an accurate mapping from $$X$$’s to $$Y$$’s.

There are challenges which get in the way of us using simpler supervised learning algorithms. In particular:

- Both $$X$$ and $$Y$$ can vary in length.
- The ratio of the lengths of $$X$$ and $$Y$$ can vary.
- We don’t have an accurate alignment (correspondence of the elements) of $$X$$ and $$Y$$.

Click [here](https://distill.pub/2017/ctc/) to learn more about CTC.

## Implementation

![detection-2](/imgs/Projects/detection-2.jpg)

CNN: Extract high-level semantic representation of the image and output convolutional features;

Pool: Pooling layer, which converts two-dimensional convolution features into one-dimensional sequence features along the width direction;

RNN: Perform sequence modeling on the context of features and output sequence features enhanced by context;

FC: The fully connected layer takes sequence features as input and outputs classification sequences with unnormalized probabilities (Subsequently, you need to use **Softmax** to normalize the classification probabilities);

CTC: Convert classification sequences into output character sequences to realize automatic alignment of inputs and outputs.

## Visualization

Here is an example.

![CTC-9](/imgs/Projects/CTC-9.png)

The character corresponding to index 0 is $$s$$​ or $$5$$​, among which the probability of $$s$$ is greater, so it is determined that the character is $$s$$​;


The characters with index 1, 2, and 3 are all "blank" characters, the character with index 5 is $$y$$​​​; the character with index 4 is "blank" or $$y$$​​​, and the probability of "blank" is greater, so the character is judged to be "blank"; the character with index 6 is "blank" or $$y$$​​​, and the probability of "blank" is greater, so the character is judged to be "blank";

The character with index 12 is "blank" or $$t$$​, among which the probability of $$t$$​ is greater, so the character is determined to be $$t$$​; the character with index 13 is $$f$$​ or $$t$$​ or $$i$$​, Among them, the probability of $$t$$​ is greater, so the character is determined to be $$t$$​;

The character with index 14, 15, 17, 18, 19 is "blank", the character with index 16 is $$e$$, and the character with index 20 is $$m$$;

The alignment obtained from the above analysis is:

$$s----y---s--tt--e---m-----$$​​

The final output sequence obtained after the alignment process is: $$system$$​, which is consistent with the visualization results.
