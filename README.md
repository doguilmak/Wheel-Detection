<h1 align=center><font size = 5>Wheel Detection with ResNet50 and Object Detection API</font></h1>

<img  src="https://www.tirerack.com/content/dam/tirerack/desktop/Open_Graph_Images/og_TireWheelPkg.jpg" height=500 width=1000 alt="TireRack">

<small>Picture Source:<a  href="https://www.tirerack.com/content/tirerack/desktop/en/packages.html"> TireRack</a>

<br>

<h2>Description</h2>

<p>Manually checking each tire can be sped up by employing an automated camera system that captures images of vehicles as they drive past. Machine learning models can process these images to determine are there any tires or not. This dataset consists of images captured by an <i>OpenMV Cam H7 Plus</i>. It includes 900 <i>240x240</i> grayscale images. Provided is a directory tire-dataset that contains the entire dataset as .jpg images.

<i>In terms of diversity, this project has a relatively limited perception. If you want to diversify, you are free to modify.</i> In addition, I just want to thank you for all the help Mr. <b>Laurence Moroney</b>! I learned a lot from you!</p>

<br>

<h2>Acknowledgements</h2>

<p>This dataset has been referred from <a  href="https://www.kaggle.com/datasets/rhammell/full-vs-flat-tire-images">Kaggle</a>.</p>

<br>

<h2>Objective:</h2>

<ul>
	<li>Installling necessery libraries and models.</li>
	<li>Build wheel detection model with ResNet50</li>
	<li>Build ground truth boxes with <code>colab_utils.annotate</code>.</li>
</ul>

<br>

<h2>Keywords</h2>

<ul>
	<li>Automobile and Vehicle</li>
	<li>Object Detection</li>
	<li>Computer Vision</li>
	<li>SSD ResNet50</li>
	<li>Object Detection API</li>
</ul>

<br>

<h2>Dataset License</h2>

<ul>
	<li>CC BY-NC-SA 4.0</li>
</ul>

<br>

<h2>Refecences</h2>

<ul>
	<li><a  href="https://www.kaggle.com/datasets/rhammell/full-vs-flat-tire-images">Kaggle</a></li>
	<li><a  href="https://laurencemoroney.com/">Laurence Moroney</a></li>
	<li><a  href="https://www.coursera.org/learn/advanced-computer-vision-with-tensorflow#instructors">Advanced Computer Vision with TensorFlow</a></li>
	<li><a  href="https://github.com/tensorflow/models">TensorFlow GitHub</a></li>
</ul>

<br>  

<h2>Objective for this Notebook</h2>  

<p>The aim of this project is to create a tire detection model based on the data. In the creation of this object detection model, <i>ResNet50</i> and <i>Object Detection API</i> have been used.</p>

<img src="wheel_test.gif"/>

<br>

<h2>Required Inputs</h2>

<p>Install TensorFlow</p>
	
	!pip install -U --pre tensorflow=="2.2.0"

<p>Clone the tensorflow models repository if it doesn't already exist</p>

	if  "models"  in pathlib.Path.cwd().parts:
		while  "models"  in pathlib.Path.cwd().parts:
			os.chdir('..')
	elif  not pathlib.Path('models').exists():
		!git clone --depth 1 https://github.com/tensorflow/models

<p>Install the Object Detection API</p>

	%%bash
	cd models/research/
	protoc object_detection/protos/*.proto --python_out=.
	cp object_detection/packages/tf2/setup.py .
	python -m pip install .

<p>Download SSD ResNet50 v1</p>

	!wget http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_resnet50_v1_fpn_640x640_coco17_tpu-8.tar.gz
	!tar -xf ssd_resnet50_v1_fpn_640x640_coco17_tpu-8.tar.gz
	!mv ssd_resnet50_v1_fpn_640x640_coco17_tpu-8/checkpoint models/research/object_detection/test_data/

<br>

<h2>Contact Me</h2>

<p>If you have something to say to me please contact me:</p>

<ul>
 <li>Twitter: <a href="https://twitter.com/Doguilmak">Doguilmak</a></li>
 <li>Mail address: doguilmak@gmail.com</li>
</ul>
