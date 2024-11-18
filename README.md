
SOLA5052 Bioenergy  Renewable Fuels
Major Assignment: Equilibrium Products from a Downdraft Biomass Gasifier
Due date, FIRST assessment: 11:55 pm, Monday, 21st  October 2024 (beginning of Week 7)
Due date, FINAL assessment: 11:55 pm, Monday, 11th  November 2024 (beginning of Week 10) People have generally found this assignment difficult. Start early.
Assignment worth: 25% of your final grade for the course. The assignment is marked out of 130.
This assignment is individual work.
Submission instructions:
•   On Moodle using the assignment submission tool.
•    FIRST submission, must be complete to Question 6.java c
•    FINAL submission, must complete Questions 7 and 8 (finish all questions).
•    Important: marks may be deducted for not strictly adhering to the following instructions, where “9999999” is your student number.
•    Use the following information in the file name of ALL your submissions: SOLA5052 Assignment 1 Submission z9999999
•    Put all files in an attached zipped folder named z9999999.zip.
•    For the main report, please submit a PDF file, named as z9999999_A1_report.pdf
•    For other files, e.g. Excel spreadsheet, be sure to include your student number in the file name, such as z9999999_A1_worksheet.xlsx
Late submission penalty: 30% plus 10% for each full day late (e.g. 3 full days late, you lose 60% of the mark you would have otherwise achieved; less than one full day late = 30%).
Assignment instructions:
•   The assignment consists of deriving equations for calculating the equilibrium products and temperature of a downdraft gasifier for a reasonably complete set of chemical species and with variable specific heats.
•   The assignment submission consists of a written report answering the questions posed, plus the software used to perform. the calculations.
•   The calculations will be done using Microsoft Excel. A template has been provided for this purpose: z9999999_A1_worksheet.xlsx,  and  will  be  referred  to  henceforth  as  “the spreadsheet” .
•   The spreadsheet gives only a structure and some key data required for the assignment. You will need to provide the formulae required in all of the yellow cells, and finally program the spreadsheet to perform. a constrained optimisation, which will give results in the green cells.
Downdraft biomass gasifierFigure 1 shows a schematic of a downdraft biomass gasifier. Biomass fuel is fed in the top and air is fed in part way into the reactor. There is not sufficient air to lead to complete combustion, so the product stream is a mixture of combustible gases, principally H2  and CO and N2 , plus a biochar product which we will treat here as simply solid carbon.If there is sufficient residence time in the gasifier, the product  gases  will  be  a  close  approximation  to equilibrium products. The task of the assignment is to determine the  composition  and temperature of the products.Unlike the idealised questions in workshops and the exam,  the  analysis  will  consider  variable  specific heats  and  a  reasonably  complete  set  of  chemical species.In the assignment, you will gradually build a model of the gasifier, entering formulae for key quantities as functions of other quantities in the spreadsheet.

