# Title of Your Project Here

'''
sources:http://stackoverflow.com/questions/4877844/how-would-i-check-a-string-for-a-certain-letter-in-python, http://stackoverflow.com/questions/2294493/how-to-get-the-position-of-a-character-in-python, https://docs.python.org/2/library/re.html, Lee Danilek
'''

# Functional Specification

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

reactant1 = input("Please enter the first reactant of a chemical reaction. Enter subscripts after the element's abrreviation. If there is only one of a certain element, enter the subscript 1 after it. Please limit your reactant to four elements. ")
reactant1 = reactant1.upper()

reactant2 = input("Please enter the second reactant of a chemical reaction. Enter subscripts after the element's abrreviation. If there is only one of a certain element, enter the subscript 1 after it. Please limit your reactant to four elements. ")
reactant2 = reactant2.upper()

product1 = input("Please enter your first product. ")
product1 = product1.upper()

product2 = input("Please enter your second product. ")
product2 = product2.upper()

r = re.search("(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?",reactant1)

l = re.search("(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?",reactant2)

k = re.search("(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?",product1)

g = re.search("(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?(([A-Za-z]+)([0-9]*))?",product2)


#ASSIGNING REACTANT VALUES

assignlist1 = []
assignvalues = [1,2,4,5,7,8,10,11]
for i in (assignvalues):
    assignlist1.append(r.groups()[i])

numbers = [1,3,5,7]
for i in numbers:
    assignlist1[i] = (int(assignlist1[i]))
print (("ASSIGNLIST1="),(assignlist1))

assignlist2 = []
assignvalues = [1,2,4,5,7,8,10,11]
for i in (assignvalues):
    assignlist2.append(l.groups()[i])

for i in numbers:
    assignlist2[i] = (int(assignlist2[i]))
print (("ASSIGNLIST2="),(assignlist2))

reactantvals = []
pos = [0,2,4,6]
for i in pos:
    for j in pos:
        if assignlist1[i] == assignlist2[j]:
            reactantvals.append((assignlist1[i+1]) + (assignlist2[j+1]))
print (("REACTANT VALS="), (reactantvals))


#ASSIGNING PRODUCT VALUES

assignlist1 = []
assignvalues = [1,2,4,5,7,8,10,11]
for i in (assignvalues):
    assignlist1.append(k.groups()[i])

numbers = [1,3,5,7]
for i in numbers:
    assignlist1[i] = (int(assignlist1[i]))
print (("ASSIGNLIST1="),(assignlist1))

assignlist2 = []
assignvalues = [1,2,4,5,7,8,10,11]
for i in (assignvalues):
    assignlist2.append(g.groups()[i])

for i in numbers:
    assignlist2[i] = (int(assignlist2[i]))
print (("ASSIGNLIST2="),(assignlist2))

productvals = []
pos = [0,2,4,6]
for i in pos:
    for j in pos:
        if assignlist1[i] == assignlist2[j]:
            productvals.append((assignlist1[i+1]) + (assignlist2[j+1]))
print (("PRODUCT VALS="), (productvals))


#CHECK IF PRODUCTS AND REACTANTS ARE EQUAL

dictionary = {'a':30, 'd':20, 'b':40}
dctionary.sorted()
print (dictionary)

    
   
  




#products = input("Please enter the products of a chemical reaction. Choose a chemical reaction with only two reactants. Choose a chemical reaction with only two reactants. Select reactions containing the elements carbon, hydrogen, nitrogen, oxygen, chlorine, and sulfur.")

'''
if int in reactant1:
    subscriptposition = (reactant1.index(int))
    elementposition = ((subscriptposition) - 1)
    elementsinreactants.append(reactant1[elementposition])
    print (elementsinreactants)
'''