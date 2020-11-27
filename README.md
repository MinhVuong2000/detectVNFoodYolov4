# detectVNFoodYolov4
Detecting Vietnam Cuisine using Yolov4

Runtime in Colab is GPU.

If you no use my file, you can use guide bellow.

1. File cfg/yolov4-custom.cfg
- First, you need verify number of class you train? As me, is 10 classes
- Find line 20, modify max_batches = max(<number of classes>*2000,6000).
- Line 22 modify steps=80%, 90% of max_batches. For example here is steps=16000,18000.
- Replace all lines have “classes=80” into “classes=<number of class>”. Can use Find/Search and Replace if no, it is in line 970, 1058 và 1146.
- Replace all lines “filters=255” into “filters=<(số class+5)*3>”. It's in line 963, 1051 và 1139.
- If you be been out memory, modify subdivisions (line 7) into 32 (or 64) or you can reduce size ảnh become width=416, height=416 (line 8,9).
  
2. File MakeFile
- Line 1, modify to GPU=1
- Line 2, modify to CUDNN=1
- Line 4, modify to OPENCV=1

3. Create yolo.names: it include name of classes

4. Create yolo.data: include 
- line 1: classes = < number of class>
- line 2:train= <link to file train.txt>
- line 3:valid= <link to file val.txt>
- line 4:names= <link to file yolo.names>
- line 5: backup=<link to file backup>

