# kaggle kernels

Recording the journey of kaggle competition.

## Working flow

1. download data set in to local computer via kaggle api, and all datasets & description would be downloaded to "competitions" subfolder of kaggle path configurated 
```bash
kaggle competitions list -s house
kaggle competitions download house-prices-advanced-regression-techniques
```
2. Fork kernel based on reference of the competition or create a brand new one.

3. Create a repo  like this one, as a container for a serial of folders to  different kenerals for different competitions, then cd into that folder.

4. Pull the specific kernel (with meta info) you created in kaggle into local repo folder, like repo/keneral_for_competition1

```bash
kernels pull -m -w jonnyhou/playground
```

5. After localize and adjust the ipynb with datasets, push into kaggle kernel
```bash
kernels push
```
be noted that the datasets location is different in local station or kaggel, so creat extra path to handle the difference in ipynb
```python
import os
import sys
if sys.platform == "linux":
    path = "../input/"
else:
    root = os.getcwd()
    path = os.path.join(root, "../../competitions/house-prices-advanced-regression-techniques/")
    path = os.path.realpath(path)+"/"
train = pd.read_csv(path+"train.csv")
test = pd.read_csv(path+"test.csv")
```
It looks rough, but works by now till a better way found.

## Contents

1. Playground
2. House prices prediction by using linear regression.


## Reference

* ISL-python repo for ISLR
* ml-math

