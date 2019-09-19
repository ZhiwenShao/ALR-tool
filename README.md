# ARL Tool
Face alignment tool v1
2016.3

The provided tool is a quick implementation of ARL [(Face alignment by deep convolutional network with adaptive learning rate)](https://zhiwenshao.github.io/pdfs/projects/2016/shao2016face.pdf). And this tool is implemented based on Caffe [1]. The example images in the folder "data" are selected from AFLW [2].

References:

[1] Jia Y, Shelhamer E, Donahue J, et al. Caffe: Convolutional architecture for fast feature embedding[C]//Proceedings of the ACM International Conference on Multimedia. ACM, 2014: 675-678.

[2] Kostinger M, Wohlhart P, Roth P M, et al. Annotated facial landmarks in the wild: A large-scale, real-world database for facial landmark localization[C]//Computer Vision Workshops (ICCV Workshops), 2011 IEEE International Conference on. IEEE, 2011: 2144-2151.

Prerequisites:

1. The provided tool is compiled on Windows 8.1, 64 bit. But we have tested this tool successfully on Windows 7 and Windows 10.  

2. If you haven't installed Visual Studio 2013 or Visual C++ Redistributable for Visual Studio 2013, then please download and install the Visual C++ Redistributable for Visual Studio 2013 from: https://www.visualstudio.com/downloads/download-visual-studio-vs

Usuage:

face_align_icassp.exe modelPath imagePath listfile outputFile
rd /s/q modelPath\\input_data

Input:
- "listfile " is a file that contains the images and corresponding face bounding box for each image. 
- "imagePath " is the path to a directory containing the image files.
- "modelPath " is the path to a directory containing the model file.

Output:
- "outputFile" is a file that will be generated by this tool and contains the predicted facial landmark locations.

The demand of "rd /s/q modelPath\\input_data" is used for deleting a temp file at each run. If you remove this demand, the running results will be wrong.  

Format:

Format of the listfile:
This file starts with the number of the images to be tested.
Then each of the following line contains the image name, followed by the left, right, top and bottom of the face bounding box.
We suggest you use the face detector provided in http://mmlab.ie.cuhk.edu.hk/archive/CNN_FacePoint.htm to generate the face bounding box.

Format of the outputFile:
5 facial landmark locations (x1,y1,x2,y2...).

Example:
Run run.bat

# Related materials
- [Caffe training configuration files of ARL](https://github.com/ZhiwenShao/ARL-configuration)
- [Face bounding box annotations of 2995 AFLW images](https://github.com/ZhiwenShao/AFLW_bbox_annotation)

Please cite our paper in your publications if it helps your research:
```
@inproceedings{shao2016face,
  title={Face alignment by deep convolutional network with adaptive learning rate},
  author={Shao, Zhiwen and Ding, Shouhong and Zhu, Hengliang and Wang, Chengjie and Ma, Lizhuang},
  booktitle={2016 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  pages={1283--1287},
  year={2016},
  organization={IEEE}
}
```

Should you have any questions, then just contact with us through email, shaozhiwen@sjtu.edu.cn.
