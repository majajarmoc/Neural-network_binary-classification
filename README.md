# Neural-network_binary-classification

One of the many available machine learning techniques commonly used in the process of chemical hazard assessment is the neural network algorithm. The effectiveness of the results obtained based on artificial neural network models is determined by hyperparameters, the tuning (selection) of which can sometimes pose problems.  The topic of my thesis was to evaluate the effect of changing the hyperparameters of a neural network on the effectiveness of a model predicting acute toxicity induced by the presence of structurally diverse organic compounds against a species of Daphnia paddlefish, such as Daphnia magna.
Within the framework of my own research, I developed classification models of chemical structure-biological activity relationships (binary classifier) based on the method of neural networks using different hyperparameters (including different neuron activation functions, number of hidden layers and number of neurons in a layer). Based on a comparative analysis of the obtained results, I defined the optimal (for the analyzed dataset) combination of hyperparameters that offers the most correct classification of compounds due to induced acute toxicity to D. magna.

# Purpose of the work
The purpose of my work was to compare the effects of different hyperparameters (including: the number of hidden layers, the number of neurons per layer, and the neuron activation function used) on the performance of a classification model for predicting acute toxicity induced by the presence of organic compounds against Daphnia Magna.

# Data
In order to achieve the stated goal of my thesis project, I used a dataset on acute ecotoxicity to the aquatic organism D. magna. Experimental data on acute toxicity were collected by the Japanese Ministry of the Environment. The dataset provides information on acute toxicity to D. magna determined for 495 organic compounds. Toxicity was expressed qualitatively with a division into two classes: (1) mildly toxic and relatively non-toxic compounds, and (2) highly and moderately toxic compounds. Classification of a chemical compound into a particular class depends on the value of the medial lethal concentration (LC50) index for that compound. LC50 is a measure of a substance's lethal concentration that determines the concentration level at which 50% of organisms exposed to the substance can be expected to die within a specified exposure time or after a conventional post-exposure period.

# Models
In order to evaluate the effect of changes in neural network hyperparameters on the effectiveness of the classification model, I built a total of five classification models. Two models using the ReLU activation function and one for each of the other activation functions: leakyReLU, GELU and linear activation function. The aforementioned activation functions were used in all layers of the network except the output layer, where the sigmoidal activation function was used.

|     Model    |     Number of hidden   layers (excluding the input and output layers)    |     Number of   neurons in the hidden layer    |     Activation function    |
|--------------|--------------------------------------------------------------------------|------------------------------------------------|----------------------------|
|     1.       |     1                                                                    |     50                                         |     ReLU                   |
|     2.       |     2                                                                    |     25                                         |     ReLU                   |
|     3.       |     2                                                                    |     25                                         |     LeakyReLU              |
|     4.       |     2                                                                    |     25                                         |     GELU                   |
|     5.       |     2                                                                    |     25                                         |     Linear                 |

# Results

Results obtained during the creation of the thesis project. The results in the attached code differ slightly, due to later revisions to the file.

## Training set
|          | Activation  function | Accuracy    | Precision   | Sensitivity | Specificity | F1-score    | MCC         |
|----------|----------------------|-------------|-------------|-------------|-------------|-------------|-------------|
| Model 1. |     ReLU             |     0,81    |     0,75    |     0,76    |     0,84    |     0,75    |     0,60    |
| Model 2. |     ReLU             |     0,81    |     0,76    |     0,72    |     0,86    |     0,74    |     0,58    |
| Model 3. |     LeakyReLU        |     0,77    |     0,68    |     0,75    |     0,79    |     0,71    |     0,53    |
| Model 4. |     GELU             |     0,80    |     0,74    |     0,71    |     0,85    |     0,72    |     0,56    |
| Model 5. |     Linear           |     0,75    |     0,70    |     0,59    |     0,85    |     0,64    |     0,45    |

## Validation set
|          | Activation  function | Accuracy  | Precision | Sensitivity | Specificity | F1-score | MCC  |
|----------|----------------------|-----------|-----------|-------------|-------------|----------|------|
| Model 1. | ReLU                 | 0,85      | 0,71      | 0,87        | 0,84        | 0,78     | 0,67 |
| Model 2. | ReLU                 | 0,87      | 0,74      | 0,90        | 0,85        | 0,81     | 0,72 |
| Model 3. | LeakyReLU            | 0,83      | 0,68      | 0,87        | 0,81        | 0,76     | 0,64 |
| Model 4. | GELU                 | 0,88      | 0,74      | 0,94        | 0,85        | 0,83     | 0,75 |
| Model 5. | Linear               | 0,79      | 0,66      | 0,68        | 0,84        | 0,67     | 0,51 |

# Conclusions

- Overall, Model 4 with the GELU activation function shows the best performance on the validation set with the highest Accuracy, Precision, Sensitivity, Specificity, F1-score, and MCC values.
- Model 2 with the ReLU activation function also performs well, achieving high values for most metrics on the validation set.
- Model 3 with LeakyReLU activation performs decently but falls slightly behind Models 2 and 4.
- Model 1 with ReLU activation is competitive, but its performance is generally lower compared to Models 2 and 4.
- Model 5 with Linear activation function consistently underperforms compared to the other models.
