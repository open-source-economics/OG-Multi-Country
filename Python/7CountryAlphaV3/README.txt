This is the current work on the code. Because of the addition of
skill classes, the solution algorithm had to be completely changed. To
verify the algebra, I also included a few Mathematica files.

Data_Files: This folder contains the data files from Kotlikoff's research.
            They include the fertility and mortality rates for each country 
            over time. Net migration and population are included as well.

Graphs: Folder contains the graphical outputs of the code for future
        reference.

AuxiliaryClass.py--This file handles the python class that we use for
                   the model. We use a python class to make it easy to
                   store and reuse all of the various pieces of the 
                   model.

AuxiliaryDemographics.py--In order to keep AuxiliaryClass decluttered,
                          we decided to take functions that didn't store
                          any varibles into the object and put them in
                          this file.

HyperbolicCalc.nb-- Verifies the correctness of the equations used in the
                    code, particularly the equations for Elliptical Utility.


Main.py- The central file where the user can change their inputs. By running
         this script, the whole model will run.

oldHHsolver.py-- Before we transitioned to vectorized code, we used this
                 solving method. It's available as a solution method if 
                 the user wants to use it. We kept it as a seperate file
                 for the same reason that AuxiliaryDemographics is seperate.

pure_cython_setup_distutils.py-- Set-up file for the pure_cython module.
                                 Cython runs faster than python and this module
                                 speeds up the most time intensive parts of the 
                                 code.

pure_cython.c-- Wrapped code generated by distutils.

pure_cython.pyx-- The cython version of the time intensive code, which consists
                  of filling the consumption and assets matrix for each country.

pure_cython.so-- The object that is callable from python.

RobustChecker.py- MPI script that tests the model. It goes through different
                  combinations of numbers of countries, number of cohorts
                  and sigma levels. It outputs .CSV files that will indicate
                  if that particular combination converged.

Stage5AlgCheck.nb-- Verifies the algebra of the other aspects of the code.

