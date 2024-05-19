## Technical Skills
<b>Programming:</b> Python, R, SQL <br>
<b>Platforms & Tools:</b> VS Code, Jupyter Notebook, R Tidyverse, Python Pandas, Git

## Education 
<div style="overflow: hidden;">
    <div style="float: left;"><em>HBSc, Major in Statistics</em></div>
    <div style="float: right;">June 2024 (expected)</div>
</div>
<p>University of Toronto Scarborough<br>
<b>Relevant Coursework:</b> Data Analysis, Regression Analysis, Time Series Analysis, Data Visualization, Web Development</p>

## Projects
### Course Website | Python, SQL, HTML, CSS
<b>Github:</b> [Course Website](https://github.com/ShuvarthyD/Course_Website) &nbsp; &nbsp; &nbsp; &nbsp; <b>Cloud:</b> [shuvarthyd.pythonanywhere.com](https://shuvarthyd.pythonanywhere.com/)
<br>
A responsive Web Development course website created using the [Flask](https://flask.palletsprojects.com/en/3.0.x/) web framework, along with the extension [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/3.1.x/) to edit and manage the database. Users initially only have access to basic course information, but can choose to **login** or **register** as a **student** or **instructor** to access additional features. 
<ul>
  <li>Instructors can access their account page to view feedback, edit student marks, and access visualizations and analyses of student mark data.</li>
  <li>Students can submit remark requests, send feedback, and view their grade summary.</li>
</ul>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/CW6.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>Used raw SQL queries instead of SQLAlchemy's "Pythonic" way of handling databases (ORM)</em></p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/CW1.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>View grade distribution by selecting an assessment and grading system</em></p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/CW2.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
  <div style="margin: 0 10px;">
    <img src="{{ "/img/CW3.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>View the top students for each assesment and a correlation heatmap</em></p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/CW5.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>Students can view their grades compared to the class averages</em></p>

### Linear Regression Analysis of Systolic Blood Pressure | R
In this project, I analyzed the effects of 10 genetic markers alongside 17 clinical covariates on systolic blood pressure (SBP) and developed a prediction model for SBP. The steps taken were as follows:
<p align="center">
</p>
<ol>
  <li>Implemented a dummy coding scheme for the categorical variables in the dataset. In R this can be achieved by using the <b>relvel</b> function and setting the reference level using the <b>ref</b> parameter.
      <br>
      <p align="center">
          <img src="{{ "/img/SBP1.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
      </p>
      <p style="text-align: center;"><em>Dummy coding scheme for 2 of the clinical covariates</em></p>
  </li>
  <li>Excluding the 10 genetic markers, I found which variables are highly correlated and only included one of them in the linear model as predictors with high correlation can lead to collinearity issues.
      <br>
      <p align="center">
          <img src="{{ "/img/SBP2.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
      </p>
      <p style="text-align: center;"><em>High correlation between the "BMI" and "overweight" variables</em></p>
  </li>
  <li>Created the linear model in R and interpreted some of the regression parameters:
      <br>
      <p align="center">
          <img src="{{ "/img/SBP3.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
      </p>
      <p style="text-align: center;"><em>...</em></p>
  </li>
  <li>A partial F-test was used to test the joint effect of the 10 genes at α = 0.05. This was achieved in R using the <b>anova</b> function using both the original model and a reduced model excluding the genetic markers as the parameters.
      <br>
      <p align="center">
          <img src="{{ "/img/SBP4.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
      </p>
      <p style="text-align: center;"><em>Derived a p-value of <b>0.0455</b> < α = 0.05, so we reject the null hypothesis and conclude that there is a joint effect of the 10 genes on SBP.</em></p>
  </li>
  <li>To obtain a prediction model, both forward selection and backward elimination strategies were utilized. The <b>MASS</b> package in R contains the <b>stepAIC</b> function to implement these strategies. Although a 5-fold cross-validation could have been conducted to calculate the mean squared prediction error (MSPE) for each model, it was deemed unnecessary as the results for both strategies led to the same model.
      <br>
      <p align="center">
          <img src="{{ "/img/SBP5.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
      </p>
      <p style="text-align: center;"><em>Both the forward and backward test in R</em></p>
      <p align="center">
          <img src="{{ "/img/SBP6.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
      </p>
      <p style="text-align: center;"><em>The obtained prediction model</em></p>
  </li>
</ol>

### Wavelength Calibration | Python
This project is divided into two parts, both aimed at obtaining a wavelength solution by finding an appropriate fit between the peak wavelengths and pixel positions of a given dataset.
#### Part 1
<p>Given a Neon Lamp Spectrum where the peak wavelengths were obtained manually and the peak pixel positions were found using the <b>find_peaks</b> function from the <b>scipy</b> package. Since the given measurements may contain observational errors, I opted to use the weighted means of the peaks. To do this I picked an acceptable range of &pm;10 pixels of the identified peaks and plugged it into the <b>centroid</b> formula <img src="https://latex.codecogs.com/svg.image?&space;X_{cent}=\frac{\sum&space;x_{i}I_{i}}{\sum&space;I_{i}}"/>. Then a simple linear fit was made using the <b>polyfit</b> function to obtain the wavelength solution.</p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/WC1.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>Major identified peaks over the intensity value of 300 with the acceptable error range</em></p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/WC2.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>linear fit of the wavelengths and centroids</em></p>
<p>Part 1 wavelength solution: <img src="https://latex.codecogs.com/svg.image?\lambda=(0.236\pm&space;0.000)x&plus;(527.843\pm&space;0.297)" style="vertical-align: middle;"/> </p>
#### Part 2
Manually obtained both the peak wavelengths and their pixel positions. However a linear fit was insufficient, so I used a residual plot to compare the accuracy of the different degrees of fit. From the residual plots shown below, we can see that the residuals for all 3 fits are random implying they are all suitable fits. But we also notice that the residuals for the cubic fit seem to be closer to having a fitting error of 0 on average, which can be further noticed in the histogram. Thus the polynomial with degree 3 was chosen as the best fit.
<p align="center">
  <img src="{{ "/img/WC3.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
</p>
<p style="text-align: center;"><em>Three degrees of polynomial fit along with its coefficients</em></p>
<div style="display: flex; justify-content: center;">
  <div style="margin: 0 10px;">
    <img src="{{ "/img/WC4.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
  <div style="margin: 0 10px;">
    <img src="{{ "/img/WC5.png" | prepend: site.baseurl | prepend: site.url}}" alt="Untitled" />
  </div>
</div>
<p style="text-align: center;"><em>The residual plot and distributions of different polynomial fits</em></p>
<p>Part 2 wavelength solution: <img src="https://latex.codecogs.com/svg.image?\lambda=-(0.065\pm&space;0.038)x^{2}&plus;(12.287\pm&space;4.762)x&plus;(15530.984\pm&space;189.504)" /></p>

