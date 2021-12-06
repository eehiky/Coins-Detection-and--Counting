# Coins-Detection-and--Counting
In this repo I've detected coins in images and video. I have used edge detection filters and draw bounding box around detected coins.
## Coin detection in imgae
Well, I'm terrible and photography. I had captured a terrible image of the coins it can be shown in figure # 01.  In this, you all coins are looking ok and good to go but one coin has more brightness, Because of this If I go for edge detection directly this coin can't be detected. The direct method can be as follows;
1. Convert RGB image to Grayscale image
   - Apply Gaussian blur filter one time
     - Apply Thresholding
       - Apply Bitwise not 
         -  Find Contours
            - Draw Contours   

But for this image if I go for this menthod outout of bitwise not will be as shown in figure # 02. You see one coin edges on right most bottom are not good and have small edges in which we are not interested, while other coins edges are detected. It mean I have to smoothen image more to supress the brightness of coin for this simply add one more step before converting image into grayscale.

1. ''Apply Gaussian blur filter one time''
   - Convert RGB image to Grayscale image
     - Apply Gaussian blur filter one time
       - Apply Thresholding
         - Apply Bitwise not 
           -  Find Contours
              - Draw Contours 

Bitwise Output can see be seen in figure # 03 after appyling Gaussian blur. As you that particular coin edges are not ideally detected but we have removed other small edges to get exact output. Figure # 04 shows final output. 
> Note : In coin detection we are interested in specific edges having circle shape. We have to remove small edges, it can be done using blurring. 

![Coins](https://user-images.githubusercontent.com/74055460/144800860-77c052cc-a472-48e9-a5e7-3cbcacfa4e3c.jpg)
<p align="center">
    Figure 1: Input image
</p>

![bitwise_not](https://user-images.githubusercontent.com/74055460/144803311-960cdc78-15a8-4270-a0d1-d52ed0800195.jpg)
<p align="center">
    Figure 2: Bitwise not output before Guassian blur
</p>

![bitwise_not](https://user-images.githubusercontent.com/74055460/144804673-fbf2bed3-0079-4952-a039-e25aaff4ab2f.jpg)
<p align="center">
    Figure 3: Bitwise not output after Guassian blur
</p>

<p align="center">
  ![output](https://user-images.githubusercontent.com/74055460/144805651-338ad1a6-7543-44e3-af75-5c5f02310f96.png)
  Figure 4: Final output
</p>

## Coin detection in video
In this part we will deal with video, In case if image we have pretty good in terms of details and resolution. When we deal with video we actually find edges for each frame and for each frame we don't have good details and resolution, so we don't need to apply gaussian filter. But in this case we will use other set of method as follows. 
