## Technical Skills
<b>Programming:</b> Python, R, SQL <br>
<b>Platforms & Tools:</b> VS Code, Jupyter Notebook, R Tidyverse, Python Pandas, Git

## Education 
<div style="overflow: hidden;">
    <div style="float: left;"><em>HBSc, Major in Statistics</em></div>
    <div style="float: right;">June 2024 (expected)</div>
</div>
<p>University of Toronto Scarborough<br>
* Relevant Coursework: Data Analysis, Regression Analysis, Time Series Analysis, Data Visualization, Web Development</p>

## Projects
### Course Website | Python, SQL, HTML, CSS
<b>Github:</b> [Course Website](https://github.com/ShuvarthyD/Course_Website) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <b>Cloud Version:</b> [shuvarthyd.pythonanywhere.com](https://shuvarthyd.pythonanywhere.com/)
<br>
A responsive Web Development course website created using the [Flask](https://flask.palletsprojects.com/en/3.0.x/) web framework, along with the extension [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/3.1.x/) to edit and manage the database. Users initially only have access to basic course information, but can choose to **login** or **register** as a **student** or **instructor** to access additional features. Instructors can access their account page to view feedback, edit student marks, and access visualizations and analyses of student mark data (see Figure 1) student mark data. Students can submit remark requests, send feedback, and view their grade summary. Although SQLAlchemy has its own "Pythonic" way of handling databases (ORM), I prefer using raw SQL queries as it is much easier to read and maintain.

### Linear Regression Analysis of Systolic Blood Pressure | R
In this project, I analyzed the effects of 10 genetic markers alongside 17 clinical covariates on systolic blood pressure (SBP) and developed a prediction model for SBP. The steps taken were as follows:
<p align="center">
</p>
1. Implemented a dummy coding scheme for the categorical variables in the dataset. In R this can be achieved by using the <b>relvel</b> function and setting the reference level using the <b>ref</b> parameter.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
2. Excluding the 10 genetic markers, I found which variables are highly correlated and only included one of them in the linear model as predictors with high correlation can lead to collinearity issues.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
3. Created the linear model in R and interpreted some of the regression parameters:
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
4. A partial F-test was used to test the joint effect of the 10 genes at α = 0.05. Our null hypothesis is all the beta values for the 10 genes = 0. Utilizing  the <b>anova</b> function, both the original model and a reduced model excluding the genetic markers were employed to derive a p-value of <b>0.0455</b> < α = 0.05. Thus the null hypothesis was rejected and I conclude that there is a joint effect of the 10 genes on SBP.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
5. To obtain a prediction model, both forward selection and backward elimination strategies were utilized. The <b>MASS</b> package in R contains the <b>stepAIC</b> function to implement these strategies. Although a 5-fold cross-validation could have been conducted to calculate the mean squared prediction error (MSPE) for each model, it was deemed unnecessary as the results for both strategies led to the same model.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>

### Wavelength Calibration | Python
This project is divided into two parts, both aimed at obtaining a wavelength solution by finding an appropriate fit between the peak wavelengths and pixel positions of a given dataset. For the first part, I am given a Neon Lamp Spectrum where the peak wavelengths were obtained manually and the peak pixel positions were found using the <b>find_peaks</b> function from the <b>scipy</b> package. Since the given measurements may contain observational errors, I opted to use the weighted means of the peaks. To do this I picked an acceptable range of &pm;10 pixels of the identified peaks and plugged it into the <b>centroid</b> formula $X_{cent} = \frac{\sum x_i I_i}{\sum I_i}\$. Then by creating a simple linear fit using the <b>polyfit</b> function, I was able to obtain the wavelength solution.
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="http://some_place.com/image1.png" />
  </div>
  <div style="margin: 0 10px;">
    <img src="http://some_place.com/image2.png" />
  </div>
</div>
<p style="text-align: center;">Text_content</p>
For the second part, I was able to obtain both the peak wavelengths and their pixel positions manually. But a linear fit was not sufficient enough so I used a residual plot to compare the accuracy of the different degrees of fit. From the residual plots shown below, we can see that the residuals for all 3 fits are random implying they are all suitable fits. But we also notice that the residuals for the cubic fit seem to be closer to having a fitting error of 0 on average, which can be further noticed in the histogram. Thus the polynomial with degree 3 was chosen as the best fit.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="http://some_place.com/image1.png" />
  </div>
  <div style="margin: 0 10px;">
    <img src="http://some_place.com/image2.png" />
  </div>
</div>
I obtain the following wavelength solution: $\lambda = −(0.065 ± 0.038)x2 + (12.287 ± 4.762)x + (15530.984 ± 189.504)$.
