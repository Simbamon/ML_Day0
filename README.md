# Scikit-learn

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

Supervised Learning  
```
Uses labeled inputs (meaning the input has a corresponding output label) to train models and learn outputs
```
One-hot Encoding
```
A method to feed nominal data (no inheret order - i.e. countries, comapnies, etc.) into the machine to develop machine learning model

Example
[USA, India, Canada, France] -> USA - [1, 0, 0, 0], India - [0, 1, 0, 0], Canada - [0, 0, 1, 0], France - [0, 0, 0, 1]
The rest are going to be [0, 0, 0 ,0]
```