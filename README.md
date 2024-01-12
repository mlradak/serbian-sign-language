# Serbian Sign Language Alphabet (SSL) - NumPy DATASET
## All 30 Serbian alphabets | Distributed in Folders and Described with key points

This SSL Dataset can be used to create Machine Learning models: Games, Educational Material, Communication Software, ...

![image](https://github.com/mlradak/serbian-sign-language/assets/17915461/e5f7a2ed-35bd-4268-a91f-4d2469ca3e04)
_Figure 1. NumPy file structure used in SSL dataset_


## How to load a NumPy file from SSL Dataset and use it?
Dataset can be used for creating machine learning models.


```
import numpy as np
import os
import time

def convert_npy_file_data_to_csv(file_name):
    numpy_array = np.load(file_name)
    total_values = len(numpy_array)
    ELEMENTS_IN_ONE_FRAME = 33*4 + 21*3 + 21*3
    counter = 0
    frame_number = 0
    all_frames = []
    for j in range(int(len(numpy_array)/(ELEMENTS_IN_ONE_FRAME))):
        frame_number += 1
        data_row = []
        for i in range(ELEMENTS_IN_ONE_FRAME):
            data_row.append(numpy_array[i+j*ELEMENTS_IN_ONE_FRAME])
        all_frames.append(data_row)
    print(all_frames)
    np.savetxt(f"{file_name}.csv", all_frames, delimiter=",")  # EXPORT DATA TO A .csv FILE
    print(f"Successfully saved {file_name}.csv file.")
    return

if __name__ == "__main__":
    file_name = "..\\SSL Program\\D\\17039342851960452-XVID.npy"
    convert_npy_file_data_to_csv(file_name)
```

