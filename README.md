# dist-shift
Application that auto-retrains when it detects a concept shift in production data.


There are two types of concept drifts:

1. When the model is trained on data that merely approximates the production data, and the production data never really resembles the train/test data.

2. When the function from inputs to outputs actually drifts away from what the model is trained on. In this case, the production data starts out similar to the train/test data, and then changes over time.


We test both types, and compare various re-training algorithms under these two conditions.


A program by Joe Redmond and Tamanna Ananna.