Figure 1: Schematic of downdraft gasifier
The following species are considered here:Wood (CHxOy)Not technically a chemical species however the heating value and ultimate analysis are knownC(S)Solid carbon, approximating charH2O(L)Liquid waterCO2 ,CH4 ,CO,O2 ,O,H2 ,H2O:Gas phase species
1) Stoichiometry (10 marks)
Let the gasification of wood in air be denoted by the following overall chemical reaction:
CHxOy+ A (O2  + 3.76N2) + B H2O(L) → np,C(S)  C(S) + np,CH4  CH4  + np,O2  O2 + np,CO2  CO2  + np,CO  CO
+ np,H2O  H2O + np,H2  H2  + np,O  O + np,N2  N2
Note: all the calculations are going to be referenced to this equation, that is, all of the extensive values (e.g. kg, J, etc,) are implicitly per kmol of C in the biomass.
An ultimate analysis shows that in dry wood the O:C ratio and the H:C ratio can be calculated as follows:
where O:C (or y) is 2 times the highest digit in your zID divided by the summation of all the digits, and H:C (or x) is two minus the O:C ratio.
a)  Using  the  above  ratios,  determine  the  formula for the factor A for  complete stoichiometric combustion, showing working, and enter it in cell B10 in the spreadsheet. (2 marks)
b)  Determine  the  stoichiometric  mass-based  Air-to-Fuel  ratio  (AFRst)  for  dry  wood,  showing working, and enter it in cell B11 in the spreadsheet. (2 marks)
c)  If the actual air-to-fuel ratio is AFR, what is the relative air-fuel ratio, λ? (Note: λ = 1/ϕ , where ϕ is equivalence ratio). Enter the formula in cell B12 in the spreadsheet (as a function of the other spreadsheet variables, e.g. the AFR in cell B8). (2 marks)
d)  Determine the factor A for a general AFR, and enter the formula in the cell B13 in the spreadsheet (as a function of the other cells, e.g. λ in cell B12). (2 marks)
e)  If the moisture content is W (kg water/kg wet biomass), what is the molar ratio of water to (dry) CHxOy (i.e. B in the chemical reaction equation)? Enter the formula in the spreadsheet in cell B14
(as function of other cells, e.g. W in cell B7). (2 marks)(At this point I assume that you have got the idea of filling in formulae based on other cells in the spreadsheet, where formulae are requested after this consider it as implicit that they are based on other cells in the sheet representing key variables or input data.)
2)        Derivation of NASA polynomials  (10 marks)
The standard-state molar specific heat at constant pressure of a species “k” can be approximated a “NASA polynomial” [1]. The NASA polynomial for the mole-based cp,k is:

where Ru is the universal ideal gas constant, and a1k-a5k are constants. Use basic definitions (week 4/5 lecture) to show that

and

where hk and s0k are the standard state molar enthalpy and entropy of the pure species respectively and a6k , a7k  are constants.Also determine the standard state molar Gibbs energy of the pure species gk in terms of hk and s0k.
Note: the molar entropy in the above definition does not include the mole fraction and pressure dependent entropy of mixing term, since this is for the pure species at the reference pressure.
3)        Evaluation of NASA polynomials  (10 marks)The data for the NASA polynomials is normally given over two temperature ranges, a high and a low temperature range, delineated by a temperature Tcut. The data for a number of chemical species are given in the spreadsheet in the cell-block E18-Z25. The coefficients aik for each species are arranged as two columns. The column directly under the species name corresponds to the low-temperature range (T
An example for how to use these data is given in the calculation of the species specific heats cp,k, for example, for C(S) in cell G30.Wood here is a special case as only the heating value is needed. Therefore most of the coefficients are zero. (We do not really mean that the cp and s are zero, they are just not needed for the calculations.)
a)  Using the results of Question 2, fill in the formulae for hk, sk and gk of all the available species in the spreadsheet (yellow cells, E31-Y33 for reactants and E50-Y52) as functions of the variables Tr (reactant temperature, in cell B29), Tp  (product temperature, in cell B48), and the species a1k- a7k.                                                                                                  (0.5 mark each, 4 total)
b)  In your written report, present a table of the  values of hk, sk, and gk for each species at the temperature Tr  = 1000 K (the entropy of wood is not known, so write N.A. there for g and s).  (1 mark)c)  To check your work so far, given that the lower heating value of the oven-dry wood is 22 MJ/kg,
an H:C ratio of 1.5 and an O:C ratio of 0.5, show that the value of a6        -1.227E4.     (5 marks)
4)        Reactant mixture properties  (5 marks)
Let nr,k be the number of kmol of the kth species per unit “kmol” of dry biomass fuel defined as CHxOy. Per 1 kmol of C in the dry biomass:
a)  Determine a formula for the total mixture enthalpy Hr, (kJ) and write this in your final report.  (2 marks)
b)  Enter the formula into the appropriate cell of the spreadsheet (B40), (intermediate calculations using the other entries of row 40 may be helpful).                                                           (2 marks)
c)  In your report, evaluate these quantities for reactants initially at Tr = 298 K and AFR = 2.0, and 20% m代 写SOLA5052 Bioenergy & Renewable FuelsPython
代做程序编程语言oisture.                                     (1 mark)
5)        Product mixture properties  (15 marks)
Let np,k be the number of kmols of the kth species per unit kmol of C in the dry biomass fuel in original reactants. The gasification occurs at constant (atmospheric) pressure.
For each of the quantities:
a)        mixture enthalpy, Hp (kJ)                                                                                             (5 marks)
b)        mixture entropy, Sp , (kJ/K) (see over for important notes)                                         (6 marks)
c)        mixture Gibbs energy, Gp (kJ)                                                                                     (4 marks)
i)         determine a formula for the quantity and write this in your final report,
ii)        enter the formula into the appropriate cell of the spreadsheet (B59-B61), taking advantage of cells E59-Y61 to figure out individual species contributions to the total, andiii)       in  your  report, evaluate these quantities for  products at a temperature Tp  = 2000 K and pressure P = 1 atm, at stoichiometric conditions and assuming complete combustion, no dissociation and completely dry biomass.
Important notes:The species entropy including entropy of mixing is given by: sk  = sk(o) −  RulnXk,where Xk is the mole fraction of the species k in its phase (i.e. gas or solid here), and sk0 is the standard entropy of the species k when as a pure compound (i.e. not in a mixture of many different species). C(S) is assumed to be the only solid phase species in the products.Given that Xk = 0 (i.e lnXk   →   −∞) is a possibility, you will need to code your answer for sk  in such a way that it gracefully deals with this (i.e. the formula returns a sensible numerical value rather than infinity or “not a number”). In doing so you may take advantage of L’Hôpital’s rule which shows that:

