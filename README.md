# partial-AUC-C
Code for the concordant partial AUC and the partial C statistic [1]  
Code written by André Carrington and Yusuf Sheikh

This package, partial-AUC-C has been superceded by use of the DeepROC class in the deepROC package, from 'pip install deeproc' or Github here:  
https://pypi.org/project/deeproc/  
https://github.com/Big-Life-Lab/deepROC  
  
Some general introductory information is found here: http://deeproc.org  
  
Citations:  
[1] Carrington AM, Fieguth PW, Qazi H, Holzinger A, Chen HH, Mayr F and Manuel DG. A new concordant partial AUC and partial c statistic for imbalanced data in the evaluation of machine learning algorithms, BMC Medical Informatics and Decision Making 20, 4 (2020) doi:10.1186/s12911-019-1014-6  
  
[2] Carrington AM, Manuel DG, Fieguth PW, Ramsay T, Osmani V, Wernly B, Bennett C, Hawken S, McInnes M, Magwood O, Sheikh Y, Holzinger A. Deep ROC Analysis and AUC as Balanced Average Accuracy Deep ROC analysis and AUC as balanced average accuracy for improved classifier selection, audit and explanation. IEEE Transactions on Pattern Analysis and Machine Intelligence, Early Access, January 25, 2022. doi:10.1109/TPAMI.2022.3145392  
  
## Instructions
Ensure you have a Python 3.7 interpreter.  
Copy files in Python3.7 folder to a local folder.  
Create a subfolder called output.  
Edit the variables (explained below) at the top of the file test_pAUCc.py as input settings.  

python test_pAUCc.py

The program will block (wait) for you to close each plot generated and each plot is saved automatically along with the log file to the output folder using the test number from the test vector or the input file.

## Explanation of variables
  
### Choose one of the following as input:  
useFile             = False  
useSingleTestVector = True  
useAllTestVectors   = False  

### Specify corresponding input parameters:  
fileName            = 'input-matlab/result581.mat'  # a matlab file (or future: csv file) for input  
singleTestVectorNum = 1  # which of 11 test vectors in the function get_ROC_test_scores_labels_ranges below  

### Choose data science parameters:  
rangeAxis           = 'FPR'  # examine ranges (next) by FPR or TPR  
filePAUCranges      = [[0, 0.33], [0.33, 0.67], [0.67, 1.0]]  # ranges, as few or many as you like  
useCloseRangePoint  = True   # automatically alter the ranges to match with the closest points in data  
costs               = dict(cFP=1, cFN=1, cTP=0, cTN=0)  # specify relative costs explicitly (default shown)  
rates               = False                             # treat costs as rates, e.g. cFPR (default False)  

### Choose what to show:  
sanityCheckWholeAUC = True  
showPlot            = True  
showData            = False  
showError           = True  

Created and tested in PyCharm with a Python 3.7 interpreter.  
