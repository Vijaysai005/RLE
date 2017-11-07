# RLE
RLE-RunLengthEncoding

#run "python setup.py install"

"""
RLE-RunLengthEncoding is a framework in python
using pandas and groupby

It is majorly used to compress the data by finding 
the correct indices required to compress

Example:
--------

input = pd.DataFrame([10, 10, 10, 20, 20, 11, 21, 11, 20, 20, 10, 10], columns=["data"])
or

input = "aabbbaababacccddbbddaa"

or

input = [10, 10, 10, 20, 20, 11, 21, 11, 20, 20, 10, 10]

So, it can take dataframe or list or string as an input for data
compression

rle = Compressor(data_for_rle=input) or RLE(input)
rle.solve(otype=params) or rle.solve(params)

# For output you can check the attributes of RLE.solve method

rle.df will return ~
       length  status  cumsum  start_index  end_index
    0       3      10       3            0          2
    1       2      20       5            3          4
    2       1      11       6            5          5
    3       1      21       7            6          6
    4       1      11       8            7          7
    5       2      20      10            8          9
    6       2      10      12           10         11

rle.start_index will return ~
[0, 3, 5, 6, 7, 8, 10]

rle.end_index will return ~
[2, 4, 5, 6, 7, 9, 11]

"""
