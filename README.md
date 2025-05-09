# ZARK1
import os
import numpy as np
import matplotlib.pyplot as plt

def f(x):
  return -20 * np.exp(-0.2 * (0.5 * x**2)**0.5) - np.exp(0.5 * (np.cos(2 * np.pi * x) + 1)) + np.e + 20

x = np.linspace(-5, 5, 200)  
y = f(x)

if os.path.exists("results")==False:
  os.mkdir("results")

with open("results/data.txt", "w") as file:
  for i in range(len(x)):
    file.write(f"{x[i]:.4f}    {y[i]:.4f}\n") 
print("данные сохранены в файл data.txt")


plt.plot(x, y)
plt.xlabel("x")
plt.ylabel("f(x)")
plt.title("График функции f(x) = -20*e**(-0.2*(0.5*x*x)**0.5)-e**(0.5*(cos(2*pi*x)+1))+e+20")
plt.grid(True)
plt.show()

