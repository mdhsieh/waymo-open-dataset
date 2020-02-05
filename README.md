# waymo-open-dataset
Training a model from the Tensorflow Object Detection API with images from the Waymo Open Dataset.

Steps are described in the Waymo Image Recognition and Training PDF.
1. Download the first TFRecord file from the Waymo Open Dataset. It will be very large (several GB). Later we will extract the images and bounding box coordinates, creating our own TFRecords, because the provided TFRecords aren't compatible with the Object Detection API. 
2. Download the faster_rcnn_resnet101_coco model folder from the Tensorflow Object Detection API Github. Clone the repository.
Link: https://github.com/tensorflow/models/tree/master/research/object_detection
3. The model is pretrained, and you can see image recognition results from Good_object_detection_tutorial.ipynb
4. Open and run Copy_of_Waymo_Open_Dataset_Tutorial.ipynb to generate train and test CSV files.
5. Create two folders with your train and test images, respectively.
6. Generate your train TFRecord by adding the paths to your train CSV file and train images folder. Repeat for the test TFRecord.
See this link: https://pythonprogramming.net/creating-tfrecord-files-tensorflow-object-detection-api-tutorial/
7. Create a pipeline.config to do training. The label map should be set to mscoco_label_map_pbtxt, and the train and test config paths 
should be set to the TFRecords.
The pipeline config file is described here: https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/configuring_jobs.md
8. Run training from the repository with the run-training script.
