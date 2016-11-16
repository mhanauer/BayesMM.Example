# BayesMM.Example
# The practitioner will first need to have R and R-Studio installed (please see chapter three of Krusckhe (2014) for details)
# Then practitioner will need to source the two following R programs.  All the practitioner needs to do is copy the 
# the two lines below exactly.
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
# Here the practitioner can create the mean of the evidence.  The evidence for the particiapnt making progress (i.e. success) is
# entered first and the evidence against the student making progress is second.  In this example, the participant has 8 pieces
# of evidence for success and two against.  The kappa.mean just produces the mean of the data which is needed to produce
# the shape parameters.  
kappa.mean = mean(c(rep(1,8), rep(0,2))); kappa.mean
# This is a function to covert the mean and total number of pieces of evidence (i.e. kappa) into A and B shape parameters.
betaABfromMeanKappa( mean=kappa.example, kappa=10)
# This is to open the graph to display the data.
openGraph()
# Here is the program for the informed prior.  There is a prior with shape parameters of 8 and 2 and data with 7 pieces
# of evidence for the participant's success and 3 against the participant's success.
post.informed = BernBeta( priorBetaAB=c(8,2) , Data=c(rep(1,7),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
# This is the same as before but for the informed prior graph below.
openGraph()
# Here is the code for the uninformed prior that can be compared to the infromed prior.  It is uninformed, because the shape
# parameters are small and the same indicaiting that we do not have strong prior knoweledge about the particiapnt.
post.uninformed = BernBeta( priorBetaAB=c(1,1) , Data=c(rep(1,7),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
# BayesMM Example for explaining how Bayes works
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#To get the mean from the prior data
kappa.example = mean(c(rep(1,5), rep(0,5))); kappa.example
#To get the shape values
betaABfromMeanKappa( mean=kappa.example, kappa=10)
#To run the actual analysis
openGraph()
post.informed = BernBeta( priorBetaAB=c(5,5) , Data=c(rep(1,4),rep(0,6)) ,showHDI=TRUE , showCentTend="Mode")
openGraph()
post.uninformed = BernBeta( priorBetaAB=c(1,1) , Data=c(rep(1,6),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
# Calculating the difference in HDI's between informed and uninformed
lower.diff = abs(90.7-41.2); lower.diff  
upper.diff = abs(92.2-56.4); upper.diff
total.diff = lower.diff - upper.diff; total.diff
# This is for the informed prior to demonstrate the it is not a problem 
post.informed = BernBeta( priorBetaAB=c(1,1) , Data=c(rep(1,2),rep(0,8)) ,showHDI=TRUE , showCentTend="Mode")

