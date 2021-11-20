# from turtle import *
from random import randint

#how to add background color
import turtle
wn=turtle.Screen()
wn.bgcolor("purple")

#Creating the finish line.
finish = turtle.Turtle()
finish.up()	#Allowing to move the finish line to a certain location.
finish.speed(0)
finish.goto(160, 140) #Moving the finish line to the correct position.
finish.down()
finish.right(90)
finish.width(5)

#Drawing the finish line.
for i in range(17):
	finish.color("blue")
	finish.forward(5)
	finish.color("red")
	finish.forward(5)

#Creating the text to say "Finish line"
finish_text = turtle.Turtle()
finish_text.up()
finish_text.speed(10)
finish_text.color("White")
finish_text.goto(110, 150)
finish_text.write("Finish Line", font = ("Times New Roman",12, "bold"))

#Creating another turtle for the starting line.
start = turtle.Turtle()
start.up()
start.speed(0)
start.goto(-140, 140)
start.width(5)
start.right(90)
start.down()

#Drawing the starting line.
for i in range(17):
	start.color("green")
	start.forward(5)
	start.color("yellow")
	start.forward(5)

#Creating the text to say "starting line"
start_text = turtle.Turtle()
start_text.up()
start_text.speed(10)
start_text.color("white")
start_text.goto(-160, 150)
start_text.write("Starting Line", font = ("Times New Roman",12, "bold"))

#print the track markers
speed(10)
penup()
goto(-140,140)

for step in range(15):
  right(90)
  for num in range(8):
    penup()
    forward(10)
    pendown()
    color("white")
    forward(10)
  penup()
  backward(160)
  left(90)
  forward(20)

#This is actually moving the text to its correct location and writing it so that people can see it.
first_text = turtle.Turtle()
first_text.speed(10)
first_text.up()
first_text.color("yellow")
first_text.goto(-180, -60)
first_text.write("GET TO YOUR STARTING POSITIONS!!!!!", font = ("Times New Roman", 14, "normal"))
first_text.down()
  
#Creating the turtles for the race and their colours.
ada = Turtle()
ada.color('red')
ada.shape('turtle')

aaron = Turtle()
aaron.color('yellow')
aaron.shape('turtle')


aiden = Turtle()
aiden.color('blue')
aiden.shape('turtle')

addy = Turtle()
addy.color('orange')
addy.shape('turtle')

#move to starting line
ada.penup()
ada.goto(-160,100)

for turn in range(10):
  ada.right(36)

aaron.penup()
aaron.goto(-160,80)

for turn in range(18):
  aaron.left(20)

aiden.penup()
aiden.goto(-160,40)

for turn in range(18):
  aiden.left(20)

addy.penup()
addy.goto(-160,20)

for turn in range(4):
  addy.left(90)
  
#Removing the old text and creating space for the new text.
first_text.clear()

#Racelight Countdown 
#Creating the first red circle as a turtle.
red_circle_1 = turtle.Turtle()
red_circle_1.speed(1)
red_circle_1.up()
red_circle_1.goto(0, 120)
red_circle_1.color("red")
red_circle_1.shape("circle")


#Creating the second red circle indicating starting is about to begin.
red_circle_2 = turtle.Turtle()
red_circle_2.speed(1)
red_circle_2.up()
red_circle_2.goto(0, 90)
red_circle_2.color("red")
red_circle_2.shape("circle")

#Creating the third red circle indicating starting is about to begin.
red_circle_3 = turtle.Turtle()
red_circle_3.speed(1)
red_circle_3.up()
red_circle_3.goto(0, 60)
red_circle_3.color("red")
red_circle_3.shape("circle")

#Creating the first green circle indicating starting is about to begin.
green_circle_1 = turtle.Turtle()
green_circle_1.speed(1)
green_circle_1.up()
green_circle_1.goto(0, 0)
green_circle_1.color("green")
green_circle_1.shape("circle")
green_circle_1.pensize(100)

red_circle_1.ht()
red_circle_2.ht()
red_circle_3.ht()
green_circle_1.ht()

#the actual race!
for turn in range(100):
  ada.forward(randint(1,6))
  aaron.forward(randint(1,6))
  aiden.forward(randint(1,6))
  aiden.forward(randint(1,6))
  addy.forward(randint(1,6))
  if ada.xcor() >= 150:
			ada.goto(-180, -80)
			ada.write("   AVA WINS CANDY FOR LIFE!!!!!", font = ("Times New Roman", 14, "normal"))
			#This tells white turtle to move to a position if they win (cross a certain x position that is equivalent to the x position of the finish line).
			break
			#This will stop the loop (and thus the turtles moving) regardless of if they have finished the range set earlier.
  if aaron.xcor() >= 150:
			aaron.goto(-180, -80)
			aaron.write("   COFFEECHUG WINS COFFEE FOR LIFE!!!!!", font = ("Times New Roman", 14, "normal"))
      #This tells white turtle to move to a position if they win (cross a certain x position that is equivalent to the x position of the finish line).
			break
			#This will stop the loop (and thus the turtles moving) regardless of if they have finished the range set earlier.
  if aiden.xcor() >= 150:
			aiden.goto(-180, -80)
			aiden.write("   AIDEN WINS XBOX GOLD FOR LIFE!!!!!", font = ("Times New Roman", 14, "normal"))
      #This tells white turtle to move to a position if they win (cross a certain x position that is equivalent to the x position of the finish line).
			break
			#This will stop the loop (and thus the turtles moving) regardless of if they have finished the range set earlier.
  if addy.xcor() >= 150:
			aiden.goto(-180, -80)
			aiden.write("   ADDY WINS WARRIOR TICKETS FOR LIFE!!!!!", font = ("Times New Roman", 14, "normal"))
      #This tells white turtle to move to a position if they win (cross a certain x position that is equivalent to the x position of the finish line).
			break
			#This will stop the loop (and thus the turtles moving) regardless of if they have finished the range set earlier.


import mysql.connector
mydb=mysql.connector.connect(host='localhost',username='root',\
password='Mani.@12')
mycursor=mydb.cursor()
mycursor.execute("CREATE DATABASE k20ud") 

mydb=mysql.connector.connect(host='localhost',username='root',\
password='Mani.@12',\
database='k20ud')
mycursor=mydb.cursor()
mycursor.execute("CREATE TABLE Players(id int AUTO_INCREMENT PRIMARY KEY,\
p_name VARCHAR(50), t_color VARCHAR(100))")

mycursor=mydb.cursor()
query="INSERT INTO Players(p_name,t_color) VALUES(%s,%s)"
data=[
    ('ada','red'),
    ('aaron','yellow'),
    ('aiden','blue'),
    ('addy','orange')
]

mycursor.executemany(query,data)
mydb.commit()


