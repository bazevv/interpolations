import numpy as np
import matplotlib.pyplot as plt

#Функция для интерполяционного многочлена Лагранжа
def lagrange(dots_x, dots_y, x):
  n = len(dots_x)
  result = 0
  for i in range(n):
    basis_polynom = dots_y[i]
    for j in range(n):
      if j != i:
        basis_polynom *= (x - dots_x[j]) / (dots_x[i] - dots_x[j])
    result += basis_polynom
  return result

#Ввод данных точек
dots_x = list(map(int, input().split()))
dots_y = list(map(int, input().split()))

x_arr = np.linspace(min(dots_x), max(dots_x), round(max(dots_x) - min(dots_x)) * 100)
y_arr = [lagrange(dots_x, dots_y, x) for x in x_arr]


# График
plt.plot(x_arr, y_arr, label="Lagrange Interpolation", color="blue")
plt.scatter(dots_x, dots_y, color="red", label="Nodes")
plt.legend()
plt.grid()
plt.show()
