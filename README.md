# Construction Cost Optimizer for Net Zero Homes

This is a Microsoft Excel model for determining the levels of insulation and PV (Solar) panels that minimize the construction cost of a Net Zero Energy home.  This model was born out of Net Zero discussions amongst members of the [Alaska Center for Appropriate Technology](http://acat.org/).

[Click here to Download the Excel Net Zero Energy Optimizer Model](Net_Zero_Optimizer.xlsm?raw=true)  
When you open the Excel workbook, you need to click the button at the top of the workbook to "Enable Content" (Macros), as the workbook has a macro attached to the "Optimize" button.  Also, this workbook uses the Excel Solver Add-In, which is provided by Microsoft with Excel.  However, the Solver Add-In needs to be enabled according to these instructions (this only needs to done once for installation of Excel):

[Load the Solver Add-In](https://support.office.com/en-us/article/Load-the-Solver-Add-in-612926fc-d53b-46b4-872c-e24772f078ca)

The blue numbers in the model are inputs that can be changed by the user.  Black numbers are formulas, which are calculated from the user inputs.

The model accounts for the Lights and Appliances energy use, Space Heating energy use, Domestic Water Heating energy use, and Solar Electric production of a home.  The model has an optimize feature that will try various combinations of four home characteristics to reduce the net energy use of the home to zero while minimizing the construction cost of the home.  All of the other home characteristics that affect energy use are not currently involved in the optimization process but could be added as the model evolves.  These other characteristics of the home are manually entered by the user. For example, the user can enter in a Window R-value of 6.0; the optimization process will not change that value.

The four characteristics that are controlled by the optimization are:

* The kilowatt capacity of the Photovoltaic Solar system (PV system).
* The insulating R-value of the Walls.
* The insulating R-value of the Ceiling.
* The insulating R-value of the Floor.

Numerous combinations of these characteristics can result in Net Zero energy use.  Relatively low levels of insulation can be combined with large amounts of PV capacity to produce a Net Zero home.  Or, high insulation and more modest amounts of PV panels can be used to be Net Zero.  The optimization process in the model picks the combination that minimizes the construction cost of the home.  Simple, linear cost estimates are used for these four energy features of the home.

Here is a screen shot of the key values that are optimized and the cost inputs associated with those characteristics:

![Optimization Inputs](images/opt_inputs.jpg)

The thick bordered box on the left highlights the four characteristics that are manipulated in the optimization process.  The gray "Optimize" button starts the optimization, and Excel finds the cost-minimizing values for the PV capacity and the three R-values.  In this example, the home reached net zero and minimized construction cost with 8.94 kW of PV, R-28 Walls, R-55 ceilings, and R-45 floors (the model simplifies and assumes all R-values and PV outputs are possible.  The model could be modified to only allow certain discrete possibilities.)

Note that you can manually type in values for the four characteristics to test out your own possible solutions.  These values will be over-written by the Solver if you later run the Optimize feature.  When you do run the Optimize feature, make sure the starting values in the cells are reasonable or Solver may have difficulty finding a solution.

## Incremental Construction Costs

It is important to understand the meaning of the cost values shown in the screen shot.  The optimization involves trying various values of PV output and R-values.  The test is whether increasing PV output by a certain amount and decreasing R-values results in lower costs while still maintaining net zero energy use.  The relevant cost characteristics are the *incremental costs* of adding/removing PV capacity and adding/removing R-value.  Any fixed costs of installing the PV system, such as the electrical connection costs, are not relevant because those costs are close to the same for all relevant levels of PV capacity.  Wall construction also has a number of fixed costs that are not related to the R-value of the wall (siding costs, sheetrock costs, etc).  These costs should be ignored when entering the incremental costs in the model.

In the example above, the incremental PV cost is shown as $3,300 / kW.  That means that the cost of adding an additional section of panels and associated inverters/racking to the system divided by the extra capacity provided by those panels is $3,330 per kW added.  The incremental Wall R-value cost is shown as $0.15 / R-value / square foot.  This figure is consistent with adding an additional R-10 to the wall design for a cost of $1.50/square-foot:   `$1.50/ft2 / R-10 = $0.15/R-value/ft2`.  These cost numbers have not been researched thoroughly and depend on the design of these components.  But, $0.15/R-value/ft2 is an estimate reasonably consistent with a wall using rigid foam to achieve additional R-value beyond that provided by a batt or cellulose-filled wall cavity.

One common situation where these linear cost estimates break down is when there is limited space to install a PV system.  Available roof space will be exceeded at some point, and additional capacity is either not possible or must be more-expensively ground mounted.  The model can somewhat accommodate this situation through use of the "Limit on PV capacity due to space" input shown above.  If you know that you can only install as much as 8 kW of PV on your roof, then you can enter this 8 kW limit for this input.  When the optimization is run, it will limit the amount of PV capacity used (the optimizer may choose to use less than the limit value if doing so minimizes costs).  Note that if you set this limit too low, the Excel Solver may not be able to find a solution that results in Net Zero energy use.  No level of Wall/Floor/Ceiling R-values will be able to drop energy use to net zero with the limited amount of PV capacity.

To Be Continued!
