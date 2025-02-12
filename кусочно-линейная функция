import numpy as np
import matplotlib.pyplot as plt

#Алгоритм соединяюший две соседние точки отрезком
def dumb_algorithm(dots_x, dots_y, x):
  i = 0
  result = 0
  n = len(dots_x)
  for i in range(n - 1) :
    if x >= dots_x[i] and x <= dots_x[i + 1]:
      a = (dots_y[i] - dots_y[i + 1]) / (dots_x[i] - dots_x[i + 1])
      b = dots_y[i] - (dots_x[i] * (dots_y[i] - dots_y[i + 1]) / (dots_x[i] - dots_x[i + 1]))
      result = a * x + b
  return result

#Ввод данных точек
dots_x = list(map(int, input().split()))
dots_y = list(map(int, input().split()))

#Сортируем массивы для работы алгоритма
sorted_dots_x = sorted(dots_x)
sorted_dots_y = sorted(dots_y)

x_arr = np.linspace(min(dots_x), max(dots_x), round(max(dots_x) - min(dots_x)) * 100)
y_arr = [dumb_algorithm(sorted_dots_x, sorted_dots_y, x) for x in x_arr]

# График
plt.plot(x_arr, y_arr, label="Dumb interpolation", color="blue")
plt.scatter(dots_x, dots_y, color="red", label="Nodes")
plt.legend()
plt.grid()
plt.show()
