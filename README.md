# Лабораторная работа №1: Анализ устойчивости стационарных точек и бифуркации Хопфа

## Цель работы
Провести линейный анализ устойчивости стационарных точек для двумерной системы обыкновенных дифференциальных нелинейных уравнений. Определить значения управляющих параметров, при которых происходит бифуркация Хопфа, построить фазовые портреты до и после бифуркации. Найти мультипликаторы Флоке для численного анализа устойчивости предельного цикла.

## Задание
Рассмотрим систему дифференциальных уравнений:

\[
\frac{dx}{dt} = ax - by - x(x^2 + y^2),
\]
\[
\frac{dy}{dt} = bx + ay - y(x^2 + y^2).
\]

## Решение

### 1. Нахождение стационарных точек
Стационарные точки находятся из условий:

\[
ax - by - x(x^2 + y^2) = 0,
\]
\[
bx + ay - y(x^2 + y^2) = 0.
\]

Рассмотрим случай \( x = 0 \):

Подставляем \( x = 0 \) в первое уравнение:

\[
a \cdot 0 - b y - 0 \cdot (0 + y^2) = -b y = 0 \Rightarrow y = 0.
\]

Таким образом, стационарная точка \( (0, 0) \).

Теперь рассмотрим случай \( x \neq 0 \). Перепишем уравнения:

\[
ax - by = x(x^2 + y^2),
\]
\[
bx + ay = y(x^2 + y^2).
\]

Разделим первое уравнение на \( x \), а второе на \( y \):

\[
a - b \frac{y}{x} = x^2 + y^2,
\]
\[
b \frac{x}{y} + a = x^2 + y^2.
\]

Теперь вычтем первое уравнение из второго:

\[
b \frac{x}{y} + a - (a - b \frac{y}{x}) = 0 \Rightarrow b \frac{x}{y} + b \frac{y}{x} = 0.
\]

Упростим:

\[
b \left( \frac{x}{y} + \frac{y}{x} \right) = 0 \Rightarrow b \left( \frac{x^2 + y^2}{xy} \right) = 0.
\]

Поскольку \( x \neq 0 \) и \( y \neq 0 \), то \( x^2 + y^2 \neq 0 \), следовательно, \( b = 0 \).

Если \( b = 0 \), то система упрощается:

\[
ax = x(x^2 + y^2),
\]
\[
ay = y(x^2 + y^2).
\]

Если \( x \neq 0 \) и \( y \neq 0 \), то:

\[
a = x^2 + y^2.
\]

Таким образом, стационарные точки лежат на окружности радиуса \( \sqrt{a} \) в плоскости \( (x, y) \).

### 2. Вычисление матрицы Якоби
Матрица Якоби для системы:

\[
J = \begin{pmatrix}
\frac{\partial f}{\partial x} & \frac{\partial f}{\partial y} \\
\frac{\partial g}{\partial x} & \frac{\partial g}{\partial y}
\end{pmatrix},
\]

где

\[
f(x, y) = ax - by - x(x^2 + y^2),
\]
\[
g(x, y) = bx + ay - y(x^2 + y^2).
\]

Вычислим частные производные:

\[
\frac{\partial f}{\partial x} = a - (x^2 + y^2) - 2x^2,
\]
\[
\frac{\partial f}{\partial y} = -b - 2xy,
\]
\[
\frac{\partial g}{\partial x} = b - 2xy,
\]
\[
\frac{\partial g}{\partial y} = a - (x^2 + y^2) - 2y^2.
\]

Таким образом, матрица Якоби:

\[
J = \begin{pmatrix}
a - 3x^2 - y^2 & -b - 2xy \\
b - 2xy & a - x^2 - 3y^2
\end{pmatrix}.
\]

### 3. Оценка матрицы Якоби в стационарной точке \( (0, 0) \)
Подставим \( x = 0 \) и \( y = 0 \) в матрицу Якоби:

\[
J(0, 0) = \begin{pmatrix}
a & -b \\
b & a
\end{pmatrix}.
\]

### 4. Вычисление следа и определителя матрицы Якоби
След матрицы Якоби:

\[
\text{Tr}(J) = a + a = 2a.
\]

Определитель матрицы Якоби:

\[
\det(J) = a \cdot a - (-b) \cdot b = a^2 + b^2.
\]

### 5. Проверка условий для бифуркации Хопфа
Для бифуркации Хопфа должны выполняться следующие условия:

1. След матрицы Якоби равен нулю: \( \text{Tr}(J) = 0 \).
2. Определитель матрицы Якоби положителен: \( \det(J) > 0 \).

Из условия \( \text{Tr}(J) = 0 \):

\[
2a = 0 \Rightarrow a = 0.
\]

При \( a = 0 \), определитель:

\[
\det(J) = 0^2 + b^2 = b^2 > 0.
\]

Таким образом, бифуркация Хопфа происходит при \( a = 0 \) и \( b \neq 0 \).

### 6. Определение параметра бифуркации
Параметром бифуркации является \( a \). При \( a = 0 \) система переходит от устойчивой стационарной точки к предельному циклу.

### 7. Фазовые портреты и временные ряды
Фазовые портреты и временные ряды системы до и после бифуркации Хопфа могут быть построены численно. При \( a < 0 \) стационарная точка \( (0, 0) \) устойчива, а при \( a > 0 \) появляется устойчивый предельный цикл.

### 8. Численный анализ устойчивости предельного цикла
Для численного анализа устойчивости предельного цикла можно использовать метод Флоке. Вычисление мультипликаторов Флоке позволяет определить устойчивость предельного цикла. Если все мультипликаторы, кроме одного, лежат внутри единичного круга, то цикл устойчив.

### Графики

#### Фазовые портреты

1. **До бифуркации (\( a < 0 \)):**
   - Стационарная точка \( (0, 0) \) устойчива.
   - Фазовый портрет показывает, что все траектории стремятся к точке \( (0, 0) \).

2. **После бифуркации (\( a > 0 \)):**
   - Появляется устойчивый предельный цикл.
   - Фазовый портрет показывает, что траектории стремятся к предельному циклу.

#### Временные ряды

1. **До бифуркации (\( a < 0 \)):**
   - \( x(t) \) и \( y(t) \) стремятся к нулю.

2. **После бифуркации (\( a > 0 \)):**
   - \( x(t) \) и \( y(t) \) осциллируют с постоянной амплитудой, соответствующей предельному циклу.

### Пример выполнения

Для численного построения графиков можно использовать Python с библиотеками `numpy` и `matplotlib`. Вот пример кода:

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import odeint

# Параметры системы
a = 1.0
b = 1.0

# Система дифференциальных уравнений
def system(state, t):
    x, y = state
    dxdt = a * x - b * y - x * (x**2 + y**2)
    dydt = b * x + a * y - y * (x**2 + y**2)
    return [dxdt, dydt]

# Временной интервал
t = np.linspace(0, 20, 1000)

# Начальные условия
initial_conditions = [1.0, 1.0]

# Решение системы
solution = odeint(system, initial_conditions, t)

# Построение фазового портрета
plt.figure()
plt.plot(solution[:, 0], solution[:, 1])
plt.xlabel('x')
plt.ylabel('y')
plt.title('Фазовый портрет после бифуркации Хопфа')
plt.grid()
plt.show()

# Построение временных рядов
plt.figure()
plt.plot(t, solution[:, 0], label='x(t)')
plt.plot(t, solution[:, 1], label='y(t)')
plt.xlabel('Время')
plt.ylabel('Значения')
plt.title('Временные ряды после бифуркации Хопфа')
plt.legend()
plt.grid()
plt.show()
