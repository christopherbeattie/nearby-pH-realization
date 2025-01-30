# Finding a nearby port-Hamiltonian realization of an LTI system
This MATLAB livescript demonstrates the computation of a port-Hamiltonian realization of a given linear time invariant system.  
If no port-Hamiltonian realization exists, minimal modifications are made to the original system that permits realization as
a port-Hamiltonian system.  

## Calling format:

            [Zhat,sys_out,Resid]=LureLMIsolve(sys_in)

              
**Input:**  sys_in - Standard system realization (A,B,C,D) with    
              A=sys_in.A, B=sys_in.B, C=sys_in.C, and D=sys_in.D  
                 
**Returns:** Zhat - left factor of positive definite solution Q = Zhat*Zhat'   
                to Lure LMI either associated with the given realization  
             (in which case sys_out is "state space equivalent" to sys_in)  
                OR with a nearby realization that is consistent with   
                    solvability of the Lure LMI;  
          sys_out - output system realization that is port-Hamiltonian:  
                       (sys_out.A,sys_out.B,sys_out.C,sys_out.D)  
              either sys_out is equivalent to sys_in or it is nearby and  
              a small perturbation of sys_in allowing for a pH realization   
               
          Resid - the left factor of the final Lure LMI residual:
                 [QA + A'Q  QB-C' ] 
                 [  BQ-C   -(D+D')]  =  - Resid * Resid'
