## Technical Skills
Programming: Python, R, SQL
Platforms & Tools: VS Code, Jupyter Notebook, R Tidyverse, Python Pandas, Git

## Education 
<div style="overflow: hidden;">
    <div style="float: left;"><em>HBSc, Major in Statistics</em></div>
    <div style="float: right;">June 2024 (expected)</div>
</div>
<p>University of Toronto Scarborough<br>
* Relevant Coursework: Data Analysis, Regression Analysis, Time Series Analysis, Data Visualization, Web Development</p>

## Projects
### Course Website | Python, SQL, HTML, CSS
Github: [Course Website](https://github.com/ShuvarthyD/Course_Website) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Cloud Version: [shuvarthyd.pythonanywhere.com](https://shuvarthyd.pythonanywhere.com/)
\<br>
A responsive Web Development course website created using the [Flask](https://flask.palletsprojects.com/en/3.0.x/) web framework, along with the extension [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/3.1.x/) to edit and manage the database. Users initially only have access to basic course information, but can choose to **login** or **register** as a **student** or **instructor** to access additional features. Instructors can access their account page to view feedback, edit student marks, and access visualizations and analyses of student mark data (see Figure 1) student mark data. Students can submit remark requests, send feedback, and view their grade summary. Although SQLAlchemy has its own "Pythonic" way of handling databases (ORM), I prefer using raw SQL queries as it is much easier to read and maintain.

### Linear Regression Analysis of Systolic Blood Pressure | R
\<br>
In this project I analyze the effects of 10 genetic markers along with 17 clinical covarites have on the systolic blood pressure (SBP), and create a prediction model for the SBP. The steps taken are as follows:
<p align="center">
</p>
1. Implement a dummy coding scheme for the catagorical variables in the dataset. In R this can be achived by using rhe **relvel** function and setting the reference level using the **ref** parameter.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
2. Excluding the 10 genetic markers, find which varibles are highly correltated and only include one of them in the linear model as predicators with high correlation can lead to collinearity issues.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
3. Create the linear model in R and intrepret some of the regression parameters:
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
4. Use a partial F-test to test the joint effect of the joint effect of the 10 genes at α = 0.05. Our null hypothesis is all the beta values for the 10 genes = 0. Using the anova() function we input the original model and a reduced model without the genetic markers and obtain a p-value of **0.0455** < α = 0.05. Thus we reject the null hypothesis and conclude that
there is a joint effect of the 10 genes on sbp.
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
5. Use both the forward selection and backward elimination strategies to obtain a prediction model. The **MASS** package in R contains **stepAIC** function to implement both strategies. Although a 5-fold cross-validation can be conducted to calculate the mean squared prediction error (MSPE) for each model, this is not neccesary as the results show that both stratigies show the same model. 
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>
<p align="center">
  <img src="http://some_place.com/image.png" />
</p>
<p style="text-align: center;">Text_content</p>

### Wavelength Calibration | Python
This project is seperated in two parts. In the first part I find a wavelength solution of neon lamp spectra by getting a linear fit between the intensity and pixel positions.


