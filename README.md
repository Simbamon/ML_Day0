# Machine Learning Day 0

## How to set up conda in VSCode

Visit the official [Anaconda webpage](https://www.anaconda.com/) and download Anaconda Distribution

Once the download is finished, open Anaconda Prompt and type
```
conda install ipykernel
```

Open up the Visual Studio Code and set `Select Python Interpreter` to conda's python  
`Example:`
```
~/anaconda3/python.exe
```

After that, click View -> Command Palette (Ctrl+Shift+P) -> and type "new notebook"
to create blank Jupyter notebook on VSCode

## Extra Notes

### This github page is based on this [FCC Youtube Video](https://www.youtube.com/watch?v=i_LwzRVP7bg) 


Supervised Learning  
```
Uses labeled inputs (meaning the input has a corresponding output label) to train models and learn outputs
```
Features
```
Qualitative - categorical data (finite number of categoreis or groups)
    Nominal Data: no inheret order - i.e. countires, companies, etc.
    Ordinal Data: inheerent order - i.e. age group, satisfaction rating, etc.

Quantitative - numerical valued data
    Discrete: integer data - i.e. number of pen, etc.
    Continuous: all real-number data - i.e. length, temperature, etc.

All of these data become a Feature Vector that feeds into the Machine Learning Model to predict an output
```

One-hot Encoding
```
A method to feed nominal data into the machine to develop machine learning model

Example
[USA, India, Canada, France] -> USA - [1, 0, 0, 0], India - [0, 1, 0, 0], Canada - [0, 0, 1, 0], France - [0, 0, 0, 1]
The rest are going to be [0, 0, 0 ,0]
```

Supervised Learning Tasks
```
Classification - predict discrete classes
    Multiclass Classification - Multiple classification
        i.e. Classifying food, animal, plant species etc.
    Binary Classification - Only two classification
        i.e. Classifying [hot dog/not hot dog], [positive/negative], [spam/not spam]

Regression - predict continuous values
    i.e. stock price, temperature, housing price
```

Supervised Learning Dataset
```
Each row = different sample in the data
Each column = different feature, except the one that is going to be an output label

X(Feature matrix) and Y (Labels/targets vector)

Divide the whole dataset into three dataset
    Training dataset - Feed this dataset into the model
    Validation dataset - used as a reality check during/after training to ensure model can handle unseen data
    Testing dataset - used as to check how generalizable the final chosen model is
```

Loss Functions
```
L1 Loss
    loss = sum(|Y(real) - Y(Predicted)|)
L2 Loss
    loss = sum(squared(Y(real) - Y(Predicted)))
Binary Cross-Entropy Loss
    loss = -1 / N * sum(Y(real)*log(Y(predicted)) + (1-Y(real)) * log((1 - Y(predicted))))

*Loss decreases as performance gets better
```

Metrics of Performance - Accuracy
```
Prediction      Actual        
Apple           Apple         O 
Orange          Orange        O
Orange          Apple         X
Apple           Apple         O

Accuracy of this model is 3/4, or 75%
```

K-nearest neighbors

```
Look at what's around you and take the label of the majority that's around me
K is the number of neighbors you are going to use to determine the value (usually 3 to 5)
When you decide the number of K, you look at the nearest K number of data around the point and get the majority

K-nearest neighbors can be extrapolated to high dimension as well
```

Precision and Recall

Check this [Wikipedia Page](https://en.wikipedia.org/wiki/Precision_and_recall) for detail

Naive Bayes

```
In order to understand the Naive Bayes, you need to understand conditional probability and bayes rule
Used Covid test result as an example (Check https://youtu.be/i_LwzRVP7bg?t=3515 for detail)

Probability
    Q: What is the probability of having covid given a positive test?
    P(Covid|+Test) = 531/551 = 96.4%

Bayes Rule
    P(A|B) = P(B|A)*P(A)/P(B)

    B = Condition

    P(False Positive) = 0.05
    P(False Negative) = 0.01
    P(Disease) = 0.1
    P(Disease|(+)Test)

    * False Positive is when you test positive, but you don't have the disease
    * False Negative is the oppsoite of False Positive

```
## FIXES

- **bash: conda: command not found**

        Get the folder directory of /anaconda3/etc/profile.d
        Right click and open Git Bash:
            $ echo ". ${PWD}/conda.sh" >> ~/.bashrc
        Reopen Git Bash:
            $ conda activate
        Conda is now activated in Git Bash

- **ModuleNotFoundError: No module named 'imblearn'**

        In Git Bash:
            $ conda install -c conda-forge imbalanced-learn
        to install imblearn module
