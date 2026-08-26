# press-and-play-
from turtle import *
from time import sleep
from random import randint

w = 200
h = 200

t1 = Turtle()
t1.color('red')
t1.width(5)
t1.shape("turtle")

t2 = Turtle()
t2.color('blue')
t2.width(5)
t2.shape("turtle")
t2.left(240)

t3 = Turtle()
t3.color('green')
t3.width(5)
t3.shape("turtle")
t3.left(120)

def catch1(x,y):
    t1.penup()
    t1.goto(randint(-100,100), randint(-100,100))
    t1.pendown()
    t1.left(randint(0,180))

t1.onclick(catch1)

def catch2(x,y):
    t2.penup()
    t2.goto(randint(-100,100), randint(-100,100))
    t2.pendown()
    t2.left(randint(0,180))

t2.onclick(catch2)

def catch3(x,y):
    t3.penup()
    t3.goto(randint(-100,100), randint(-100,100))
    t3.pendown()
    t3.left(randint(0,180))

t3.onclick(catch3)

def gameFinished(t1, t2, t3):
    t1_outside = abs(t1.xcor()) > w or abs(t1.ycor()) > h
    t2_outside = abs(t2.xcor()) > w or abs(t2.ycor()) > h
    t3_outside = abs(t3.xcor()) > w or abs(t3.ycor()) > h
    isOutside = t1_outside or t2_outside or t3_outside
    return isOutside

t1.onclick(catch1)
t2.onclick(catch2)
t3.onclick(catch3)

while gameFinished(t1, t2, t3) != True:
    t1.forward(7)
    t2.forward(7)
    t3.forward(7)
    sleep(0.1)


t1.clear()
t2.clear()
t3.clear()

t1.write('Game over!', font=('Arial',16, 'bold'))
t1.hideturtle()
t2.write('Game over!', font=('Arial',16, 'bold'))
t2.hideturtle()
t3.write('Game over!', font=('Arial',16, 'bold'))
t3.hideturtle()

exitonclick()
