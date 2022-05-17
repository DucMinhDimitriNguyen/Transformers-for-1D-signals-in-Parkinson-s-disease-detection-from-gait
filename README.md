
# Transformers for 1D signals in Parkinson’s disease detection and severity prediction from gait

## Prerequisites

- Python 3.7 
- CPU or  NVIDIA GPU + CUDA CuDNN 
- Install the prerequisite's libraries with ```pip install -r requirements.txt```

## Dataset

The dataset used in the paper is from Physionet. It can be downloaded from (1). A sample of the dataset is available in the subfolder data. 

## Getting Started

The entry point is ```train.py``` file. It has 3 arguments: 
  - input_data: Input folder containing the dataset. 
  - exp_name: type of experiment to run: 
      - 'train_classifier': Run the cross-validation experiment for Parkinson detection. 
      - 'train_severity': Run the cross-validation experiment for Parkinson severity prediction using the UPDRS scale. 

Once executed, the algorithm will generate the following output files:

    ├── output (dir)
        ├── exp_name_Day_Month (when the program is launched) 
            ├── hour_minutes (when the program is launched)  
                ├──  weights.hdf5 : weights of the model
                ├──  res_seg.csv: results of accuracy, sensitivity and specificity by segments.
                ├──  res_pat.csv: results of accuracy, sensitivity and specificity by patients. 
                ├──  training_i.csv: training loss and accuracy for each fold i. For 10-fold cross-validation, 10 files. 
                ├──  model.json: Model architecture (keras)
                ├──  gt.csv: and pred.csv  ( for severity prediction) ground truth level and prediction level for each patient.
                ├──  confusion_matrix.csv: Confusion matrix for severity prediction
    
## References

(1) https://physionet.org/content/gaitpdb/1.0.0
    
    
                
