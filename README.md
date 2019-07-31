# TensorFlowLearning


Installation Of Tensor Flow: <br/>
Windows:<br/><br/>

Download Python 64-bit of 3.5.x or 3.6.x (As of now (1st march 2018) Tensor flow only supports on 64 bit of 3.6 and 3.5)<br/>
Set Environment Path <br/>
Couple of paths below.<br/>

Install Curl
https://curl.haxx.se/windows/


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

Install tensorflow-hub
``` CMD
pip install tensorflow-hub
```


Redirect to TensorFlow Folder:
cd /Users/lennox/Desktop/ImageTrainingFinal/tensorflow

Activate: 
source ./bin/activate

Retrain:

python retrain.py \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \ 
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/Bikes

Optimize

python -m tensorflow.python.tools.optimize_for_inference \
  --input=tf_files/retrained_graph.pb \
  --output=tf_files/optimized_graph.pb \
  --input_names="Mul" \
  --output_names="final_result"

Mobile Mandatory
Round:

python -m scripts.quantize_graph \
  --input=tf_files/optimized_graph.pb \
  --output=tf_files/rounded_graph.pb \
  --output_node_names=final_result \
  --mode=weights_rounded

 Optional Copying files to Asset folder

cp tf_files/optimized_graph.pb /Users/lennox/productinformation/app/src/main/assets/graph.pb
cp tf_files/retrained_labels.txt /Users/lennox/productinformation/app/src/main/assets/retrained_labels.txt


