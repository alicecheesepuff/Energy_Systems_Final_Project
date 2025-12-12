Overview:
The code in "Project4_4_all.ipynb" solves a wind farm sizing and siting optimization problem on the IEEE-14 bus test system. The model determines optimal wind farm locations and capacities while considering transmission constraints, generation costs, and five demand and wind capacity factor scenarios.

Please reference "Project4_1.ipynb," "Project4_2.ipynb," and "Project4_3.ipynb" for steps taken to formulate the model, as outlined in the project directions.

Requirements:
pip install cvxpy numpy pandas matplotlib networkx
pip install pyscipopt

How to run:
Set parameter values in the code block below the constraints section. For example:
candidates.value = 1  # Number of wind farm sites allowed
Cinv.value = 2.5      # Investment cost ($/MW)

For discrete siting constraint, set solver to "SCIP" and candidates to 1. To allow all potential wind sites, set candidates parameter to 4. If you wish to use "HIGHS," you can comment out the following constraint: 
# discrete siting constraint
con.append(y <= cp.multiply(z, ybar))
con.append(sum(z) <= candidates)