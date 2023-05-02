Download Link: https://assignmentchef.com/product/solved-cosc6373-homework-3-parking-lot-vacancy-detector
<br>
A public infrastructure has various parking lots. The parking lots get completely occupied very often and the public visiting the infrastructure spend too much time looking for a parking space, unaware that the parking lot is completely occupied. They would like to implement an automated solution to convey this information by displaying the number of available parking spaces at the entrance to the parking lot.

<table width="623">

 <tbody>

  <tr>

   <td width="312"> </td>

   <td width="312"> </td>

  </tr>

  <tr>

   <td colspan="2" width="623"></td>

  </tr>

 </tbody>

</table>




These parking lots are overlooked be surveillance cameras. The task is to leverage them to detect and count the empty parking spots.

Data set:

The data set consists of images from three separate parking lots parking1a, parking1b and parking2. Each of the parking has data set sorted for three different scenarios cloudy, rainy and sunny. Each single day is represented by the folder, for example the folder (e.g. PKLot/parking/cloudy/2012-12-12/) contains multiple snapshot images (like 2012_12_12_10_00_05.jpg) and the corresponding ground truth file (like 2012_12_12_10_00_05.xml).







Ground Truth(.xml)

Each image in the parking2 has 100 annotated parking spaces (see image below), along with the location, and occupancy information of the parking spot (Every image is supplemented with a ground truth file. For example (parking2/cloudy/2012-09-12/2012-09-12_06_05_16.jpg) has the ground truth file (parking2/cloudy/2012-09-12/2012-09-12_06_05_16.xml).




XML File description:

<table width="623">

 <tbody>

  <tr>

   <td width="309">Space: each parking spotId: Space IDOccupied: 0 – unoccupied, 1-occupied rotatedrect:Center: Of the rectangleSize: of the rectangleAngle: orientation of the rectangle Contour:Points on the contourPlease note that OpenCV python does not have rotatedRect data structure. One would have to come up with your own logic to extract the bounding box.  </td>

   <td width="314"></td>

  </tr>

 </tbody>

</table>







Assignment steps:

<ol>

 <li>Create a training dataset</li>

 <li>Train a cascade classifier.</li>

 <li>Car Detection: Use the classifier to detect cars in a test image.</li>

 <li>Parking spot analysis application: Use the detected cars to decide if a parking spot is empty.</li>

</ol>

Cascade Classifier Training:

<ol>

 <li>Training set (3 Pts):

  <ol>

   <li>Use <strong>Sunny</strong> scenario in each parking lot set to create your training set.</li>

   <li>Write a python program to extract training images using the XML file.

    <ol>

     <li>Use any XML parser library to read the xml file and extract training images. Example below</li>

    </ol></li>

  </ol></li>

</ol>

<table width="413">

 <tbody>

  <tr>

   <td width="83"></td>

   <td width="83"></td>

   <td width="83"></td>

   <td width="83"></td>

   <td width="83"></td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>Train your cascade classifier (3 Pts)</li>

</ol>

(OpenCV           provides           utilities           to           train           cascade            classifier:

<u>https://docs.opencv.org/4.2.0/dc/d88/tutorial_traincascade.html</u>)

<ol>

 <li>Please provide examples of the sample dataset used for positives and negatives and report and justify the number of positive and negative samples used along with the no of stages used to train the cascade classifier and justify in the report.</li>

 <li>Use two sets of features to train your classifier

  <ol>

   <li>HAAR – Haar-like features</li>

   <li>LBP – Local binary patterns</li>

   <li>Report performance of the classifier that is chosen 3. Car Detection (3 Pts):</li>

  </ol></li>

 <li>Use images from rainy and cloudy datasets to test your algorithm</li>

 <li>Write a python program that takes the cascade classifier parameters as input and a test image (from rainy and cloudy datasets) and performs car detection</li>

 <li>Test your detection using both sets of features, Haar and LBP 4. Parking lot analysis (3 Pts):</li>

 <li>Using the detected cars, and the location of the parking spots, determine, if a parking spot is occupied or empty.</li>

 <li>Use the ground truth to compare and summarize your results.

  <ol>

   <li>Test 25 images each from rainy and cloudy (total 50 tests) dataset and report the true positives, false positive, accuracy.</li>

   <li>Some scenarios might have multiple cars but the parking spots might not be annotated, report your results only with respect to the annotated parking spaces and ignore the rest.</li>

  </ol></li>

</ol>

<ul>

 <li>Populate the table below with your findings.</li>

</ul>




<table width="602">

 <tbody>

  <tr>

   <td rowspan="2" width="71"> TestImage</td>

   <td rowspan="2" width="85">ClassifierFeature </td>

   <td width="71"> </td>

   <td colspan="2" width="175">Training</td>

   <td rowspan="2" width="57">TP</td>

   <td rowspan="2" width="57">FP</td>

   <td rowspan="2" width="85">Accuracy</td>

  </tr>

  <tr>

   <td width="71">Stages</td>

   <td width="84">No.          ofPositives</td>

   <td width="92">No.            ofNegatives</td>

  </tr>

  <tr>

   <td width="71"></td>

   <td width="85"></td>

   <td width="71"></td>

   <td width="84"></td>

   <td width="92"></td>

   <td width="57"></td>

   <td width="57"></td>

   <td width="85"></td>

  </tr>

 </tbody>

</table>




<ol start="5">

 <li>Report (3 Pts):</li>

</ol>

<ol>

 <li>Document your findings in the report</li>

 <li>In each of the steps of training, testing, and performance analysis, please include in your report, with example images, a discussion of the following:

  <ol>

   <li>what challenges or limitation do you see in each step and what could be done to improve the same</li>

   <li>compare/show or discuss expected difference(s) before and after the improvement action.</li>

  </ol></li>

</ol>




<strong>Instruction: </strong>

<ol>

 <li>Submit code on Github</li>

 <li>All coding must be done using <strong>python</strong></li>

 <li>Use tools available in OpenCV.</li>

</ol>




<strong>Dataset: </strong>

<ol>

 <li>Dataset can be downloaded at:</li>

</ol>

<u>https://www.dropbox.com/sh/5wd3eb35dt7yp2h/AACyHVKO4AQ4oGN6fe5Wo1Ka?dl=0</u>


