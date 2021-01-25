"""
Traslation en 2D
Martin Cabrera Arturo Augusto
14/12/2020
"""
import numpy as np
import matplotlib.pyplot as plt
#Número de control L17390347

plt.axis([20,100,20,100])
plt.grid()
plt.title('Taslacion en 2D')

xc=50
yc=50
plt.scatter(xc,yc,s=10,color='k')

#__valores determinados
Rz=7*6
Sx=1/5
sy=7/5

#Dibujar el circulo
radio=5
p1=np.radians(0)
p2=np.radians(360)
dp=np.radians(1)

xlast=radio*np.sin(p1)+xc
ylast=radio*np.cos(p2)+yc

for i in np.arange (p1,p2,dp):
    x=radio*np.sin(i)+xc
    y=radio*np.cos(i)+yc
    plt.plot([xlast,x],[ylast,y],color='r')
    xlast=x
    ylast=y

#Cuadrado que tendrá el circulo adentro
xx1=xc-2*radio
xx2=xx1+4*radio
yy1=yc+radio
yy2=yy1-2*radio

plt.plot([xx1,xx1],[yy1,yy2],color='b')
plt.plot([xx2,xx2],[yy1,yy2],color='b')
plt.plot([xx1,xx2],[yy1,yy1],color='b')
plt.plot([xx1,xx2],[yy2,yy2],color='b')
#Cuadrado que parte del centro
xp1=50
xp2=xp1+4*radio
yp1=50
yp2=yp1-2*radio
plt.plot([xp1,xp1],[yp1,yp2],color='purple')
plt.plot([xp2,xp2],[yp1,yp2],color='purple')
plt.plot([xp1,xp2],[yp1,yp1],color='purple')
plt.plot([xp1,xp2],[yp2,yp2],color='purple')

plt.show()
