# cs401-homework-7-robot-localization-solved
**TO GET THIS SOLUTION VISIT:** [CS401 Homework 7-Robot Localization Solved](https://www.ankitcodinghub.com/product/cs401-homework-7-robot-localization-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;99132&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS401 Homework 7-Robot Localization Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

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

<div class="kksr-stars-active" style="width: 0px;">
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
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
# Homework 7 – Robot Localization

**Coding Homeworks.** Your final submission should be a compressed package with extension .zip, which includes your codes and explanations (you need to know how to write the manuscript with Markdown or LATEX). Your code should be run step-by-step without any error. Real-time animation is also recommended.

—-

## Overview

You will be implementing a 2-Dimensional Kalman Filter for constant velocity model and particle filter for 2D robot localization using measurements from landmarks.

Corresponding code skeltons are provided for you to implement the filter. Also, the visulization of the two filters are provided in the framework.

## 2D Kalman Filter with Constant Velocity Model

A simulated scenario where we consider a robot in 2D and use odometry for prediction and mocked GPS measurement for evaluation.

## motion model and obervation motion model.

### Velocity-based 2D robot motion model

This is a sensor fusion localization with Particle Filter(PF).

The blue line is true trajectory, the black line is dead reckoning trajectory,

and the red line is estimated trajectory with PF.

In a 2D map with distributed landmarks, we assume that the robot can measure a distance from landmarks,

This measurements are used for PF localization.

&nbsp;

Suppose the robot has a state vector includes 3 states at time &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;t” title=”https://latex.codecogs.com/svg.image?\inline t” /&gt;:

&lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;\textbf&amp;space;X_t&amp;space;=&amp;space;\begin{bmatrix}x_t&amp;space;\\y_t&amp;space;\\\theta_t\end{bmatrix}” title=”https://latex.codecogs.com/svg.image?\inline \textbf X_t = \begin{bmatrix}x_t \\y_t \\\theta_t\end{bmatrix}” /&gt;

Meanwhile, the robot can obtain the velocity and orientation information, and their can be used as input vector at each time step:

&lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;\textbf{u}_t&amp;space;=&amp;space;\begin{bmatrix}&amp;space;v_t\\w_t\end{bmatrix}” title=”https://latex.codecogs.com/svg.image?\inline \textbf{u}_t = \begin{bmatrix} v_t\\w_t\end{bmatrix}” /&gt;

Thus, the robot motion model is:

&lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;\textbf&amp;space;X_{t&amp;plus;1}&amp;space;=&amp;space;A&amp;space;\textbf{X}_t&amp;space;&amp;plus;&amp;space;B&amp;space;\textbf{u}_t&amp;space;&amp;plus;&amp;space;\textbf{w}_t” title=”https://latex.codecogs.com/svg.image?\inline \textbf X_{t+1} = A \textbf{X}_t + B \textbf{u}_t + \textbf{w}_t” /&gt;

where

&lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;A&amp;space;=&amp;space;\begin{bmatrix}1&amp;space;&amp;&amp;space;0&amp;space;&amp;&amp;space;0&amp;space;\\0&amp;space;&amp;&amp;space;1&amp;space;&amp;&amp;space;0&amp;space;\\0&amp;space;&amp;&amp;space;0&amp;space;&amp;&amp;space;1&amp;space;\\\end{bmatrix}” title=”https://latex.codecogs.com/svg.image?\inline A = \begin{bmatrix}1 &amp; 0 &amp; 0 \\0 &amp; 1 &amp; 0 \\0 &amp; 0 &amp; 1 \\\end{bmatrix}” /&gt;, &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;B&amp;space;=&amp;space;\begin{bmatrix}cos(\theta_t)&amp;space;&amp;&amp;space;0&amp;space;\\sin(\theta_t)&amp;space;&amp;&amp;space;0&amp;space;\\0&amp;space;&amp;&amp;space;&amp;space;1\\\end{bmatrix}” title=”https://latex.codecogs.com/svg.image?\inline B = \begin{bmatrix}cos(\theta_t) &amp; 0 \\sin(\theta_t) &amp; 0 \\0 &amp; 1\\\end{bmatrix}” /&gt;, and &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;\textbf{w}_t&amp;space;” title=”https://latex.codecogs.com/svg.image?\inline \textbf{w}_t ” /&gt; is the zero-mean Gaussian process noise vector with covariance matrix Q.

### Observation Model:

Also, the robot has a GPS sensor, it means that the robot can observe x, y position at each time:

&lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;\textbf{Z}_{t&amp;plus;1}&amp;space;=&amp;space;H\textbf{X}_{t&amp;plus;1}&amp;space;&amp;plus;&amp;space;\textbf{v}_{t&amp;plus;1}” title=”https://latex.codecogs.com/svg.image?\inline \textbf{Z}_{t+1} = H\textbf{X}_{t+1} + \textbf{v}_{t+1}” /&gt;

where, &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;H&amp;space;=&amp;space;\begin{bmatrix}1&amp;space;&amp;&amp;space;0&amp;space;&amp;&amp;space;0&amp;space;\\0&amp;space;&amp;&amp;space;1&amp;space;&amp;&amp;space;0&amp;space;\\0&amp;space;&amp;&amp;space;0&amp;space;&amp;&amp;space;0&amp;space;\\\end{bmatrix}” title=”https://latex.codecogs.com/svg.image?\inline H = \begin{bmatrix}1 &amp; 0 &amp; 0 \\0 &amp; 1 &amp; 0 \\0 &amp; 0 &amp; 0 \\\end{bmatrix}” /&gt; and &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;\textbf{v}_{t&amp;plus;1}” title=”https://latex.codecogs.com/svg.image?\inline \textbf{v}_{t+1}” /&gt; is the zero-mean Gaussian observation noise with variance R.

### Implement the kalman filter

If the kalman filter design is complete, we just have to write the code to run the filter and output the data in the format of our choice.

The initial uncertanty for the motion noise and observation noise are defined in the code.

The comparisons between the odometry, GPS, filter and ground truth are shown in the following figure:

&lt;div align=left&gt; &lt;img src=sources/kalman_compare.png width=40%/&gt; &lt;/div&gt;

## Particle filter 2D localization

In a 2D map with some landmarks, a robot moves with velocity-based motion model and can measure its relative distances from nearby landmarks.

You will use the particle filter algorithm to locate the robot based on the distance measurements.

## Generic Particle Filter Algorithm

– Randomly generate a bunch of particles: particles can have position, heading, and/or whatever other state variable you need to estimate. Each has a weight (probability) indicating how likely it matches the actual state of the system. Initialize each with the same weight.

– Predict next state of the particles: Move the particles based on how you predict the real system is behaving.

– Update: Update the weighting of the particles based on the measurement. Particles that closely match the measurements are weighted higher than particles which don’t match the measurements very well.

– Particle Resampling: Discard highly improbable particle and replace them with copies of the more probable particles.

– Compute Estimate: Optionally, compute weighted mean and covariance of the set of particles to get a state estimate.

You can refer to [Tutorial of particle filter ](https://github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/blob/master/12-Particle-Filters.ipynb) for better understanding and python implementation of particle filter.

&lt;div align=left&gt; &lt;img src=sources/animation.gif width=50%/&gt; &lt;/div&gt;

This is a sensor fusion localization with Particle Filter(PF).

The blue line is true trajectory, the black line is dead reckoning trajectory,

and the red line is estimated trajectory with PF.

It is assumed that the robot can measure a distance from landmarks (RFID).

This measurements are used for PF localization.

—-

## Task 1

Please derivate the predcition and update process of kalman filter.

## Task 2

Please implement the “predict” and “update” function in the code [kalman-filter.py](code/kalman-filter.py)

## Task 3

Please implement the “re-sampling” and “weight calculation” parts in [particle_filter.py](code/particle_filter.py)

## Note for tasks

The covariance matrix from particles is calculated as following:

&lt;div align=left&gt; &lt;img src=sources/cov_pf.png width=60%/&gt; &lt;/div&gt;
