<H1>Nvidia AI Specialist Certification</H1>
<br>
<br>
<aside>
✅ **OverView of the Project**

- Opening background information

- General description of the current project

- Proposed idea for enhancements to the project

- Value and significance of this project

- Current limitations

- Literature review

</aside>

<br>
<br>

# Title

Plastic recycling code recognition for camera-enabled recycling bins

<br>
<br>

# Opening background information

<aside>
✅ - This project provides an important technical foundation for environmental protection, resource conservation, and sustainable development. A recycling mark recognition system using AI will enable automated recycling classification, which will be of great help in increasing recycling rates and solving the problem of plastic pollution. Also, this is a personal story, but when I was serving in the military, we mobilized troops to separate garbage dumps, but the recycling rate at that time was so low that I started thinking about creating recycling awareness trash cans.

</aside>

---

<br>

# General description of the current project

<aside>
✅ - The goal is to develop an artificial intelligence (AI) system that can automatically recognize and classify recyclable plastic marks. The artificial intelligence (AI) system will proceed with the project with plans to apply it to trash cans. Installing recycling code recognition trash cans in places with low recycling rates, such as military or public trash cans, can save human resources in the future. The key is to streamline the recycling process, increase the plastic recycling rate, and build technology that can contribute to environmental protection.

</aside>

---

<br>

# **Proposed idea for enhancements to the project**

<aside>
✅ - **+ AI-based automated recycling classification system**
    
    In the current plastic recycling process, the process of distinguishing and sorting marks by human eyes is time-consuming and can lead to mistakes. Using an AI model, you can quickly and accurately analyze images and automatically recognize various types of plastic marks, enabling efficient separate discharge.
    
- **+ Scalable system**
    
    This project provides a scalable system that can learn not only specific recycling marks, but also various types of recycling marks and plastic types in the future. This has the potential to develop into a technology that can be applied in specific regions in the short term and in the global market in the long term.

</aside>

---

<br>

# Value and signifiance of the project

<aside>
✅ - Currently, plastic pollution is emerging as a serious environmental problem worldwide. In particular, since plastic does not decompose in nature, it has a significant impact on the natural environment, including soil, sea, and air. However, plastic is a recyclable resource. Therefore, there is an urgent need for a system to accurately separate and efficiently recycle plastic. This project can play an important role in automating the recycling process by accurately recognizing plastic recycling marks and reducing environmental pollution by increasing recycling rates.

</aside>

---

<br>

# **Current limitations**

<aside>
✅ - There are several key limitations in current plastic recycling technologies. First, the variety and complexity of plastic types make efficient sorting difficult. Second, the quality of recycled plastic often falls short compared to virgin plastic, limiting its reuse in new products. Third, recycling infrastructure and systems are unevenly distributed, making it challenging to establish an efficient global recycling framework. Lastly, a lack of public awareness about plastic recycling and economic barriers also pose significant constraints.

</aside>

---

<br>

# **Literature review**

<aside>
✅ - A variety of learning data, image recognition, and object detection for recycled plastics are needed.

</aside>

---

<br>
<br>

## Image acquisition method

- 1. Videos and images are obtained by directly shooting plastic items with a plastic recycling code with a camera.
- 2. If you want to obtain more images of plastic recycling codes, you can do so by searching.

<br>