I advise that you run tests to check that your solution does indeed give sensible results on this point, as not doing this correctly will lead to problems later.
6)        Element numbers  (10 marks)
a)  Determine a general formula for the kmols of C, H and O atoms NC , NH , and NO  (per C in the original dry biomass) in terms of the nk,p’s or nk,r’s for any combination of the previously listed molecular species.      (8 marks)b)  Enter the appropriate formulae for reactants in cells B43-B45 and for products in cells B64-B66. (2 marks)
STOP HERE FOR FIRST/MID-TERM SUBMISSION, 11:55pm 21st  OCTOBER 2024, WEEK 7. SUBMIT USING THE FIRST ASSIGNMENT SUBMISSION ON THE MOODLE PAGE.
7)  Equilibrium calculation                                                                           (50 marks)You are to calculate the equilibrium flame temperature and full composition for AFR = 2.0 and 20% moisture. The reactant temperature is 298  K. The gasification occurs at constant atmospheric pressure of 1 atm.To find the equilibrium condition, you will need to solve a constrained optimisation problem, using the Solver feature of Excel. This solver will converge well if you have set up the problem correctly and if you give it a good initial guess. If you give it a poor initial guess, it will either not converge at all or converge slowly.
To generate an initial guess, let us first assume we know that the product temperature is 1000 K. We seek now only to find the product species compositions at this fixed temperature.
a)  What constraint does the second law of thermodynamics impose on the equilibrium state in this situation? Explain in simple words.          (5 marks)
b)  What other constraints are imposed by mass considerations? Hint: there are two constraints. (10 marks)
c)  Use the “Solver” feature of Microsoft Excel to calculate the equilibrium state at 1000 K. You may need to install the Solver add-in first – check the help. An example of how to use this function is given in the spreadsheet under the tab “Solver Example” . Basically, it tries to maximise or minimise some cell by varying other cells, with constraints on how the cells can be varied.You will need to give the solver an initial guess. Many good initial guesses will lead to a solution. One approach  may  be  provided  by  noting that  apart from  N2   (which  is  nonreactive  and  is therefore the same in the products as in the reactants), the major products are likely to be CO, H2 , H2O and CO2 . This system is under-determined, more unknowns than equations, though you may guess an amount of the C that ends up in CO and CO2 , or similarly an amount of the H that ends up in H2 or H2O, which would allow you to determine a solution that satisfies the constraints to use as an initial guess.After obtaining a converged solution, list the kmol (per kmol of C in the biomass) you obtain of each of the product chemical species in a table in your report (you only need to list the values for C(S), H2 , CO and CH4).
Note also that you can and must save your solver settings – click the load / save option and put them in a free space of a number of cells that solver will tell you it needs.  (15 marks)Now having a good initial guess, you need to solve for the full equilibrium, including the temperature. You can assume there is no heat loss in the gasification process. In principle you could do this iteratively using the method in d) by a bisection search at different temperatures to satisfy the first law of thermodynamics, but there is a faster method, which uses the first law of thermodynamics directly in the Solver, and which converges reliably given a good initial guess.
d)  Apply the  1st   law  of thermodynamics to the  biomass gasifier.  First write down the complete equation of the 1st  law applicable to the situation of the gasifier. Use assumptions like negligible heat loss and work transfer, steady state assumption etc. to arrive at a simplified expression.  (5 marks)
e)  What constraint does the second law of thermodynamics impose on the equilibrium state in this situation? Explain in simple words.            (5 marks)
f)   Now recalculate the equilibrium, taking into account the first law condition and the revised second law condition. Start from the initial guess in part c). Write the temperature and species kmol (for C(S), H2 , CO and CH4) you obtained in a table in your report, and submit your Excel spreadsheet set up to solve this problem together with your report.  (10 marks)
* If you are really struggling to get a converged solution, ask a demonstrator, bringing your Excel sheet with you, and being prepared to discuss why you made the choices you did.
8)        Effect of AFR  (20 marks)In this question you will use the tool you developed to find out how AFR will affect your product yield. The product gases are cooled to 298 K and the water is condensed out. The gasifier can be operated between AFR of 1.0 and 3.0.
a)  First, determine formulae for the m3  yield, per kg of dry biomass for each of the gases CO, H2 , CH4 , and the remaining lumped together gases. (Remember that water is condensed out.) Write the formulae in the written report and enter the formula in cells E65-E68. Also enter a formula for the char yield, in kg C(S)/kg dry biomass and enter it in cell E69.  (5 marks)
b)  Second, determine a formula for the LCV of the cooled gas in a). Although the calorific value can be calculated from the NASA polynomials, here it is sufficient to assume that only CO, H2 , and CH4  contribute to the calorific value, and that their calorific values are 11.6 MJ/m3 , 9.89 MJ/m3 and 32.8 MJ/m3 , respectively.) Write the formula in your report for the LCV (MJ/m3) of the gas (including the diluents in the volume), and in the spreadsheet enter the LCV values on a volume basis (MJ/m3) and per kg of the original dry biomass (MJ/kg dry biomass) in cells E71 and E72, respectively. (5 marks)
c)  Finally, use the solver to determine the gas yields in m3/kg biomass (CO, H2 , CH4 , and the remaining lumped together diluents), the char yield in kg/kg dry biomass and the LCV of the gas in kg/kg dry biomass for the AFR values of 1, 2 and 3 (with all other parameters the same as in question 7 part f). Present this information graphically and make a comment on the trends.    (10 marks)
End of assignment. Submit using the Assignment Submission Tool on the course Moodle page by 11:55 pm, Monday, 11th  November 2024 (beginning of Week 10).
ReferencesS. Gordon and B. J. McBride, "Computer Program for Calculation of Complex Chemical Equilibrium Compositions,  Rocket  Performance,  Incident  and  Reflected  Shocks  and  Chapman-Jouguet Detonations" NASA Report SP-273, (1971).

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
