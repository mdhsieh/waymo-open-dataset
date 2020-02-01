# waymo-open-dataset
Training a model from the Tensorflow Object Detection API with images from the Waymo Open Dataset.

Steps are described in the Waymo Image Recognition and Training PDF.
1. Download the faster_rcnn_resnet101_coco model folder from the Tensorflow Object Detection API Github. Clone the repository.
Link: https://github.com/tensorflow/models/tree/master/research/object_detection
2. The model is pretrained, and you can see image recognition results from Good_object_detection_tutorial.ipynb
3. Open and run Copy_of_Waymo_Open_Dataset_Tutorial.ipynb to generate train and test CSV files.
4. Create two folders with your train and test images, respectively.
5. Generate your train TFRecord by adding the paths to your train CSV file and train images folder. Repeat for the test TFRecord.
See this link: https://pythonprogramming.net/creating-tfrecord-files-tensorflow-object-detection-api-tutorial/
6. Create a pipeline.config to do training. The label map should be set to mscoco_label_map_pbtxt, and the train and test config paths 
should be set to the TFRecords.
The pipeline config file is described here: https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/configuring_jobs.md
7. Run training from the repository with the run-training script.
