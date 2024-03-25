    
    
    $$
    You encounter a grammar production like expr -> expr / 2. If you know the type of 'expr' is guaranteed to be an unsigned integer, suggest a parser-level optimization. 


     You are parsing an expression with multiple additions and multiplications. The target architecture has instructions that can perform multiply-and-add operations in a single cycle. Propose a way the parser could facilitate using these instructions.


     A simple loop has a multiplication by a constant within it. The target architecture allows multiplications by powers of 2 to be done with shifts. Calculate how many assembly instructions you save by applying this optimization if the constant is 16.
    $$
```c


    for (int i = 0; i < n; ++i) {
//     result += value * 16; // Multiplication by 16
// }
// Optimized code:
// for (int i = 0; i < n; ++i) {
//     result += value << 4; // Left shift by 4 bits (equivalent to multiplying by 16)
// }

```


