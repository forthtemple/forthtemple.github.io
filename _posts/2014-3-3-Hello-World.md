---
layout: post
title: Faster RCNN
---

I am trying to understand faster RCNN especially the ROI pooling part. The first part is familiar:<br><br>
You process an image such as:<br>
<img src="http://forthtemple.com/fasterrcnn/IMG_0744iii.jpg" />
<br>
<br>
through say 5 convolutional layers:<br>
<img src="http://forthtemple.com/fasterrcnn/try.jpg" height="350"/>
<br>
<br>
For an image of say 300x300 you will get 512 x 13 x 13 grids with 512 for each of the kernels in conv5. Here I'm just showing two:<br>
<img src="http://forthtemple.com/fasterrcnn/try2.jpg" width="100"/>
...
<img src="http://forthtemple.com/fasterrcnn//try2.jpg" width="100"/>
...
<br>
<br>
You generate say 1000 regions of interests. Then create say 1000 6x6 ROI pools for each of these regions. Here is simplified to 5 regions (instead 1000)<br>
<img src="http://forthtemple.com/fasterrcnn/IMG_0744reg.jpg"/><br>
<br>
On the 13x13 grid the regions are:<br>
<img src="http://forthtemple.com/fasterrcnn/try3.jpg"/><br>
<br>
You get five 6 x 6 ROI pools:<br>
<table>
<tr>
<td>
<img src="http://forthtemple.com/fasterrcnn/pool3.jpg"/></td><td><img src="http://forthtemple.com/fasterrcnn/pool4.jpg"/></td><td><img src="http://forthtemple.com/fasterrcnn/pool5.jpg"/></td><td><img src="http://forthtemple.com/fasterrcnn/pool1.jpg"/></td><td><img src="http://forthtemple.com/fasterrcnn/pool2.jpg"/></td>
</tr>
<tr>
<td>
<img src="pool3_6x6.jpg"/></td><td><img src="pool4_6x6.jpg"/></td><td><img src="pool5_6x6.jpg"/></td><td><img src="pool1_6x6.jpg"/> </td><td><img src="pool2_6x6.jpg"/></td> </tr>
<tr>
<td colspan="5">
<br>
The 5 pools have been converted in 6 x 6 grids as seen in blue. In the first region you can see you have to stretch say 3x3 from the 13x13 grid into 6x6.
<br>
<br>
</td></tr>
<tr><td align="center"><img src="arrow.jpg"/><br>coin</td><td  align="center"><img src="arrow.jpg"/><br>coin</td><td  align="center"><img src="arrow.jpg"/><br>coin</td><td  align="center"><img src="arrow.jpg"/><br>NA</td><td  align="center"><img src="arrow.jpg"/><br>NA</td></tr>
</table>
<br>
Each of these regions are then given scores for each class and those regions with high enough scores are used.<br>
<br>
My question is, that if the original pool size if 3x3 from the 13x13 grid, does this mean upscaling to 6x6 is wasted? Is my understanding of faster RCNN way off?


I can update my site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.


