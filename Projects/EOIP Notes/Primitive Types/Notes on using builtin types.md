
1. Be very comfortable with bitwise operations. [[Bitwise operations in python]]
2. Understand how to use **mask** and learn how to create them in a machine independent way
3. Know fast ways to clear the lowermost set bit (also things like: set the lowermost bit to zero, get the index, etc)
4. understand **signedness** and its implications to **shifting**
5. Consider using a **cache** to accelerate operations by using it to brute-force small inputs.
6. Be aware that commutativity and associativity can be used to perform operations in parallel and reorder operations.

**Refer to the python code in primitive types for a better understanding**

8. The key methods for numeric types are abs(-34.5), math. ceil(2. 17), math. floor(3. 14), min(x, -4), max(3 .14, y), pow(2 .7, 3.14) (alteratively, 2.71 ** 3.14), and math. sqrt (22 5).
9. Know how to interconvert integers and strings, e.g., str(421) , int('42'), floats and strings, e.g., str(3. 14), float(' 3. 14').
10. Unlike integers, floats are not infinite precision, and it's convenient to refer to infinity as float('inf ') and float('-inf '). These values are comparable to integers, and can be used to create psuedo max-int and pseudo min-int.When comparing floating point values consider using math.isclose() - it is robust, e.g., when comparing very large values, and can handle both absolute and relative differences.
11. The key methods in random are random.randrange(28), random.randint(8,1.6), random. random(), random. shuffle (A), and random. choice(A).