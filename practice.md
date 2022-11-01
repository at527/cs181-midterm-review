# CS181 Midterm Practice Problems

## Lecture 1

1\. What is the focal length? Give a brief definition.

The focal Length is the distance from the
center of a lens to the focal point.
The focal point is where light
converges to form an image.

2\. A video camera sends 30 images (frames) per second of $640 \times 480$  
“true color” pixel values. How many bytes per second are sent?

$$
\begin{align*}
    640 \times 480 &= 307,200 \text{ pixels} \\
    1 \text{ pixel} &= 8 \text{ bits} = 1 \text{ byte} \\
    307,200 \times 1 \times 30 &= 9,216,000 \text{ bytes/second} 
\end{align*}
$$

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

$$
\begin{align*}
    \begin{bmatrix}
        1 & 0 & 0 & 0 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 1/f & 0
    \end{bmatrix}
    \begin{bmatrix}
        a \\
        b \\
        c
    \end{bmatrix}
    &= \begin{bmatrix}
        a \\
        b \\
        c/f
    \end{bmatrix}
    = \begin{bmatrix}
        af/c \\
        bf/c \\
        1
    \end{bmatrix} \\
%
    \begin{bmatrix}
        f & 0 & 0 & 0 \\
        0 & f & 0 & 0 \\
        0 & 0 & 1 & 0
    \end{bmatrix}
    \begin{bmatrix}
        a \\
        b \\
        c
    \end{bmatrix}
    &= \begin{bmatrix}
        fa \\
        fb \\
        c
    \end{bmatrix}
    = \begin{bmatrix}
        af/c \\
        bf/c \\
        1
    \end{bmatrix}
\end{align*}
$$

True, the projections are equivalent. 

## Lecture 3

4\. Which of the following factors does not affect the intrinsic parameters of a camera model?

A. Focal length \
B. Image resolution \
C. Principal point \
D. None of the above

None of the above. The intrinsic parameters of a camera 
characterize the optical, geometric, and digital
characteristics of a camera.

These account for
1. Focal Length
2. Principal point (where optical axis intersects image plane)
3. Pixel Aspect ratio (pixel shape)
4. Angle between axes (skewness of sensor)

The Image Resolution can affect the pixel aspect ratio and pixel size.

5\. Write down a matrix that will translate a homogeneous point $[x, y, 1]^T$ 3 units in the positive x
direction and 10 units in the positive y direction.

$$
\begin{align*}
\begin{bmatrix}
    x + 3 \\
    y + 10 \\
    1
\end{bmatrix}
&= 
\begin{bmatrix}
    1 & 0 & 3 \\
    0 & 1 & 10 \\
    0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
    x \\
    y \\
    1
\end{bmatrix}
\end{align*}
$$

6\. Consider two identical cameras (such that $K=K'$), 
whose optical axis coincides with the z axis, 
whose focal length is 0.03 meters, with square pixels, 
no pinhole point offset and zero skew. \
What is its intrinsic camera matrix, $K$?

$$
\begin{align*}
    \mathbf{K} &=
    \begin{bmatrix}
        -f  & s         & c_x \\
        0   & -\alpha f & c_y \\
        0   & 0         & 1
    \end{bmatrix}
\end{align*}
$$
where $\alpha$ is the aspect ratio,\
$s$ is the skew and\
$(c_x, c_y)$ is the principal point.

$$
\begin{align*}
    f &= 0.03 \\
    \mathbf{K} &=
    \begin{bmatrix}
        -0.03  & 0     & 0 \\
        0   & 0.03 & 0 \\
        0   & 0         & 1
    \end{bmatrix}
\end{align*}
$$

The optical axis coinciding with the
z-axis means it intersects with the
projection plane at the origin. (Imagine right hand rule as axes.)

## Lecture 4

7\. What does a homography do? And mention some of its properties.

A homography is a projective transformation that
maps points to points. This determines the relationship
between two images from the same camera center.

Properties of homographies:
1. The origin does not necessarily map to the origin (pan left to right).
2. Lines map to lines.
3. Parallel lines do not necessarliy remain parallel.
4. Ratios are not preserved.

8\. How many point correspondences are needed to fit a 2D affine model?

A 2d affine transformation has 6 degrees of freedom,
so at least 3 correspondences are required (each gives 2).

9\. Select all the options that are correct 
regarding properties of homographies (2D projective transformations): \

A. Origin does not necessarily map to origin \
B. Every measurement (i.e., point) provides 1 independent equation \
C. parallel lines remain parallel \
D. Ratios are not preserved 

A: True \
B: False: Each provides 2 equations. \
C: False: Parallel lines may not remain parallel. \
D: True: Ratios are not necessarily preserved.

## Lecture 5

10\. In the image below, let $P(X, Y, Z) = (14, 0, 24)$, 
$X_L = 5$, $X_R = 11$, and $f = 4$
(assume each measurement has the same unit). \
Calculate the disparity between the projection of $P$ onto the
left and right camera image planes.

<img src="q5.png" width="300">

$$
\begin{align*}
    x_L &= f \frac{X - X_L}{Z} \\
    x_R &= f \frac{X - X_R}{Z} \\
    \text{disp} &= x_R - x_L \\
    &= \frac{f}{Z} 
    \left( \left(X - X_R \right) - \left(X - X_L \right) \right) \\
    &= \frac{f}{Z} \left( X_L - X_R  \right) \\
    &= \frac{4}{24} \left( 5 - 11  \right) \\
    &= -1
\end{align*}

$$

## Lecture 6



## Lecture 7


## Lecture 8


## Lecture 9


## Lecture 10