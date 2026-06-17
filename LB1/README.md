
---

# Итоговый отчёт по ЛР-01: Линейное программирование

## Кейс 1: Муниципальная пекарня (`civil_01`)

### Задание 1. Геометрическое решение

* **Математическая модель:** $\max z = 7x_1 + 5x_2$ при $4x_1 + 2x_2 \le 40$ и $x_1 + 2x_2 \le 22$.
* **Вершины:** Оптимум в $(6, 8)$, где $z = 82$.

### Задание 2. Проверка через `linprog`

```python
import numpy as np
from scipy.optimize import linprog
c = np.array([-7, -5])
A_ub = np.array([[4, 2], [1, 2]])
b_ub = np.array([40, 22])
res = linprog(c, A_ub=A_ub, b_ub=b_ub, bounds=[(0, None), (0, None)], method='highs')
print(f"Оптимальный план пекарни: x1={res.x[0]:.2f}, x2={res.x[1]:.2f}, Max Profit={-res.fun:.2f}")

```

---

## Кейс 2: Городской ремонтный участок (`civil_02`)

### Задание 1. Геометрическое решение

* **Математическая модель:** $\max z = 8x_1 + 7x_2$ при $3x_1 + 2x_2 \le 24$ и $2x_1 + 3x_2 \le 30$.
* **Вершины:** Оптимум в $(2.4, 8.4)$, где $z = 78$.

### Задание 2. Проверка через `linprog`

```python
c = np.array([-8, -7])
A_ub = np.array([[3, 2], [2, 3]])
b_ub = np.array([24, 30])
res = linprog(c, A_ub=A_ub, b_ub=b_ub, bounds=[(0, None), (0, None)], method='highs')
print(f"Оптимальный план ремонта: x1={res.x[0]:.2f}, x2={res.x[1]:.2f}, Max Z={-res.fun:.2f}")

```

---

## Кейс 3: Полевые рационы (`military_01`)

### Задание 1. Геометрическое решение

* **Математическая модель:** $\max z = 10x_1 + 7x_2$ при $3x_1 + x_2 \le 21$ и $x_1 + 2x_2 \le 14$.
* **Вершины:** Оптимум в $(5.6, 4.2)$, где $z = 85.4$.

### Задание 2. Проверка через `linprog`

```python
c = np.array([-10, -7])
A_ub = np.array([[3, 1], [1, 2]])
b_ub = np.array([21, 14])
res = linprog(c, A_ub=A_ub, b_ub=b_ub, bounds=[(0, None), (0, None)], method='highs')
print(f"Оптимальный план рационов: x1={res.x[0]:.2f}, x2={res.x[1]:.2f}, Max Value={-res.fun:.2f}")

```

---

## Кейс 4: Ремонтно-обслуживающий склад (`military_02`)

### Задание 1. Геометрическое решение

* **Математическая модель:** $\max z = 11x_1 + 8x_2$ при $2x_1 + 3x_2 \le 24$ и $3x_1 + x_2 \le 21$.
* **Вершины:** Оптимум в $(3.9, 5.4)$, где $z = 86.1$.

### Задание 2. Проверка через `linprog`

```python
c = np.array([-11, -8])
A_ub = np.array([[2, 3], [3, 1]])
b_ub = np.array([24, 21])
res = linprog(c, A_ub=A_ub, b_ub=b_ub, bounds=[(0, None), (0, None)], method='highs')
print(f"Оптимальный план склада: x1={res.x[0]:.2f}, x2={res.x[1]:.2f}, Max Z={-res.fun:.2f}")

```


