# This is a python tips page

## Opening files in Python with OS Library

```py
import os

# reading data
with open('data.txt', 'r') as f:
    data = f.read()

# writing data
with open('data.txt', 'w') as f:
    data = 'some data to be written to the file'
    f.write(data)

# list of all the files in a directory
os.listdir('my_directory/')

```

## List comprehension with IF ELSE condition

```py

# Only IF
[i*20 for i in range(1,20) if i >10]

#-------------result------------
# [220, 240, 260, 280, 300, 320, 340, 360, 380]


# If ELSE
[ i*20 if i >10 else i for i in range(1,20) ]

#----------------result-----------------
# [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 220, 240, 260, 280, 300, 320, 340, 360, 380]

```