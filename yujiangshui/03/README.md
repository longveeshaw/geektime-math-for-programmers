# 03 | 迭代法：不用编程语言的自带函数，你会如何计算平方根？

迭代法，简单来说，其实就是不断地用旧的变量值，递推计算新的变量值。

## 迭代法应用

- 求数值的精确或者近似解。典型的方法包括二分法（Bisection method）和牛顿迭代法（Newton’s method）。
- 在一定范围内查找目标值。典型的方法包括二分查找。
- 机器学习算法中的迭代。相关的算法或者模型有很多，比如 K- 均值算法（K-means clustering）、PageRank 的马尔科夫链（Markov chain）、梯度下降法（Gradient descent）等等。迭代法之所以在机器学习中有广泛的应用，是因为很多时候机器学习的过程，就是根据已知的数据和一定的假设，求一个局部最优解。而迭代法可以帮助学习算法逐步搜索，直至发现这种解。

### 求方程的精确或者近似解

比如利用二分法不断迭代追求一个近似解（注意设置精度来终止）。

### 查找匹配记录

利用二分法将一个有序字典进行对半查找对应单词。注意设置终止条件，比如相近和相同单词。
