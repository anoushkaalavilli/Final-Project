# Matrix Grapher and Transformer
'''
sources: Alg 2H Textbook, my dad
'''

# The user enters points to form a shape. Then, they select a transformation and the computer graphs the transformed shape and the original shape.

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
  The user can access my program through runpython with a link from GitHub.
* If there are graphics screens involved, describe every screen that the user will experience: what is it for? 
  What did the user have to do to get there and how does she move on to the next?
  There is one pop up screen. The screen will have two shapes. One shape (the pink one) will be the one that the user made and the other shape (the blue one) will be the transformed shape.
* For each graphics screen, describe every active control input and what it does. What elements on the screen will
  change in response to user input?
  The pink shape is dependent on the coordinates the user enters. The blue shape is a transformation of the pink shape. The type of transformation is determined by the user.
* Does the program respond to mouse input? What, exactly, does the mouse do?
The program doesn't respond to user input.
* Does the program respond to keyboard input? How?
The coordinates of the shape are entered using a keyboard by the user as well as the kind of transformation.
* What graphical assets will be used?
The original shape (who's coordinates are entered by the user) and the transformed shape will appear on the screen.
* Does the user have to do anything to install the program?
No.

Your specification should **not** include the following types of information:

* The language you will use to create it.
* Names of any specific files in the project.
* How you will structure the classes, functions and code in your program.
* The name of any files or tools that you will use to design the program.
'''
from ggame import App, Color, LineStyle, Sprite, RectangleAsset, CircleAsset, EllipseAsset, PolygonAsset

npoints = input("How many points would you like in your shape? ")
npoints = int(npoints)

point_matrix = []
firstxpoint = input("Please enter the x coordinate of your first point. Values should be between 10 and 900. ")
firstxpoint = int(firstxpoint)
firstypoint = input("Please enter the y coordinate of your first point. Values should be between 10 and 900. ")
firstypoint = int(firstypoint)
point_matrix.append([firstxpoint, firstypoint])

for i in range(npoints-1):
    pointx = input("Please enter the x coordinate of your next point. Values should be greater than -1000 and less than 1000. ")
    pointx = int(pointx)
    pointy = input("Please enter the y coordinate of your next point. Values should be greater than -1000 and less than 1000. ")
    pointy = int(pointy)
    point_matrix.append([pointx, pointy])
    
transformation = input("What kind of transformation would you like? a) 90 clockwise rotation  b) 90 counter clockwise rotation  c) reflection over y axis  d) reflection over x axis ")

black= Color(0x000000, 1.0)
pink = Color(0xF70960,1.0)
turquoise = Color(0x3CFFCB, 1.0)
noline= LineStyle(0, black)

for i in range(npoints):
    point = RectangleAsset(10, 10, noline, black)
    Sprite(point, (point_matrix[i][0], point_matrix[i][1]))

for i in range(npoints):
    shape1 = PolygonAsset(point_matrix, noline, pink)
    Sprite(shape1)

transformation_matrix_rotate_ccw = [[0,1], [-1, 0]]
transformation_matrix_rotate_cw = [[0,-1], [1,0]]
transformation_matrix_yreflection = [[-1, 0], [0, 1]]
transformation_matrix_xreflection = [[1,0], [0,-1]]

transformedmatrix = []
if transformation == "a":
    for i in range(npoints):
        tx = (transformation_matrix_rotate_cw[0][0]*point_matrix[i][0])+(transformation_matrix_rotate_cw[0][1]*point_matrix[i][1])
        #tx = tx+500
        transformedmatrix.append(tx)
        ty = (transformation_matrix_rotate_cw[1][0]*point_matrix[i][0])+(transformation_matrix_rotate_cw[1][1]*point_matrix[i][1])
        #ty = ty+500
        transformedmatrix.append(ty)
elif transformation == "b":
    for i in range(npoints):
        tx = (transformation_matrix_rotate_ccw[0][0]*point_matrix[i][0])+(transformation_matrix_rotate_ccw[0][1]*point_matrix[i][1])
        #tx = tx+500
        transformedmatrix.append(tx)
        ty = (transformation_matrix_rotate_ccw[1][0]*point_matrix[i][0])+(transformation_matrix_rotate_ccw[1][1]*point_matrix[i][1])
        #ty = ty+500
        transformedmatrix.append(ty)
elif transformation == "c":
    for i in range(npoints):
        tx = (transformation_matrix_yreflection[0][0]*point_matrix[i][0])+(transformation_matrix_yreflection[0][1]*point_matrix[i][1])
        #tx = tx+500
        transformedmatrix.append(tx)
        ty = (transformation_matrix_yreflection[1][0]*point_matrix[i][0])+(transformation_matrix_yreflection[1][1]*point_matrix[i][1])
        #ty = ty+500
        transformedmatrix.append(ty)
elif transformation == "d":
    for i in range(npoints):
        tx = (transformation_matrix_xreflection[0][0]*point_matrix[i][0])+(transformation_matrix_xreflection[0][1]*point_matrix[i][1])
        #tx = tx+500
        transformedmatrix.append(tx)
        ty = (transformation_matrix_xreflection[1][0]*point_matrix[i][0])+(transformation_matrix_xreflection[1][1]*point_matrix[i][1])
        #ty = ty+500
        transformedmatrix.append(ty)


transformedmatrixnumber = len(transformedmatrix)

transformedmatrix1 = []
for i in range(0, transformedmatrixnumber, 2):
    transformedmatrix1.append([transformedmatrix[i], transformedmatrix[i+1]])
    
xnumber = (firstxpoint - transformedmatrix1[0][0])
ynumber = (firstypoint - transformedmatrix1[0][1])

transformedmatrix2 = []
for i in range(0, transformedmatrixnumber, 2):
    transformedmatrix2.append([transformedmatrix[i]+xnumber, transformedmatrix[i+1]+ynumber])

'''
for i in range(npoints*2, 2):
    transformed_point = RectangleAsset(10, 10, noline, black)
    Sprite(transformed_point, (transformedmatrix[i], transformedmatrix[i+1]))
'''

for i in range(npoints):
    shape2 = PolygonAsset(transformedmatrix2, noline, turquoise)
    Sprite(shape2)

myapp = App()
myapp.run()