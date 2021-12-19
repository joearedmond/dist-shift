# dist-shift
Application that auto-retrains when it detects a concept shift in production data.


We are working with 2 different types of concept drift:

1. **Sudden Concept Drift** When the model is trained on data that merely approximates the production data, and the production data never really resembles the train/test data.

2. **Incrementeal Concept Shift**: When the function from inputs to outputs actually drifts away from what the model is trained on. In this case, the production data starts out similar to the train/test data, and then changes over time.

![image](https://user-images.githubusercontent.com/37457936/146691423-53ec071b-f98a-44d9-b109-9ec63561226d.png)
**image from [Learning under Concept Drift: A Review](https://arxiv.org/abs/2004.05785)**


We test both types, and compare various re-training algorithms under these two conditions.



A very cool program by Joe Redmond and Tamanna Ananna.
