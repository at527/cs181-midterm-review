# CS181 Midterm Practice Problems

## Lecture 1

1\. What is the focal length? Give a brief definition.

2\. A video camera sends 30 images (frames) per second of $640 \times 480$  
“true color” pixel values. How many bytes per second are sent?


## Lecture 2

3\. True or False: The two projection matrices P1 and P2, below, 
will map a real world point to the same point 
in the image plane (assume $f$ does not equal 0).

$$
    P_1 = \begin{bmatrix}
            1 & 0 & 0 & 0 \\
            0 & 1 & 0 & 0 \\
            0 & 0 & 1/f & 0
            \end{bmatrix},
    P_2 = \begin{bmatrix}
            f & 0 & 0 & 0 \\
            0 & f & 0 & 0 \\
            0 & 0 & 1 & 0
            \end{bmatrix}
$$

## Lecture 3

4\. Which of the following factors does not affect the intrinsic parameters of a camera model?

A. Focal length \
B. Image resolution \
C. Principal point \
D. None of the above

5\. Write down a matrix that will translate a homogeneous point $[x, y, 1]^T$ 3 units in the positive x
direction and 10 units in the positive y direction.

6\. Consider two identical cameras (such that $K=K'$), 
whose optical axis coincides with the z axis, 
whose focal length is 0.03 meters, with square pixels, 
no pinhole point offset and zero skew. \
What is its intrinsic camera matrix, $K$?

## Lecture 4

7\. What does a homography do? And mention some of its properties.

8\. How many point correspondences are needed to fit a 2D affine model?

9\. Select all the options that are correct 
regarding properties of homographies (2D projective transformations): \

A. Origin does not necessarily map to origin \
B. Every measurement (i.e., point) provides 1 independent equation \
C. parallel lines remain parallel \
D. Ratios are not preserved 

## Lecture 5

10\. In the image below, let $P(X, Y, Z) = (14, 0, 24)$, 
$X_L = 5$, $X_R = 11$, and $f = 4$
(assume each measurement has the same unit). \
Calculate the disparity between the projection of $P$ onto the
left and right camera image planes.

## Lecture 6



## Lecture 7


## Lecture 8


## Lecture 9


## Lecture 10