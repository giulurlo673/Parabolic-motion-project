from vpython import *
import numpy as np

scene2 = canvas(title='progetto beer-pong', width=1200, height=600, center=vector(0, 0, 0))

N1, N2, N3, N4, N5, N6, g = np.loadtxt('pythonn.txt')

ground = box(pos=vector(150, -4, 0), size=vector(+300, 3, 50), color=color.white)


class Bicchiere:
    bicchiere = cylinder(pos=vector(286, -4, 9), size=vector(11, 8, 8), color=color.green)
    bicchiere.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere2 = cylinder(pos=vector(286, -4, 0), size=vector(11, 8, 8), color=color.green)
    bicchiere2.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere3 = cylinder(pos=vector(286, -4, -9), size=vector(11, 8, 8), color=color.green)
    bicchiere3.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere4 = cylinder(pos=vector(277, -4, -4.5), size=vector(11, 8, 8), color=color.green)
    bicchiere4.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere5 = cylinder(pos=vector(277, -4, 4.5), size=vector(11, 8, 8), color=color.green)
    bicchiere5.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere6 = cylinder(pos=vector(268, -4, 0), size=vector(11, 8, 8), color=color.green)
    bicchiere6.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere = cylinder(pos=vector(286, -4, 9), size=vector(11.1, 7, 7), color=color.black)
    bicchiere.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere2 = cylinder(pos=vector(286, -4, 0), size=vector(11.1, 7, 7), color=color.black)
    bicchiere2.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere3 = cylinder(pos=vector(286, -4, -9), size=vector(11.1, 7, 7), color=color.black)
    bicchiere3.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere4 = cylinder(pos=vector(277, -4, -4.5), size=vector(11.1, 7, 7), color=color.black)
    bicchiere4.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere5 = cylinder(pos=vector(277, -4, 4.5), size=vector(11.1, 7, 7), color=color.black)
    bicchiere5.rotate(axis=vector(0, 0, 1), angle=pi / 2)
    bicchiere6 = cylinder(pos=vector(268, -4, 0), size=vector(11.1, 7, 7), color=color.black)
    bicchiere6.rotate(axis=vector(0, 0, 1), angle=pi / 2)


class box:
    box(pos=vector(5, -45, 21.5),
        size=vector(10, 80, 7),
        color=color.white)
    box(pos=vector(5, -45, -21.5),
        size=vector(10, 80, 7),
        color=color.white)
    box(pos=vector(295, -45, 21.5),
        size=vector(10, 80, 7),
        color=color.white)
    box(pos=vector(295, -45, -21.5),
        size=vector(10, 80, 7),
        color=color.white)
    box(pos=vector(150, -45, 21.5),
        size=vector(10, 80, 7),
        color=color.white)
    box(pos=vector(150, -45, -21.5),
        size=vector(10, 80, 7),
        color=color.white)
    box(pos=vector(150, -8, 21.5),
        size=vector(300, 8, 1),
        color=color.white)
    box(pos=vector(150, -8, -21.5),
        size=vector(300, 8, 1),
        color=color.white)
    box(pos=vector(297, -8, 0),
        size=vector(1, 8, 50),
        color=color.white)
    box(pos=vector(3, -8, 0),
        size=vector(1, 8, 50),
        color=color.white)
    box(pos=vector(150, -8, 0),
        size=vector(1, 8, 50),
        color=color.white)
    box(pos=vector(6, -2, 0),
        size=vector(10, 1, 10),
        color=color.red)


h = 10
R = 1

p1a = sphere(pos=vector(2, R * 2, 0), radius=R, color=color.red)
p1b = sphere(pos=vector(2, R * 2, 0), radius=R, color=color.red)

b1 = sphere(pos=p1a.pos, radius=R * 1.5, make_trail=True)  # caratteristiche e traiettoria della palla
b2 = sphere(pos=p1b.pos, radius=R * 1.5, color=color.cyan, make_trail=True)

g = vector(0, g, 0)
v1 = N1  # v0 palla 1
theta1 = N3 * pi / 180  # theta palla 1
alpha1 = N4 * pi / 180
v2 = N2
alpha2 = N6 * pi / 180
theta2 = N5 * pi / 180

b1.v = v1 * vector(cos(theta1), sin(theta1), sin(alpha1))  # calcolo vx e vy palla 1
b2.v = v2 * vector(cos(theta2), sin(theta2), sin(alpha2))

t = 0
dt = 0.03

t1 = 0
dt1 = 0.03



class Cannone:
    Cannone1 = cylinder(pos=vector(1.5, 1, 0), size=vector(11, 6, 6), color=color.magenta)
    Cannone1.rotate(axis=vector(0, 0, 1), angle=theta1)
    Cannone1a = cylinder(pos=vector(1.6, 1, 0), size=vector(11, 5, 5), color=color.black)
    Cannone1a.rotate(axis=vector(0, 0, 1), angle=theta1)
    Cannone2 = cylinder(pos=vector(1.5, 1, 0), size=vector(11, 6, 6), color=color.cyan)
    Cannone2.rotate(axis=vector(0, 0, 1), angle=theta2)
    Cannone2 = cylinder(pos=vector(1.6, 1, 0), size=vector(11, 5, 5), color=color.black)
    Cannone2.rotate(axis=vector(0, 0, 1), angle=theta2)


while b1.pos.y >= 0:
    rate(100)

    b1.v = b1.v + g * dt
    b2.v = b2.v + g * dt
    if b2.pos.y <= R * 2 and t > .4:
        b2.v = vector(0, 0, 0)
    b1.pos = b1.pos + b1.v * dt
    b2.pos = b2.pos + b2.v * dt
    t = t + dt

while b2.pos.y >= 0:
    rate(100)
    b2.v = b2.v + g * dt1
    b1.v = b1.v + g * dt1
    if b1.pos.y <= R * 2 and t > .4:
        b1.v = vector(0, 0, 0)
    b2.pos = b2.pos + b2.v * dt1
    b1.pos = b1.pos + b1.v * dt1
    t1 = t1 + dt1

print(b1.pos)
print(t)
print(b2.pos)
print(t1)
