# csce-448-748-assignment-5-solved
**TO GET THIS SOLUTION VISIT:** [CSCE 448/748 Assignment 5 Solved](https://mantutor.com/product/csce-448-748-computational-photography-solved-3/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113299&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSCE 448\/748 Assignment 5 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
Programming Assignment 5

1 Goal

The goal of this project is to become familiar with the seam carving approach. Seam carving is a technique to “retarget” (smart resize) images; the technique preserves the content in order of its importance in the image (as defined by some energy function). It was introduced in 2007 (video, paper) by Shai Avidan and Ariel Shamir. Wikipedia has a good overview of the algorithm.

2 Starter Code

Starter code (in Python) along with the images can be downloaded from here. Note that, expected results for a few images are included in the “Results” folder.

3 Main Task

The main task involves implementing the seam carving approach. The goal is to create two resized version of each input image; 1) reduce the width by a factor of 2, and 2) reduce the height by a factor of 2. As discussed in the class, height reduction can be done by simply rotating the image (or the energy matrix) 90 degrees (you can use numpy rot90 or any other similar function for this). For this task, you only need to generate two resized images for the first three images in the package. The forth image is related to the extra credit part.

In addition to the provided examples, you need to show one image of your own which demonstrates the failure case of the approach. You need to properly discuss why the method fails on your example in the report. You are free to reduce the width or height by any factor of your choosing for this extra image. To implement seam carving, you need to do the following:

1. Compute the energy matrix for your image. Use the energy function discussed in the class which is the sum of absolute gradients in x and y directions. Make sure you convert the color images into grayscale (using rgb2gray in MATLAB or a similar function in python) before computing the gradients.

2. Find the best (lowest energy) seam using dynamic programming:

• Make a scoring matrix (M) the size of your image initialized with the values in the energy matrix (E), i.e., make a copy of your energy matrix.

• Set the values of every entry in the matrix except for the first row by adding to it the minimal value in any of the cells above it in the seam: M(x,y) = E(x,y) + min[M(x − 1,y − 1),M(x,y − 1),M(x + 1,y − 1)], where M(x,y) is the cost of the lowest-cost seam going through that point. You’ll have to do this in an order such that M(··· ,y − 1) is defined at the time it’s evaluated – row by row works. Also beware boundary conditions.

• Find the minimal value in the bottom row of the scoring matrix. This is the bottom of the optimal seam.

• Trace the seam from the bottom by following the smallest value in any of the positions above it in the seam.

3. Remove that seam in the image

4. Repeat steps 1 to 3 on the new image. Note that you have to recompute the energy matrix each time to take into account new edges added by the seam removal.

4 Extra Credit

5 Write Up

For each result, you should show the input image and the two resized images (reducing width and height).

You also need to include one example of your own, where the method fails to generate reasonable results. You need to properly discuss why the method fails on this example. If you implement the extra credit part, show the result with and without the mask (four images) in addition to the input image on the forth example. Describe how you implemented the assignment. Discuss any problem you faced when implementing the assignment or any decisions you had to make.

6 Graduate Credit

Graduate students have to do the extra credit.

7 Deliverables

Your entire project should be in a folder called “firstnamelastname”. This folder should be zipped up and submitted through e-campus. Inside the folder, you should have the followings:

• A folder named “Code” containing all the codes for this assignment. Please include a README file to explain what each file does if you add any other files to the starter code.

• A report in the pdf format. Make sure you write your name on top of the report. Also make sure the pdf file is under 5 MB.

Make sure you exclude all the results and original images from your submission.

8 Checklist

Make sure you can check all the items below before submitting your assignment. You will lose 5 points for each item that cannot be checked.

The folder is named properly (“firstnamelastname”). Note between first and last name. The folder structure should be exactly as follows

“firstname lastname.zip”

– “firstname lastname”

∗ “Code”

∗ Report.pdf

Inside the root folder, there is a folder called “Code” that contains your source code. Also make sure the report is in the root folder.

The folders “Images” and “Results” are not included (you only submit your codes and a report).

Name written on top of the report.

The report is in pdf format and the file is under 5 MB.

9 Ruberic

Total credit: [100 points]

[70 points] – Seam carving

[10 points] – Include one example of your own, where the approach fails

[20 points] – Write up

Extra credit: [10 points]

[10 points] – Incorporating Mask

10 Acknowlegements
