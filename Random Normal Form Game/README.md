# Experiment settings.

Games were generated using GAMUT [1]. The default payoff range is used, i.e. [-100, 100]. Approximation values are not normalized, i.e. lie in the range of [0, 200]. No game is larger than 4GB.

MIP was solved using CPLEX [2] which was given 1 hour (3600 seconds) of running time and 4GB memory. If CPLEX exceeded either of these limits, the process was killed.

# File nomenclature.

*nbOfInstances_gameName_nbOfPlayers_nbOfActions_metaTime.txt*

- nbOfInstances = number of instances in this file.
- gameName = name of the game. here: Random Normal Form Game (RNFG).
- nbOfPlayers = number of players in the instances.
- nbOfActions = number of actions each player has in the instances.
- metaTime = time given to the metaheuristics.

e.g. *10_RNFG_3_4_60.txt* contains 10 instances of Random Normal Form Games with 3 players each having 4 actions. Metaheuristics were given 60 seconds of running time.

# File contents.

Per instance, the seed for GAMUT is given. Setting the seed in GAMUT will allow generating the exact same instance.
Set the seed in GAMUT by setting the `Global.randSeed` variable to the wanted seed. Then make a new RNG by setting `Global.rand = new Random(Global.randSeed);`.

For each instance, results for each metaheuristic is given as wel for the MIP.
- SHC = Shotgun Hill Climbing = Random Restart Hill Climbing.
- SA = Simulated Annealing.
- CLO = Chained Local Optimization.
- MIP = Mixed Integer (Linear) Programming.

*method : found_solution approximation_value time*

- method =  SHC/SA/CLO/MIP
- found_solution = the best solution found in the reported time. In case of MIP: *infeasible* (no PNE), found_solution (= PNE), *OUT OF TIME* or *OUT OF MEMORY*.
- approximation_value = The approximation value. 0 means the found_solution represents a PNE. Not reported for MIP.
- time: running time.

# Contact.
Got suggestions, comments, questions and/or insults? Don't hesitate: niels.elgers@student.kuleuven.be

[1] GAMUT : http://gamut.stanford.edu/ 

[2] CPLEX : https://www-01.ibm.com/software/commerce/optimization/cplex-optimizer/
