# QHack2023OpenHackathon

This is the project in QHack2023OpenHackathon Quantum Chemistry Challenge.

## Calculate the BeH2 ground state energy

There are many different ways to calculate a ground state energy of a molecule. In particular, VQE, one of hybrid quantum-classical algorithms, receives people's attention in both sides, accuracy and feasibility.  
On the other hand, it is also known that VQE needs much time to run. So it can be said that VQE algorithm could still not bring out the potential of Quantum Computer. However, to obtain benefits from the full potential, we have to wait for Fault Tolerant QC. In this project, with the simulator without noises, we run the algorithm for FTQC and calculate the ground state energy more efficiently.  

## How to

We followed [Sugisaki et al.(2021)](https://doi.org/10.1021/acs.jpclett.1c03214)'s method generally. This method uses Quantum Phase Estimation to calculate a state energy as an eigenvalue of Hamiltonian. In usual Bayesian Phase Estimation methods, the Hamiltonian, which is trottered into extremely complex gate, must be a controlled one, then they proposed a new method, Bayesian Phase Difference Estimation, in which the controlled gate will be Prep gate instead of Hamiltonian. It can reduce the CNOT gate, which causes noises, and make the circuit less complex.  

We constructed the circuit following Fig.1(b) in the paper, and optimized the Energy with Eq.2 in the paper and ternary search algorithm.  
In this method, we have to prepare the wave function correponding to the Energy. In the paper they calculate this *a priori*, but it was a little difficult for an amatuer at chemistry, so we invent the plan to use the moderate-optimized VQE ansatz as an approximate eigen wave function. 

## Results 

We got the value close to the actual one. But we have some problems. Details are written in .ipynb code.

## Future Works

By simulator limitations, we considered only 4 MOs in this simulation. In the future works, we should take all considered MOs into account for more accurate calculations.  
And as written above, this algorithm also focus on reducing noises. It is looking forward to be run on the QC with enough qubits, be evaluated the influence of noises and see the arrival of FTQC era!