[Google Drive - Train Video / Plastic, Can-RecycleCode DataSet](https://drive.google.com/drive/folders/1U06urchYQgUS13HIrnAcXyG1Lu9j78hj?usp=sharing)

<br>

[Google Drive - DataSet and Result / All-RecycleCode DataSet](https://drive.google.com/drive/folders/1BnvuJfLOWVoczlMWEHVnba1yDsy5Am5r?usp=sharing)

<br>

First of all, there is a dataset through searching on Google Drive, but we trained with the dataset obtained by directly filming and videoing.
And after training, for areas where we felt there was insufficient data for learning, we added some images obtained through searching and trained them again.

<br>

**1. In order to learn at a resolution of 640 x 640, cut the videos and images to fit 640 x 640.**

[https://online-video-cutter.com/ko/resize-video](https://online-video-cutter.com/ko/resize-video) You can easily cut it through their site.

![image.png](readme_images/image.png)

<br>

**2. DarkLabel**

[https://www.zaivhub.com/ko/yolov5](https://www.zaivhub.com/ko/yolov5)

After downloading the DarkLabel program and data.yaml file through this site, you can use it to convert collected videos and images into labeled images.

<br>

**3. First, open the darklabel.yml file with Notepad.**

![image.png](readme_images/image%201.png)

<br>

**4. Add class plastic_classes.**

![image.png](readme_images/image%202.png)

<br>

**5. Add format9 at the bottom.**

![image.png](readme_images/image%203.png)

<br>

**6. 9.Plastic is created when you run DarkLabel.exe.**

![image.png](readme_images/image%204.png)

<br>

**7. First, open the video by pressing the Open Video button, uncheck the bottom to save images by frame, and save them using the as Images button.**

![image.png](readme_images/image%205.png)

<br>

**8. Then, the collected videos and images are extracted as images and labels from DarkLabel.**

![image.png](readme_images/image%206.png)

<br>

**9. Change the name of the label and image obtained as above.**

Sort by name.

Click at the top and press ctrl + A.

Press the F2 button.

![image.png](readme_images/image%207.png)

If you change the file name to train1_(1), all other files will be changed in order.

![image.png](readme_images/image%208.png)

This same operation is applied to all images and labels obtained from other train images.

**※ The file names of the image file and label file corresponding to each image must be the same.**

<br>

## Edit Data.yaml file and download data model

**1. Edit the data.yml file obtained when downloading Darklabels in the yolov5-master folder.**

![image.png](readme_images/image%209.png)

![image.png](readme_images/8ef95373-c036-439b-bda5-c047a297d50a.png)

**2. If you do not have the yolov5n.pt file, download the yolov5n.pt file through the link below.**

[https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5n.pt](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5n.pt)

**3. Results obtained through the above processes**

![image.png](readme_images/image%2010.png)

The results will be routed separately below.

<br>

## Write code using Google Colaboratory.

**1. Integrates with Google Drive.**

![image.png](readme_images/image%2011.png)

**2. Install yolov5.**

![image.png](readme_images/image%2012.png)

**3. Create a train folder and a valid folder.**

![image.png](readme_images/image%2013.png)

**4. Move the file based on the result obtained above to the appropriate path.**

Location of images folder and labels folder

![image.png](readme_images/b8bf697d-cce6-4a37-ade0-649efca66643.png)

data.yaml file location

![image.png](readme_images/8edfb8e6-10fe-45d6-9c18-c3bf6d2903d4.png)

yolov5n.pt model location

![image.png](readme_images/18954f2b-2298-4d65-ae93-de870e2b6560.png)

**5. Generate verification data.**

![image.png](readme_images/image%2014.png)

python [train.py](http://train.py/) --img 640 --batch 16 --epochs 300 --data .\data\data.yaml --weights [yolov5s.pt](http://yolov5s.pt/)

<br>

## Start learning

**1. Prepare in advance before starting learning.**

![image.png](readme_images/image%2015.png)

**2. Learning begins when you execute the command below.**

![image.png](readme_images/image%2016.png)

<br>

## Check learning outcomes

**1. You can check that the best.pt model has been created.**

![image.png](readme_images/11f9d9ce-0c20-4673-945c-d40e4b29bd17.png)

**2. Check the training result train_batch**

![train_batch0.jpg](readme_images/train_batch0.jpg)

![train_batch2.jpg](readme_images/train_batch2.jpg)

![train_batch0.jpg](readme_images/train_batch0%201.jpg)

![train_batch1.jpg](readme_images/train_batch1.jpg)

![results.png](readme_images/results.png)

![labels_correlogram.jpg](readme_images/labels_correlogram.jpg)

![labels.jpg](readme_images/labels.jpg)

![P_curve.png](readme_images/P_curve.png)

<br>

## Verification of learning outcomes

**1. You can verify using the command below.**

python [detect.py](http://detect.py/) --weight runs/train/exp/weights/best.pt --source [Path to image to test] --img 640 --conf 0.8

![image.png](readme_images/image%2017.png)

![image.png](readme_images/image%2018.png)

**2. Verification results**

![image.png](readme_images/image%2019.png)

**3. Alternatively, you can test with a video instead of an image using the command below.**

python [detect.py](http://detect.py/) --weight runs/train/exp/weights/best.pt --source [Path to video to test] --img 640 --conf 0.8

<br>

[Google Drive - detect-video from test-video](https://drive.google.com/drive/folders/10aHjcGPqCY0Am8rhcIJPTdkirmEg8USJ?usp=sharing)

<br>

![testVideo1](https://github.com/user-attachments/assets/49f620f7-b6c6-4d4b-8810-a4c468a459f2)

testVideo(1) is a test video that recognizes only plastic by learning a dataset excluding cans.

![testVideo2](https://github.com/user-attachments/assets/318d7bb8-fdc1-406b-a518-22422e4006d1)

Later, a separate dataset for cans was learned and updated. So testVideo(2) is a test video that recognizes only plastic by learning a dataset including cans.

![testVideo3_480](https://github.com/user-attachments/assets/a6282177-c2de-44c5-9d35-8b082a078923)

testVideo(3) was tested on more objects.
