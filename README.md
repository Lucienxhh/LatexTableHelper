# LatexTableHelper
A helper programmed in Python for latex table generation, providing alignment policy for integers and conversion policy to percentage for floats.

## An example code for prediction indicators

```
from LatexTable import *
matrix = [
    [0.2566, 0.3146, 0.2334, 0.7593], 
    [0.1344, 0.0893, 0.3094, 0.3239], 
    [0.3364, 0.2585, 0.1349, 0.1432]
]
firstColumn = ['dataset1', 'dataset2', 'dataset3']
avgs = avgEachColumn(matrix)
matrix = insertRow(matrix, avgs, len(matrix))
firstColumn.append('Average')
matrix = insertColumn(matrix, firstColumn, 0)
writeTable(matrix)
```
results can be seen in table.txt:
```
dataset1 & 25.66\% & 31.46\% & 23.34\% & 75.93\%\\
dataset2 & 13.44\% & \enspace8.93\% & 30.94\% & 32.39\%\\
dataset3 & 33.64\% & 25.85\% & 13.49\% & 14.32\%\\
Average & 24.25\% & 22.08\% & 22.59\% & 40.88\%\\
```
then add some basic structures and compile this latex code
```
\begin{table*}[htbp]
\caption{result}
\centering
\renewcommand{\arraystretch}{1.5}
\begin{tabular}{c|c|c|c|c}
\hline
 dataset & precision & recall & f1-score & auc \\
\hline
dataset1 & 25.66\% & 31.46\% & 23.34\% & 75.93\%\\
dataset2 & 13.44\% & \enspace8.93\% & 30.94\% & 32.39\%\\
dataset3 & 33.64\% & 25.85\% & 13.49\% & 14.32\%\\
\hline
Average & 24.25\% & 22.08\% & 22.59\% & 40.88\%\\
\hline
\end{tabular}
\end{table*}
```
![image](https://user-images.githubusercontent.com/72843445/224525908-636b433c-5de5-48c7-8e66-e745306548cb.png)

## An example code for dataset desciption

```
matrix = [
    [1234, 1234, 2334, 75], 
    [1344, 893, 3094, 9], 
    [364, 2585, 1349, 1432]
]
firstColumn = ['dataset1', 'dataset2', 'dataset3']
sums = sumEachColumn(matrix)
matrix = insertRow(matrix, sums, len(matrix))
firstColumn.append('Total')
matrix = insertColumn(matrix, firstColumn, 0)
writeTable(matrix)
```
results can be seen in table.txt:
```
dataset1 & 1,234 & 1,234 & 2,334 & \;\enspace\enspace75\\
dataset2 & 1,344 & \;\enspace893 & 3,094 & \;\enspace\enspace\enspace9\\
dataset3 & \;\enspace364 & 2,585 & 1,349 & 1,432\\
Total & 2,942 & 4,712 & 6,777 & 1,516\\
```
then add some basic structures and compile this latex code

```
\begin{table*}[htbp]
\caption{result}
\centering
\renewcommand{\arraystretch}{1.5}
\begin{tabular}{c|c|c|c|c}
\hline
 dataset & class num & commits & stars & method num \\
\hline
dataset1 & 1,234 & 1,234 & 2,334 & \;\enspace\enspace75\\
dataset2 & 1,344 & \;\enspace893 & 3,094 & \;\enspace\enspace\enspace9\\
dataset3 & \;\enspace364 & 2,585 & 1,349 & 1,432\\

\hline
Total & 2,942 & 4,712 & 6,777 & 1,516\\
\hline
\end{tabular}
\end{table*}
```
![image](https://user-images.githubusercontent.com/72843445/224526211-01ae5170-42d1-4f2f-baa6-b5b31534184f.png)
