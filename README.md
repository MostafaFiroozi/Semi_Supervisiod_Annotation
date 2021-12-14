# Semi_Supervisiod_Annotation
This code uses the output of a TensorFlow object detector to produce image annotations (COCO standard XML file) for the rest of dataset.
In most of the object detection projects, producing a gold standard for the model using usual image annotation tools is where most of the pain comes from. It requires a lot of time and anergy to annotate a big dataset of images. <br> 
A lot of automatic online image annotation tools are expensive and not accorate enough. But why not using the inteligence of our own model to alleviate?<br> 
In this approach, I suggest to first annotate a reasonable portion of the dataset, then build a prototype model based on that. Now hawing a detector, you can use this code to draw the bounding boxes around the rest of the dataset, and construct the .xml files for those images. Then you can correct those annotations and build the final model having a wide enough dataset.
## Steps:
1- Clone this repository. <br> 
2- Annotate a reasonable percentage of the dataset using labelimg.
###  :warning: :warning: :warning: Attention( be careful to choose a heterrogeneus subset of the dataset.) <br> 
3-Change the pipeline config path, ckpt path, label_map.pbtxt to the one of your prototype model. <br> 
![image](https://user-images.githubusercontent.com/73081215/145988417-80d1208e-c510-4690-b980-8937b36233d2.png)

4-Change the rout path to where your images are located. <br> 
5-Copy the example .xml file to your disk and define its path in the code.<br> 
6-Set a threshold that you want to consider it as the minimum value of the detection score of an object to consider it for the annotation.<br> 
7-Run the code cells for Semi_Supervisiod_Annotation to produce the .xml file.<br> 
8- As you see, the second poor pussy cat 🙀 is annotated as a dog  🐕 by mistake.
![image](https://user-images.githubusercontent.com/73081215/145986544-520546fe-2c47-402f-88f3-1017a860f61e.png)

7-But don't worry, open labelimg and correct for the mistakes.<br> 
![image](https://user-images.githubusercontent.com/73081215/145987468-7bba6e49-1df4-49e1-9546-c3490294b53b.png)
Now she is corrected!![image](https://user-images.githubusercontent.com/73081215/145987633-5213ab68-c415-4ca2-8101-63a1e637ae11.png)
8-Enjoy building a robust model with a big enough dataset. :dancer: :cake: 🙀 🐶 
