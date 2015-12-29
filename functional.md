# Title of Your Project Here

'''
sources:http://stackoverflow.com/questions/4877844/how-would-i-check-a-string-for-a-certain-letter-in-python, http://stackoverflow.com/questions/2294493/how-to-get-the-position-of-a-character-in-python, https://docs.python.org/2/library/re.html, Lee Danilek
'''

## Functional Specification

'''
This document should become the functional specification of the project you are working on.

A functional specification describes in great detail how a device or program will appear to an
outside user. That is, it treats all hardware as a "black box", the contents of which are completely
unknown to the user. The functional specification should include sections with the following information:

Your specification **should include** the following types of information:

* A title. Replace the title at the beginning of this document.
* Summary or introduction. In general, in a few lines or less, what is your program about or what is it about?
* How does the user access your program? Is it shared via http://runpython.com? Is a web site? Embedded in 
  a single board computer? 
* If there are graphics screens involved, describe every screen that the user will experience: what is it for? 
  What did the user have to do to get there and how does she move on to the next?
* For each graphics screen, describe every active control input and what it does. What elements on the screen will
  change in response to user input?
* Does the program respond to mouse input? What, exactly, does the mouse do?
* Does the program respond to keyboard input? How?
* What graphical assets will be used?
* Does the user have to do anything to install the program?

Your specification should **not** include the following types of information:

* The language you will use to create it.
* Names of any specific files in the project.
* How you will structure the classes, functions and code in your program.
* The name of any files or tools that you will use to design the program.
'''

import re

reactant1 = input("Please enter the reactants of a chemical reaction. Enter subscripts after the element's abrreviation. ")
reactant1 = reactant1.upper()

r = re.search("(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?",reactant1)
print(r.groups())

elementsinreactants = []
elementsinreactants.append(r.groups())
print (elementsinreactants)

print (("elementsinreactants = "), (elementsinreactants))
print (r.group(0))

#products = input("Please enter the products of a chemical reaction. Choose a chemical reaction with only two reactants. Choose a chemical reaction with only two reactants. Select reactions containing the elements carbon, hydrogen, nitrogen, oxygen, chlorine, and sulfur.")

'''
if "2" in reactant1:
    subscriptposition = (reactant1.index("2"))
    elementposition = ((subscriptposition) - 1)
    elementsinreactants.append(reactant1[elementposition])
    print (elementsinreactants)
    
if "3" in reactant1:
    subscriptposition = (reactant1.index("3"))
    elementposition = ((subscriptposition) - 1)
    elementsinreactants.append(reactant1[elementposition])
    print (elementsinreactants)
  
if int in reactant1:
    subscriptposition = (reactant1.index(int))
    elementposition = ((subscriptposition) - 1)
    elementsinreactants.append(reactant1[elementposition])
    print (elementsinreactants)

if "C" in reactant1:
    elementsinreactants.append("carbon")

if "H" in reactant1:
    elementsinreactants.append("hydrogen")
    
if "O" in reactant1:
    elementsinreactants.append("oxygen")
    
if "N" in reactant1:
    elementsinreactants.append("nitrogen")
'''

    
    
    
    
    
    
    
    
#regex
    
    
# find a way to make the subscript 23 not be mistaken for subscript 2, also, make 2subscript program for all numbers
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    


