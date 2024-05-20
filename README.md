<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/AAM-Driverless/aamfsd_cv_dataset/tree/master/Rules>
    <img src="red_car.jpg" alt="Logo" width="275" height="200">
  </a>

  <h3 align="center">Arab Academy Motors</h3>

  <p align="center">
    AAM Computer Vision subteam
    <br />
    <br />
    <br />
    <a href="https://github.com/AAM-Driverless/aamfsd_cv_dataset/blob/master/Rules/FSAE_Rules_2021_V1.pdf">Rules</a>
    ·
    <a href="https://github.com/AAM-Driverless/aamfsd_cv_dataset/issues">Report issue</a>
    ·
    <a href="https://github.com/AAM-Driverless/aamfsd_cv_2022/tree/master/src/aam_perception">Computer_Vision Packages</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#About AAM-Driverless">About AAM-Driverless</a>
      <ul>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About AAM-Driverless

our team installs an autonomous function in the race vehicle, a simple,computational efficient yet robust pipeline was our target. State-of-the-art algorithms were adopted in perception, state estimation, path planning, and control.




<!-- GETTING STARTED -->
## Getting Started

This is how to train YOLO on costum dataset

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* CMake >= 3.18
* CUDA >= 10.2
* OpenCV >= 2.4
* cuDNN >= 8.0.2



### Installation

```sh
git clone https://github.com/AlexeyAB/darknet
cd darknet
mkdir build_release
cd build_release
cmake ..
cmake --build . --target install --parallel 8
```



<!-- USAGE EXAMPLES -->
## Usage

1. download label_img : https://tzutalin.github.io/labelImg/
2. label your dataset (recomended:windows version)
3. add text files to imgs folder
4. edit /darknet/Makefile
```sh
GPU=1             # activate compilte with GPU
CUDNN=1
CUDNN_HALF=1
OPENCV=1          # activate opencv for visualisation
OPENMP=1
```
4. add pretrained wheights to darknet folder
5. create .names file in data folder
```sh
yellow_cone
blue_cones
orange_cone
```
6. create .cfg file in cfg folder
```sh
yellow_cone
blue_cones
orange_cone
```
7. create train.txt file in data folder containing adresses of **training dataset**
```sh
data/obj/1.jpg
data/obj/2.jpg
data/obj/3.jpg
```
8. create test.txt file in data folder containing adresses of **testing dataset**
```sh
data/obj/1.jpg
data/obj/2.jpg
data/obj/3.jpg
```
9. create .data file
```sh
classes = 3
train  = data/train.txt
names = data/obj.names
valid  = data/test.txt
backup = backup/
```             
10. view results
```sh                      
./darknet detector demo data/obj.data cfg/aam_YOLOV4.cfg backup/aam_YOLOV4_final.weights test1.mp4 -ext_output -out_filename res.avi
./darknet detector demo data/obj.data cfg/aam_YOLOV4.cfg backup/aam_YOLOV4_final.weights test1.mp4 -ext_output
./darknet detector test data/obj.data cfg/aam_YOLOV4.cfg backup/aam_YOLOV4_final.weights test2.jpg -ext_output
```         

                          
<!-- CONTRIBUTING -->
## Contributing

Everyone submits their work on by committing it **in their own branch** and keep updating it though out the season .

1. clone repo
2. write your code
2. Create your Branch with your name (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add text that describe your code'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)




<!-- LICENSE -->
## License

This workspace is a private property of AAM team please don't share it online 



<!-- CONTACT -->
## Contact

Omar El-Fayoumi - omarselfayoumi@gmail.com

Project Link: https://github.com/AAM-Driverless/aamfsd_cv_dataset
