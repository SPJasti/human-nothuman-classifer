# human-nothuman-classifer
i have made a binary classifier in (4 hours) which tells if a image has human in it or not .

# check * intern_test_2 (1).ipynb * for step by step execution (link below )
https://github.com/SPJasti/human-nothuman-classifer/blob/master/intern_test_2%20(1).ipynb

i was given the task :
Given a 256x256 image, write a binary classifier to differentiate the given image has a human or not. The approach and the code are more important than the accuracy rate. Please feel free to pick a relevant open dataset for this problem

I used human dataset from https://data.mendeley.com/datasets/t2y7cm69m6/1 

I combined two datasets from the website given below  those were ' open country ' and ' Forest ' :
http://cvcl.mit.edu/database.htm
and created a folder called Nothuman 

NOTE : 
The approach and code was important than the accuracy .
if accuracy was important as well then one should spend more time in finding and creating a datasets with better negatives .

uploaded the folder to google drive 
made a new python 3 notebook -> enabled hardware acceleration (GPU) -> got authorization to access the file 

CODE :  inspired by sentdex
import all necessary modules 
displaying the image and checking the pixel size (here : 5183 X 3456)

 resizing into 256*256 

creating training dataset 

shuffling using random.shuffle (why you may ask ? -> cross validation , minimum value of a loss function )
refer to the link below for further understanding  :
https://datascience.stackexchange.com/questions/24511/why-should-the-data-be-shuffled-for-machine-learning-tasks

using pickle : 
why ? - Pickling is a way to convert a python object (list, dict ) into a character stream 

i tried optimizing the model but we could ease on the accuracy hence just tested in my own leisure time 

# building neural network : 
starting off with a convolutional layer
adding a convolutional layer   (2 * 64 Neural network  )
window size - 3x3
dense layer of 64 nodes and before that we have to flatten 
because from CNN we get 2D array and dense accepts 1D array 

output layer :
dense - activation ('sigmoid')

loss='binary_crossentropy'
optimizer='adam'
metrics=['accuracy']

batch size - how many images to pass at once 
validation split -a set of examples used to tune the parameters of a classifier
epochs - The number of epochs is a hyperparameter that defines the number times that the learning algorithm will work through the entire training dataset .

saving the model created as ' 64X3-CNN.model '

############################################################

testing/ checking the created model :

feel free the check with any photo of your choice . 

# sai praneeth jasti 
# saipraneeth.jasti@vitap.ac.in
