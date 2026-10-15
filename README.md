# Breast Cancer ANN — Basic Assignment

Source: https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data

The original Kaggle data.csv is included. The notebook follows Basic.ipynb and Untitled5.ipynb with simple separate cells, an exact 16 ReLU -> 8 ReLU -> 1 sigmoid network, Adam, binary_crossentropy, and 30 epochs. All notebook cells were executed, and accuracy was checked against saved predictions.

## Run on Kaggle
1. Open the source dataset page and create a new notebook.
2. Import Breast_Cancer_ANN_Basic.ipynb through the File menu.
3. Attach the breast cancer dataset under Input and confirm data.csv is present.
4. Run all cells. The loading cell searches Kaggle input automatically; if several attached datasets contain data.csv, select the correct path from the printed list.
5. Save Version with outputs. Make the notebook public if required by your teacher, then submit YOUR notebook URL.

## Run on Colab
1. Open https://colab.research.google.com/ and upload Breast_Cancer_ANN_Basic.ipynb.
2. Upload data.csv through the Files sidebar.
3. Run cells in order. If TensorFlow is missing, run %pip install tensorflow in a new cell.

## Submit on GitHub
1. Create a repository, such as breast-cancer-ann.
2. Extract the project ZIP.
3. Add file > Upload files: upload the notebook, README, data.csv and outputs folder.
4. Commit the files. Submit your repository URL with your saved Kaggle notebook URL.

## Data and evaluation
- Original: 569 rows, 30 numeric measurement features, one diagnosis column, an id, and an empty column.
- Drop id and the empty column. No remaining missing values or duplicates; all rows remain.
- Encode B=0 and M=1. Split into 364 training, 91 validation, 114 test rows, stratified with seed 42.
- Fit StandardScaler on the 364 training rows only.
- Train once for exactly 30 epochs, batch size 32. No test-based tuning or early stopping.
- Validation is used for the learning curve; the test set is evaluated at the end.
- Run versions and CPU execution settings are recorded in outputs/run_details.json. Numerical results may vary across versions/hardware.

## Results
The ANN achieved 97.37% test accuracy (111 correct predictions out of 114) after 30 epochs. The test set was kept separate from both training and validation, and scaling was fitted only on training rows. This is a classroom classification result on one split, not evidence of clinical readiness; results may vary across TensorFlow versions or hardware.
