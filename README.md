# Personalised_Mixed_Meal_Model
Code accompanying "Towards precision; utilising personalised computational models to quantify the effect of nutirtional interventions on metabolic resilience" The Personalised Mixed Meal Model MATLAB implementation includes functions to fit the Mixed Meal Model to individual meal response data and to visualise the results. The M3al_Calculator.exe installs a stand alone application with a user friendly GUI that will allow you to fit the Mixed Meal Model to user supplied meal response data using Matlab RunTime. Matlab version: R2019b

_____________________________________________________________________________________________________________________________________________________

Included functions include
______________________________________________________________________________________________________________________________________________________
**M3al_Model_ODE.m** - Mixed Meal Model equations.
**M3al_Model_Initial.m -** Specify initial values and model constants necessary for the Mixed Meal Model to simulated.
**M3al_Model_Parameters.m** - Defines parameter values for Mixed Meal Model. 
**integratorfunG.m **- Calculate the integral of plasma glucose for PID controller. 
**M3al_Model_ErrorFunc.m **- Calculate the error used in the model fitting/optimisation procedure. 
**Fit_M3al_Model.m **- Function fitting the Mixed Meal model to supplied challenge test data.(single fitting using lsqnonlin) 
**Fit_M3al_Model_LatinHyperCube.m **- Function fitting the Mixed Meal model to supplied challenge test data using multiple initial values defined using a latin-hypercube design. 
**Fit_M3al_Model_Individual.m** - Fit the Mixed Meal Model to individual meal reponse data (row) provided in an array of multiple individual repponses. 
**Plot_M3al_Model.m **- Generate figure showing Mixed Meal Model simulation for a specified parameter set. 
**Plot_MultiFit_M3al_Model.m **- Generate figure showing multiple Mixed Meal Model simulations for each fitting generated using multiple initial values from the Fit_M3al_Model_LatinHyperCube.m function.
**Plot_Individual_M3al_Model.m **- function that takes in a struct of several individual model fits generated using the Fit_M3eal_Model_Individual.m function and creates a  separate figure showing each model fit.
**sample_data.mat** - Sample meal response data for five synthetic individuals. 

**M3al_Calculator.exe**-File to install the Meal Model Calculator, a stand-alone application with a GUI that allows the user to enter measured plasma glucose, insulin, NEFA, and triglyceride data in response to a meal and to then generate a personalised Mixed Meal Model. The Meal Model Calculator uses a multi-start approach. THe Meal Model Calculator will then visualise all the personalised model fits obtained using the multi-start and provide the estimated parameter values for the fit with the lowest sum of squared errors between the model simulation and provided data. The Meal Model Calculator makes use of MATLAB RunTime to allow the use of the app without the need for a MATLAB license. 

__________________________________________________________________________________________________________________________________________________________
Use
__________________________________________________________________________________________________________________________________________________________
To fit the Mixed Meal Model to an array of personalised meal responses (columns correspond to time points and row correspond to individuals) use the Fit_M3al_Model_Individual.m function as shown below

individual_fitting = Fit_M3al_Model_Individual(sample_data,num_init

Where sample_data is the measured meal response data organised in a meal response struct and num_iniit is the number of initialisation you with to use for lsqnonlin. 
The output of the function is the individual fitting struct which contains

 
 For further information or questions please contact Shauna O'Donovan at s.d.odonovan@tue.nl.
