# Log3C (FSE 2018 accepted paper)


Log3C is a general framework that identifies service system problems from system logs. It utilizes both system logs and system KPIs to promptly and precisely identify impactful system problems. Log**3C** consists of four steps: Log parsing, Sequence vectorization, **C**ascading **C**lustering and **C**orrelation analysis. This is a joint work by CUHK and Microsoft Research, Asia. More details are introduced in our paper. 


**Paper title:** Identifying Impactful Service System Problems via Log Analysis 

**Authors:** Shilin He, Qingwei Lin, Jian-Guang Lou, Hongyu Zhang, Michael R. Lyu, Dongmei Zhang


The repository contains the source code of Log3C, including data loading, sequence vectorization, cascading clustering, data saving, and etc. The core part is the cascading clustering algorithm, which groups a large number of sequence vectors into clusters by iteratively sampling, clustering, matching. 


## Prerequisites:
* Python version 3.5 or above
* All required packages are installed
* Windows, Linux or macOS platform

Note: Anaconda (Python 3.5 or above) is highly recommended, all required packages are already installed in Anaconda. You can also install the required packages with the "requirements.txt" by using command:

`pip install -r requirements.txt`

## Installing:
1. Download the project code files with:

`git clone https://github.com/AnonymousPaper/Log3C.git`

2. Go to the project directory

`cd Log3C`

## Usage:

To use the model, open a terminal, change directory to this project code, run the command: 

`python run.py`


## Project Structure:
1. run.py: main entry function, which defines all the required hyper-parameters.
2. cascading_clustering.py: implementation of the cascading clustering algorithm. 
3. dataloader.py: load the input data files into memory
4. save_results.py: save the clustering result into files.

For details, please refer to the code comments.


## Data Format:
* Multiple log sequence matrix files: each file consists of log sequence vectors within a time interval. 
* The KPI data: each KPI value corresponds to the system status of a time interval. 

1. A log sequence matrix at time interval **T0**:

|Log Seq   | Event1 |  Event2 | Event3 | Event4 |   ...  |					 
|:-------: | :----: |:-------:| :-----:| :-----:| :-----:|			
|  **1**   |   2    |    1    |    0   |    2   |   ...  |			
|  **2**   |   3    |    2    |    4   |    1   |   ...  |			
|  **3**   |   2    |    1    |    3   |    3   |   ...  |			
|  ...     |  ...   |   ...   |   ...  |   ...  |   ...  |			
			

Assume that there are N time intervals in total, then we have N such matrixes as well as N KPI values. These K KPI values are stored in one file, which is shown as below.

2. KPI data

|Time Interval | KPI   |
| :----:   | :----: |
| **T0** |  0.05  |
| **T1** |  0.10  |
| **T2** |  0.07  |
| .. |   ...  |

Only one KPI file, which contains N KPI values. 

## Synthetic Data:

The synthetic datasets are available in **[Google Drive](https://drive.google.com/drive/folders/1rbyK15h8alihUfEO68_JSz9F0vQSq3C3?usp=sharing)**, which can be used to validate the cascading clustering algorithm. Descriptions about the datasets can be found in the README.txt file



