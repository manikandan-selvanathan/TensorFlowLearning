# TensorFlowLearning


Installation Of Tensor Flow: <br/>
Windows:<br/><br/>

Download Python 64-bit of 3.5.x or 3.6.x (As of now (1st march 2018) Tensor flow only supports on 64 bit of 3.6 and 3.5)<br/>
Set Environment Path <br/>
Couple of paths below.<br/>

For Python---->C:\Users\----\AppData\Local\Programs\Python\Python35   
For PIP---->C:\Users\----\AppData\Local\Programs\Python\Python35\Scripts

Open CMD and Run command below
``` CMD
pip3 install --upgrade tensorflow
```
This will take a while to install tensor flow.




Run Below small program to check everything works. Open CMS and Type "python".<br/>
It will open python cmp. And run below script.
``` Python
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```


