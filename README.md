# cs6910-Assignment-3 [CS20M005, CS20M016]

The code RnnWandB.ipynb implements Reccurent Neural Network on a subset of dakshina dataset with the following functionalities..<br/><br/>
```
Optimizers               :Adam,RMSProp
Batch size               :64
Cell Type                :LSTM,GRU,RNN
Initialization           :Random
Beam Search              :0,3,5,6
```
Funtions used:
-
 
* *Dropout*                : The Dropout layer randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.<br/><br/>
* *Reccurrent Dropout*     : Just as with regular dropout, recurrent dropout has a regularizing effect and can prevent overfitting. It's used in Keras by simply passing an      argument to the LSTM or RNN layer.<br/><br/>
* *Beam Search*            : The beam search strategy generates the translation word by word from left-to-right while keeping a fixed number (beam) of active candidates at each time step. By increasing the beam size, the translation performance can increase at the expense of significantly reducing the decoder speed.<br/><br/>
* *Cell Type*              : 3 types of Recurrent Neural network cells- LSTM, GRU and Simple RNN.<br/><br/>

At dense layer we have used "softmax" as the activation function.<br/><br/>
The implementation is linked with wandb and hyper parameter tuning can be done effectively by changing the values of sweep confiiguration in the script. The configuration used for parameter searching are as follows.<br/><br/>
```
'epoch'          : [2,5,10,15,20]
'batch_size'     : [64]
'dropout'        : [0.1,0.01,0.0]
'recc_dropout'   : [0.1,0.01,0.0]
'beam_search'    : [0,3,5,6]
'layers'         : [3,4]
'hidden_neurons' : [64,126,256]
'cell_type'      : ['RNN','GRU','LSTM']
'optimizer_fn'   : ['adam','rmsprop']
```

The code Attention.ipynb implements Reccurent Neural Network along with attention mechanism, on a subset of dakshina dataset with the following functionalities..<br/><br/>
Attention Mechanism is used to improve the performance of the Encoder-Decoder RNN on machine translation.<br><br/>
We have used the following functionalities for the attention model.<br><br/>
```
Optimizers               :Adam,RMSProp
Batch size               :32,64
Cell Type                :LSTM,GRU,RNN
Initialization           :Random
Beam Search              :3,4,5,6
```
Best Models
-
The best configuration that gave maximum accuracy for the RNN model is :</br>
``` 
Word level Validation Accuracy : 52.7%

'epoch'         :15
'batch_size'    : 64
'dropout'       : 0.1
'beam_search'   : 6
'layers'        : 3
'hidden_neurons': 256
'recc_dropout'  : 0.1
'cell_type'     : GRU
'optimizer_fn'  : adam


The best configuration that gave maximum accuracy for the Attention model is :</br>
``` 
Accuracy : 54.8%

'epoch'            : 10
'batch_size'       : 64
'dropout'          : 0.01
'recc_dropout'     : 0.05
‘beam_search'      : 6
‘latent dimensions': 256
‘cell_type'        : 'GRU'
'optimizer_fn'     : 'rmsprop'
```


