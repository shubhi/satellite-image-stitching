# Mosaic Satellite Image Stitching using Hadoop MapReduce


## Abstract:

Satellite images depicting the Earth’s surface received at the ground station are obtained by observatories taking pictures while moving along a predefined orbit around the Earth. These images extracted after multiple rotations are called mosaics or tiles. Due to current technological restrictions, mosaics are unable to capture an object as a whole. Thus, to extract a concerned subject in a singular image, image stitching is implemented. Images that are obtained from observatories are generally too humongous in size such that simple image stitching in an image processing environment cannot be implemented on these Big Data Images.

The aim of this project is to develop a two-step Map Reduce framework for the stitching of satellite images wherein objects or required observatory fields fall in two different images, thus providing way for further processing, such as image recognition, classification, etc. The proposed system enables recognition and extraction of objects whose parts fall in separate satellite mosaic images. However, this is a time and resource consuming process. The major aim of the study is improving the performance of the image stitching processes by utilizing big data framework. To realize this, the application architecture consists of a preprocessing step, a mapper function and a reduce function. The preprocessing steps converts the two images to bitmaps and string format to make the suitable for Map Reduce functions. The mapper function creates new space for images. Finally, the reduce function using the out of the mapper as an input, calculates the maximum number of black pixel overlaps between the images and obtains the best possible matching position for the images. The overlapping images are combined with the help of a merging algorithm. 

Stitching of satellite mosaics are often implemented in various scientific domains such as remote sensing, geophysics, map engineering and cartography, and in many application areas such as object recognition /extraction /tracing, spatial analysis, 3D imaging, etc. With further processing the obtained results can be used in image processing, image classification, Feature extraction, mapping, etc.


## System Design:

This study implements the combining the mosaic images with reference to the coordinate most commonly intersecting between each other. The algorithm developed works on a single node. The system is developed in accordance with a MapReduce framework. The application architecture consists of a preprocessing step, a mapper function and a reduce function. The preprocessing steps converts the two images to bitmaps and string format to make the suitable for Map Reduce functions. The mapper function creates new space for images. Finally, the reduce function using the out of the mapper as an input, calculates the maximum number of black pixel overlaps between the images and obtains the best possible matching position for the images. The overlapping images are combined with the help of a merging algorithm.


## Implementation:

1. The developed application retrieves the file path of the images as input values from the user. 

2. After reading the files, the images are preprocessed and two sets are created, one for merge coordinate calculation and the other for the final image merge. The first set (S1) consists of the image matrices in String format. The second set (S2) consists of the image matrices which undergo Theresholding to obtain bitmaps which are then represented in String format. 

3. The map function accepts image matrices img1 and img2 in S2 and returns img2newspace matrix which consist of img2 defined in a new space that accommodates for all possible combinations of img2 with img1. Suppose the images have size (axb), the resultant img2newspace has size (3a-2) x (3b-2). 

4. The reduce function takes img1 and img2newspace as inputs to calculate the maximum number of black pixel overlaps. Which in turns helps determine the best coordinate for merge. 

5. Using the output from the above, a merge operation combines the images in S1 to obtain the complete stitched image. 


## Suggestions and Conclusion:

1. The above was a theoretical study of the combination of Big Data Analytics and Image Processing applied in the field of Satellite and Observatorial Analysis.

2. The output of the implementation can result in either the binary image or with better image segmentation in the original colored form for the stitched image.  

3. The same can be used in object detection, image classification, recognition, mapping and other divisions.  

4. With more complex algorithms, the system can also be modified further to stitch multiple images, taken from different source points that would accordingly have different sizes and oriented in multiple different ways. 

5. The objective of this project, to develop a theoretical implementation of Apache Hadoop MapReduce in a real-world application, has been achieved. 


## References:

1. Kuiler, Erik W. "From Big Data to Knowledge: An Ontological Approach to Big Data Analytics." Review of Policy Research 31, no. 4 (2014): 311-318. 

2. Bonny, M.Z., Uddin, M.S., 2016. Feature-based image stitching algorithms. IEEE, pp. 198–203. doi:10.1109/IWCI.2016.7860365. 

3. Chia-Yen Chen, 1998. Image Stitching Comparisons and New Techniques.  

4. Eken, S., Sayar, A., 2016. A MapReduce based Big-data Framework for Object Extraction from Mosaic Satellite Images, In IoTBD 2016 International Conference on Internet of Things and Big Data (Doctoral Consortium), pp. 14-18. 

5. Pravenaa, S., Menaka, R., 2016. A Methodical Review on Image Stitching and Video Stitching Techniques. Int. J. Appl. Eng. Res. 11, 3442–3448. 
