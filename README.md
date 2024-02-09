[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

---

# 1)

$T(n) = T(n/13) + 5$

$T(n/13) = (T(n/13/13) + 5) + 5 =$

$T(n/169) + 10$

$T(n/2197) + 15$

$T(n/13^{i}) +5i$ for $i = \log_{13}n$

$T(n/13^{\log_{13}n}) + 5\log_{13}n = T(1) + 5 \log_{13}n$

Ignoring constants and lower terms leaves us with

$\theta(\log n)$

# 2)

$T(n) = 13 \cdot T(n/13) + 5$

$T(n/13) = 13(13 \cdot T(n/13/13)) + 5 + 5 =$

$169 \cdot T(n/169) + 10$

$2197 \cdot T(n/2197) + 15$

$13^{i} \cdot T(n/13^{i}) + 5i$ for $i = \log_{13}n$

$13^{\log_{13}n} \cdot T(n/13^{\log_{13}n}) + 5 \log_{13}n$

$n \cdot T(1) + 5 \log_{13}n$

Ignoring constants and lower terms leaves us with

$\theta(n)$

# 3)

$T(n) = 13 \cdot T(n/13) +2n$

$T(n/13) = 13(13 \cdot T(n/13) +2n/13) + 2n =$

$169 \cdot T(n/169) + 28n/13$

$13(169 \cdot T(n/169) + 28n/13/13) + 2n =$

$2197 \cdot T(n/2197) + 366n/169$

$13^{i} \cdot T(n/13^{i}) + 2ni$ for $i = \log_{13}n$

$13^{\log_{13}n} \cdot T(n/13^{\log_{13}n}) + 2n\log_{13}n$

$n \cdot T(1) + 2n \log_{13}n$

$n + 2n \log_{13}n$

Ignoring constants and lower terms leaves us with

$\theta(n\log n)$
