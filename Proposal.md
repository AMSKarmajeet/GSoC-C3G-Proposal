# Google Summer of Code
## Canadian Centre for Computational Genomics


### Project Info

**Project Title:** Improved Tools for Genetic Diversity Modelling

**Project Short Title:** Optimizing Genetic Modelling

**URL of project idea page:**  
[C3G Project Idea List (see "Population genetics simulation and modelling")](https://bitbucket.org/mugqic/gsoc2016/overview)  
[Ryan Gutenkunst's ∂a∂i software](https://bitbucket.org/gutenkunstlab/dadi/)


### Biographical Information

I am an undergraduate at Duke University majoring in computer science and biology. I'm especially interested in the intersection of these two fields, so I am very excited at the possibility of working on a project in bioinformatics this summer. I have taken courses in a number of subjects that will aid me in completing the project this summer, including molecular biology, DNA science, algorithm design, discrete math, differential equations, and linear algebra. I am also fluent in both Python and C++, the two languages that will be used in the project.

In high-school, I participated in the USA Biology Olympiad, a competition that involves over 10,000 students across the country. After multiple rounds involving difficult theoretical questions and practical examinations, I placed first in the nation. I then advanced to the international competition in Bali with 240 students from 60 countries, and earned another gold medal. I also placed first internationally in the smaller University of Toronto Biology Exam. Additionally, I worked in a molecular genetics lab at the NIH one summer, where I studied the genetic basis to the development of the vertebrate vascular system, which involved performing DNA sequence analysis.

In computer science, most of my experience is academic. However, I performed an independent research study in biostatistics last semester, where I analyzed causes of depression, and its effects on performance in American adults. This involved using R to analyze a massive CDC dataset of health evaluations. I used a unique analytic approach, using a structural equation model to set up relationships between different variables, and determine their correlations.

I believe I could be a great asset to this project, and hope to have the chance to contribute to it as I will not only gain experience in a subject I'm passionate about, but will also provide software that will really help the genetics community.


### Contact Information

**Name:** Will Long

**Postal Address:**  
*College Address (Until May 7)*  
302 Gilbert-Addoms  
1368 Campus Drive  
Box 94878  
Durham, NC 27708-4878  

*Home Address (After May 7)*  
1833 Nigel Court  
Vienna, VA 22182

**Phone:** (703) 965-1255 

**Email:** wlong799@gmail.com

**Other Communications:**  
Skype (wlong799@gmail.com)

**Emergency Contact:**  
Diane Long (Mother)
(703) 965-0213
dianeslong@yahoo.com


### Student Affiliation

**Institution:** Duke University

**Program:** Double major in biology and computer science

**Stage of Completion:** 1 Year

**Verification Contact:** I can have an official transcript emailed to you upon request.


### Schedule Conflicts

None.


### Mentors

**Mentor Name:** Dr. Simon Gravel

**Mentor Email:** gravellab@gmail.com

After I finished my selection test, I emailed Dr. Gravel to introduce myself, and quickly explain my background and interest in the project. We then had a discussion over video chat, where he explained the possible projects for this summer, and asked me more about what I might be interested in and able to do. He followed up in an email earlier this week with the project he thought was best suited for me. We discussed the project some more, to make sure I understood the details and what was expected.


### Synopsis

Interpreting genomic data largely relies on simulation software. One important family of software simulates population-level diversity over the course of evolution as a function of selection and demography. The ∂a∂i open-source package, developed by Ryan Gutenkunst (http://gutengroup.mcb.arizona.edu), is the leading software in the field, but is limited when handling large datasets.

This project aims to overhaul the computational engine of the ∂a∂i software by implementing a recently developed approach for solving partial differential equations. The project will use ∂a∂i's interface and code-base, but introduce a new spectrum simulation engine. Using a moment-based approach will improve performance and reduce numerical uncertainty, offering the genetics community with a general-purpose simulation tool that can address larger and more complex datasets than previously possible. 

A prototype version of the computational engine is already running. The goal of this project will be to optimize the engine and embed it efficiently in the existing code-base.


###  Benefits to Community
*(max 250 words)*  
*Don't forget to make your case for a benefit to the organization, not just to yourself.  Why would Google and your organization be proud to sponsor this work? How would open source or society as a whole benefit? What cool things would be demonstrated?*


### Coding Plan & Methods

*Describe in detail your plan for completing the work.  What functions will be written, how and when will you do design, how will you verify the results of your coding?  Each project is different, please make your application appropriate to the work you propose.*  

There are five main parts to this project, listed below in mostly chronological order. Further details on timing can be found in the timeline section below. Step 1 is profiling, which will take place mainly at the beginning of the summer, but also throughout the project to ensure optimizations are being focused on the correct code. The bulk of the project lies in step 2, which is where optimization of code for the new computational engine takes place. Step 3 may be skipped in case an unseen issue comes up, and I run short on time. I need to ensure I leave enough time for step 4, embedding the code in the software, as all the other steps are useless without it. Step 5 is testing, and thus will be performed throughout the summer to ensure things are running correctly.

1. Profile the code to find time wasting functions. In addition to the computationally expensive methods described below, there are a number of essential minor functions that are frequently called. Profiling the code will provide insight into which functions should be focused on to improve performance.
 
2. Refactor the Python engine and port to C++ as necessary to improve performance. Each simulation consists in the integration of a set of linear differential equations. This process can be made more efficient in a variety of ways.
  * For high-dimensional problems, generating the matrices necessary for the linear system can be computationally expensive. This step can be optimized by porting it to C++, or by keeping the matrices in memory for quick reuse in further simulations.  
  * Resolving the set of differential equations is also very expensive. It consists in the resolution of a linear system (Ax = B). A is both sparse and banded, and with a few approximations, it can be written as a pentadiagonal matrix which is an especially useful form for numerical solutions. It may be possible to take advantage of this to code an efficient solver for resolution of pentadiagonal linear systems.
  *Optimize other functions as deemed necessary by the profiling step taken before. This may involve porting to C++ or making the code more efficient.  

3. Improve the optimization algorithm used to compare simulations to data. Once the partial differential equation is solved, it is possible to go from a set of model parameters to a an experimental prediction. The question lies in finding the parameters that best fit the data. Optimizing the code that does this can further improve the performance of the software.

4. Testing the code. This step will be performed throughout the summer to ensure code is working correctly. The ∂a∂i package already provides a number of tests that could be used to quickly check the new code. Furthermore, since we can generally find the solutions already, simply by using the ∂a∂i software that already exists, it will be possible to compare the results from our new version against the old one. It will also be important to track and compare the amount of time it takes the program to complete the calculations, to ensure that the improvements actually worked.


### Timeline

*Provide a detailed timeline of how you plan to spend your summer, organized by deliverables.  Don't leave testing and documentation for last, as that's almost a guarantee of a failed project.*

*What is your contingency plan for things not going to schedule?* 

**Before April 22 (Acceptance Announcements)**

* Install ∂a∂i software onto my computer and all necessary dependencies. Work through the manual and the provided examples to make sure I understand how to use the software and what it does.
* Study the new approach for solving differential equations, to understand how the mathematics work. 

**April 22 - May 21 (Community Bonding)**

* Talk with my mentor and possibly Dr. Gutenkunst to further discuss expectations for the summer project.
* Look through the source code for the prototype of the computational engine. Begin to think more specifically about how I might optimize the engine. Make sure I understand how the engine implements the mathematical algorithm, and what each function does.
*Look at the source code for the original project to see how the new implementation will have to be structured in order to properly interface with the existing code-base.

**May 22 - May 28 (Coding Period Begins)**

*Profiling

**May 29 - June 8**

*Matrix generation optimization (C++ and store in memory)

**June 8 - June 19**

*Linear system resolution optimization, pentadiagonal matrix and C++

**June 20 - June 27 (Midterm Evaluations)**

*Check for other possible functions to improve run time

**June 28 - August 6**

**August 6 - August 14**

**August 15 - August 23 (Final Submission)**

**August 23 - August 29 (Final Evaluations)**

**August 30 (Results)**

**CONTINGENCY PLAN**

### Management of Coding Project

*How do you propose to ensure code is submitted / tested?*

*How often do you plan to commit?  What changes in commit behavior would indicate a problem?*


### Test

*Describe the qualification test that you have submitted to you project mentors.  If feasible, include code, details, output, and example of similar coding problems that you have solved.*

My qualification test was to complete an IPython notebook that dealt with the evolution of allele frequencies in a finite population. The notebook can be found on my [GitHub](https://github.com/wlong799/GSoC-C3G). Completion of this notebook involved the following:

* Learning the basics of genetic simulation programs. The program in the notebook implemented a Wright-Fisher simulation model for studying the evolution of allele frequencies in a simple population. I learned about the parameters necessary for definining populations, various ways one can choose to model evolution, and different ways we can represent this data in Python.
* Practice with BLABLA
