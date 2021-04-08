# single-layer-perceptron(AND gate)
import numpy as np
def activation(x):
    if x >= 0:
        return 1
    else:
        return 0
    
def perceptronModel(input,weight,bias):
    x = np.dot(weight,input) + bias
    y = unitStep(x)
    return y

def AND_logicFunction(input):
    weight = np.array([1, 1])
    bias = -1.5
    return perceptronModel(input, weight, bias)
    
A = np.array([0, 1])
B = np.array([1, 1])
C = np.array([0, 0])
D = np.array([1, 0])

print("AND({}, {}) = {}".format(0, 1, AND_logicFunction(A)))
print("AND({}, {}) = {}".format(1, 1, AND_logicFunction(B)))
print("AND({}, {}) = {}".format(0, 0, AND_logicFunction(C)))
print("AND({}, {}) = {}".format(1, 0, AND_logicFunction(D)))

import matplotlib.pyplot as plt
fig, ax = plt.subplots()
xmin, xmax = -0.2, 1.4
X = np.arange(xmin, xmax, 0.1)
ax.scatter(0, 0, color="r")
ax.scatter(0, 1, color="r")
ax.scatter(1, 0, color="r")
ax.scatter(1, 1, color="g")
ax.set_xlim([xmin, xmax])
ax.set_ylim([-0.1, 1.1])
m, c = -1, 1.2
ax.plot(X, m * X + c )
plt.plot()




