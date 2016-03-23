# Google Summer of Code
## Canadian Centre for Computational Genomics


### Project Info

**Project Title** Improved Tools for Genetic Diversity Modelling

**Project Short Title:** Genetic Modelling Optimization

**URL of project idea page:**  
[C3G Project Idea List](https://bitbucket.org/mugqic/gsoc2016/overview) (Project listed as "Population genetics simulation and modelling")  
[Bitbucket for current ∂a∂i software](https://bitbucket.org/gutenkunstlab/dadi/)


### Biographical Information

INSERT (BRIEF) BIOGRAPHY HERE

HIT ON BIOLOGY/GENETIC PAST

MOVE ON TO COMPUTER SCIENCE/MATH AND WHY I'M INTERESTED


### Contact Information

**Name:** Will Long

**Melange Link_id:** What is this?

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


### Student Affiliation

**Institution:** Duke University

**Program:** Pursuing a double major in biology and computer science.

**Stage of Completion:** One Year

**Verification Contact:** I can have an official transcript emailed to you upon request.


### Schedule Conflicts

None


### Mentors

**Mentor Name:** Dr. Simon Gravel

**Mentor Emails:** gravellab@gmail.com

**Mentor link_ids:** What is this?

*Have you been in touch with the mentors? When and how?*

Dr. Gravel and I emailed back and forth a few times when I first expressed interest in the project. We had a discussion over video chat about the different projects he was considering working on, my background and interests, and what I might want to do this summer. He then followed up in an email with the project he thought best suited to my abilities and interests, and I asked him for a few clarifications.


### Synopsis
*(max 150 words)*  
*Start your proposal with a short summary of the project, designed to convince the reviewer to read the rest of the proposal.*

The interpretation of genomic data largely relies on simulation software. One important family of software simulates population-level diversity over the course of evolution as a function of selection and demography. The ∂a∂i open source package, developed by Ryan Gutenkunst [http://gutengroup.mcb.arizona.edu] is the leading software in the field, but it suffers from limitations when handling large datasets.

This project aims to overhaul the computational engine of the ∂a∂i software by implementing a recently developed approach for the solution of partial differential equations.  This project will use ∂a∂i's interface and code-base but introduce a new spectrum simulation engine. Using a moment-based approach will provide improved performance and reduced numerical uncertainty compared to ∂a∂i, offering the genetics community with a general-purpose simulation tool that can address larger and more complex datasets than previously possible. 

A prototype version of the computational engine is already running. The goal of this project will be to optimize the engine and embed it efficiently in the existing code-base. 


###  Benefits to Community
*(max 250 words)*  
*Don't forget to make your case for a benefit to the organization, not just to yourself.  Why would Google and your organization be proud to sponsor this work? How would open source or society as a whole benefit? What cool things would be demonstrated?*


### Coding Plan & Methods

*Describe in detail your plan for completing the work.  What functions will be written, how and when will you do design, how will you verify the results of your coding?  Each project is different, please make your application appropriate to the work you propose.*  

*Describe perceived obstacles and challenges, and how you plan to overcome them.*


### Timeline

*(consult GSOC schedule)*

*Provide a detailed timeline of how you plan to spend your summer, organized by deliverables.  Don't leave testing and documentation for last, as that's almost a guarantee of a failed project.*

*What is your contingency plan for things not going to schedule?* 


### Management of Coding Project

*How do you propose to ensure code is submitted / tested?*

*How often do you plan to commit?  What changes in commit behavior would indicate a problem?*


### Test

*Describe the qualification test that you have submitted to you project mentors.  If feasible, include code, details, output, and example of similar coding problems that you have solved.*


### Anything Else
