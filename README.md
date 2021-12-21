# dist-shift
Application that naively learns continuously in production to make a model robust to concept drift.


We are working with 2 different types of concept drift:

1. **Sudden Concept Drift** When the model is trained on data that merely approximates the production data, and the production data never really resembles the train/test data.

2. **Incrementeal Concept Shift**: When the function from inputs to outputs actually drifts away from what the model is trained on. In this case, the production data starts out similar to the train/test data, and then changes over time.

![image](https://user-images.githubusercontent.com/37457936/146691423-53ec071b-f98a-44d9-b109-9ec63561226d.png)
**image from [Learning under Concept Drift: A Review](https://arxiv.org/abs/2004.05785)**

That took the form of two different synthetic datasets:

The Sudden Shift Sine dataset
![image](https://user-images.githubusercontent.com/37457936/146951160-4afcbc96-5407-4ecf-85c1-f0d87731a1a2.png)

The temporal Sine Wave dataset (gradual drift)
![image](https://user-images.githubusercontent.com/37457936/146951221-b1be0b75-3f5c-493c-a5de-ae215318bb0d.png)

# Our algorithms
The idea here is to continuously learn in production, whether or not a concept drift is detected.

1. ## Online retraining
We propagate the loss for a each data point seen in production
![image](https://user-images.githubusercontent.com/37457936/146951672-5a4df067-ade3-49e2-a530-9d31a0f4b578.png)

2. ## Small Batch Online Retraining
We propogate the loss for a small batch of data seen in production. We hypothesized that this would help us be more resilient to noise in the production data.
![image](https://user-images.githubusercontent.com/37457936/146951746-34355ace-6166-4b65-91ff-f7e98748d2b7.png)


# Results
We used the error rate at the end of the production time series to evaluate the algorithm performance.
![image](https://user-images.githubusercontent.com/37457936/146951841-dc7dcd1a-7f7a-40d3-bd3e-735bdfaa701f.png)


A very cool program by Joe Redmond and Tamanna Ananna.
