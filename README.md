# cs6910-Assignment-3 [CS20M005, CS20M016]
-

We have implemented a code that implements Reccurent Neural Network on a subset of dakshina dataset with the following functionalities..<br/><br/>
```
Optimizers               :Adam,RMSProp
Batch size               :64
Cell Type                :LSTM,GRU,RNN
Initialization           :Random
Beam Search              :0,3,5,6
```
We have also used the following as the hyperparameters.<br/><br/>

* *Dropout*                : The Dropout layer randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.<br/><br/>
* *Reccurrent Dropout*     : 
* *Beam Search*            :
* *Cell Tyoe*              :

At dense layer we have used "softmax" as the activation function.<br/><br/>
The implementation is linked with wandb and hyper parameter tuning can be done effectively by changing the values of sweep confiiguration in the script. The configuration used for parameter searching are as follows.<br/><br/>
'epoch' : [2,5,10,15,20]
'batch_size': [64]
'dropout' : [0.1,0.01,0.0]
'recc_dropout' : [0.1,0.01,0.0]
'beam_search' : [0,3,5,6]
'layers' : [3,4]
'hidden_neurons' : [64,126,256]
'cell_type' : ['RNN','GRU','LSTM']
'optimizer_fn' : ['adam','rmsprop']
