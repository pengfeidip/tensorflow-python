# tensorflow-python
this is a test floder of tensorflow -python codes based on jupyter notebook 



**2018-7-24-11:25:36** 

更新一下readme, 熟悉一下git/github的用法



**2018-7-27 10:36:03** 

- I create a  new neural network which  architecture is similar to LeNet , including  **inference ** and **training ** 
- the  file name is **myNet_infer, myNet_train, myNet_eval**






**Version_1**: 

folder: version _1, include myNet_infer, myNet_train, myNet_eval

- base : 

  - after 30,000 iterations, the result is not good , .

  - in training set : **5799/59500 , 9.746% accuracy** 

  - in test set: **982/10000, 9.82% accuracy**

  - the ipynb file in the folder named **version _1** 
- change 1:  

  - change the learning rate , from 0.01 to 0.001
  - result is not imporved
- change 2:
  - change the weights initialization :
    - **version_1:base**  tf.truncated_normal_initializer()
    - **version_1:change 1**  tf.truncated_normal_initializer(stddev=0.1)
  - result: 
    - in training set: **59275/59500  accuracy : 99.62%**
    - in test set: **9882/1000  accuracy : 98.82%** 
- $\color{Red}{\text{Summary}}$ : 
  - base: **high bias, may be, the neural network has a  problem ** 
  - change 1: high bias , may be the neural network has a  problem 
  - change 2: weights initialization is very important !!! $\color{Red}{\text{★}}$ 

**Version_2**: 

folder: version _2, include myNet_infer, myNet_train, myNet_eval

**change neural network architecture** , i.e. the file myNet_infer is different to **version_1**, others are same,.

but I think there is not much difference between **version_1:base** and  **version_2 :base** in terms of architecture

- base :
  - result is excellent !!!
  - in training set **59474/59500 , accuracy : 99..96%**
  - in test set **9877/10000. accuracy : 98.77%**
  - Comparison with **version_1:base** , this result of **version_2:base**  means , the problem is NN architecture 
- change 1:
  - change the **weights initialization:**
    - **version_2:base**  tf.truncated_normal_initializer(stddev=$\color{Red}{\text{0.1}}$ )
    - **version_2:change 1**  tf.truncated_normal_initializer(), means stddev=$\color{Red}{\text{1.0}}$ 
  - result: 
    - in training set: **1118/59500 accuracy:  1.87%**
    - in test set: **1135/10000   accuracy:  11.35%** 
- change 2:
  - change the **weights initialization :**
    - new initialization :   tf.truncated_normal_initializer(stddev=$\color{Red}{\text{0.5}}$ )
  - result:
    - in training set: **6214/59500  accuracy :10.44%**
    - in test set:   **1028/10000   accuracy :  10.28%**
- $\color{Red}{\text{Analysis}}$ :  weights initialization is very important

**2018-8-4 08:27:15**

- **reuse_myNet.ipynb **: reusing the my_Net by restore the **graph** and the **parameters**

