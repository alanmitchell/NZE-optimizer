# Construction Cost Optimizer for Net Zero Homes

This is a Microsoft Excel model for determining the levels of insulation and PV (Solar) panels that minimize the construction cost of a Net Zero Energy home.  This model was born out of Net Zero discussions amongst members of the [Alaska Center for Appropriate Technology](http://acat.org/).

[Click here to Download the Excel Model](Net_Zero_Optimizer.xlsm?raw=true)  
When you open the Excel workbook, you need to click the button at the top of the workbook to "Enable Content" (Macros), as the workbook has a macro attached to the "Optimize" button.  Also, this workbook uses the Excel Solver Add-In, which is provided by Microsoft with Excel.  However, the Solver Add-In needs to be enabled according to these instructions (this only needs to done once for installation of Excel):

[Load the Solver Add-In](https://support.office.com/en-us/article/Load-the-Solver-Add-in-612926fc-d53b-46b4-872c-e24772f078ca)

The model accounts for the Lights and Appliances, Space Heating, Domestic Water Heating, and Solar Electric production of a home.  Currently, the model has an optimize feature that will try various combinations of four home characteristics to reduce the net energy use of the home to zero and to minimize the construction cost of the home.  All of the other home characteristics that affect energy use are not currently involved in the optimization process but could be added as the model evolves.  These other characteristics of the home are manually entered by the user. For example, the user can enter in a Window R-value of 6.0; the optimization process will not change that value.

The four characteristics that are controlled by the optimzation are:

* The kilowatt capacity of the Photovoltaic Solar system (PV system).
* The insulating R-value of the Walls.
* The insulating R-value of the Ceiling.
* The insulating R-value of the Floor.

Numerous combinations of these characteristics can result in Net Zero energy use.  Relatively low levels of insulation can be combined with large amounts of PV capacity to produce a Net Zero home.  Or, high insulation and more modest amounts of PV panels can be used to be Net Zero.  The optimization process in the model picks the combination that minimizes the construction cost of the home.  Simple, linear cost estimates are used for these four energy features of the home.

Here is a screenshot of the key values that are optimized and the cost inputs associated with those characteristics:

![Optimization Inputs](images/opt_inputs.jpg)

The thick bordered box on the left highlights the four characteristics that are manipulated in the optimizatio process.  The gray "Optimize" button starts the optimization, and Excel finds the cost-minimizing values for the PV capacity and the three R-values.  In this example, the home reached net zero and minimized construction cost with 9.13 kW of PV, R-29 Walls, R-56 ceilings, and R-45 floors (the model simplifies and assumes all R-values and PV outputs are possible.  The model could be modified to only allow certain discrete possibilities.)

To Be Continued!
