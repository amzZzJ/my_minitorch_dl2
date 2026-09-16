# minitorch
The full minitorch student suite. 


To access the autograder: 

* Module 0: https://classroom.github.com/a/qDYKZff9
* Module 1: https://classroom.github.com/a/6TiImUiy
* Module 2: https://classroom.github.com/a/0ZHJeTA0
* Module 3: https://classroom.github.com/a/U5CMJec1
* Module 4: https://classroom.github.com/a/04QA6HZK
* Quizzes: https://classroom.github.com/a/bGcGc12k

## Task 1.5

```text
Simple: Epoch 500  loss 0.4755  correct 50/50
Diag:   Epoch 500  loss 0.6893  correct 50/50
Split:  Epoch 500  loss 2.5240  correct 50/50
Xor:    Epoch 500  loss 2.7498  correct 50/50
```

## Task 2.5

```text
Simple: Epoch 500  loss 2.2712  correct 49/50  time 0.0215 s/epoch
Diag:   Epoch 500  loss 0.4960  correct 50/50  time 0.0452 s/epoch
Split:  Epoch 500  loss 0.3224  correct 50/50  time 0.1746 s/epoch
Xor:    Epoch 500  loss 5.8454  correct 47/50  time 0.1744 s/epoch
```

## Task 3.1 and 3.2 diagnostics

`python project/parallel_check.py` reports:

```text
tensor_map: loop #0 is parallel; parallel structure is already optimal.
tensor_zip: loop #1 is parallel; parallel structure is already optimal.
tensor_reduce: loop #2 is parallel; parallel structure is already optimal.
_tensor_matrix_multiply: loop #3 is parallel; parallel structure is already optimal.
```

Allocation hoisting is reported for the index buffers in map, zip and reduce.

## Task 3.5

```text
Simple: Epoch 480  loss 0.0078  correct 50/50  time 0.046 s/epoch
Diag:   Epoch 240  loss 0.0055  correct 50/50  time 0.057 s/epoch
Split:  Epoch 399  loss 0.0007  correct 50/50  time 0.050 s/epoch
Xor:    Epoch 270  loss 1.0946  correct 50/50  time 0.087 s/epoch
```

The first epoch takes about 5 seconds because Numba compiles the functions. A
short width-100 run averaged 0.302 seconds per epoch including compilation.
