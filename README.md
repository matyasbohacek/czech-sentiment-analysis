# Czech sentiment analysis

Machine learning model trained for semantic analysis on the Czech language. The model has been trained on a datset of several hundreds of annotated sentences and can label `positive`, `neutral` and `negative` sentiment.

It is also very lightweight and can be used for multiple use-cases.

## Metrics

| Version | Training accuracy | Validation accuracy | Testing accuracy |
|---------|-------------------|---------------------|------------------|
| `1.0`   | 99%               | 91%                 | To be done.      |

## Implementation

### Usage in Python

To use the model in your Python project, make sure to install **coremltools** package first. Then, you can simply use the following snippet to envoke the model:

```python
import coremltools

model = coremltools.models.MLModel('czech-sentiment-analysis.mlmodel')

result = model.predict({"text": "Ahoj světě!"}) 
result_label = result["label"].
```

### Usage in Swift

If you want to use the model in your Swift app, simply drag the model file into your project in **Xcode**. A wrapping class will be generated automatically, on top of which you will be able to use the model. It is as simple as:

```Swift
import NaturalLanguage
import CoreML

let mlModel = try czech_sentiment_analysis(configuration: MLModelConfiguration()).model
        
let sentimentPredictor = try NLModel(mlModel: mlModel)
sentimentPredictor.predictedLabel(for: "Ahoj světě!")
```
