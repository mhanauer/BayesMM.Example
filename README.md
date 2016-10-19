# BayesMM.Example
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#To get the mean from the prior data
kappa.example = mean(c(rep(1,8), rep(0,3))); kappa.example
#To get the shape values
betaABfromMeanKappa( mean=kappa.example, kappa=11)
#To run the actual analysis
openGraph()
post.informed = BernBeta( priorBetaAB=c(8,3) , Data=c(rep(1,6),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
openGraph()
post.uninformed = BernBeta( priorBetaAB=c(1,1) , Data=c(rep(1,6),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
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
#Calculating the difference in HDI's between informed and uninformed
lower.diff = abs(52.1-41.2); lower.diff  
upper.diff = abs(89.7-90.7); upper.diff
total.diff = lower.diff + upper.diff; total.diff
