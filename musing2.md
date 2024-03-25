A dead variable
def example():
    x = 5  # x is initialized
    x = x + 2  # x is modified
    x = 10  # x is reassigned without being referenced in between
    print(x)  # x is referenced

example()

Dead Code

def example():
    x = 5
    if x > 10:  # This condition is never true
        print("This is dead code")  # This line is never executed

    y = 10
    y = y + 5  # This operation has no effect because y is not used afterwards

example()


Dead code elimination and constant propagation 

def example():
    x = 5
    y = x * 2  # Constant propagation can replace 'x' with 5
    if y > 10:  # This condition is now always true
        print("This is not dead code anymore")  # This line is now always executed

    z = 10
    z = z + 5  # Dead code elimination can remove this line
    return y

example()


It's always safe to eliminate dead assignments

def example():
    x = 5
    y = x * 2
    print(y)

    z = complex_function()  # This is a dead assignment if 'z' is not used later
    return y

def complex_function():
    print("This function has side effects!")
    return 10

example()



Basic Building Blocks 


def example():
    x = 5
    y = x * 2
    print(y)
    return y


def example(a):
    x = 5
    if a > 0:
        y = x * 2
    else:
        y = x * 3
    print(y)
    return y



int main() {
    volatile int i = 10; // 'volatile' keyword is used
    i = i + 10;
    printf("%d\n", i);
    return 0;
}
volatile keyword tells the compiler not to optimize the line i = i + 10;. Without volatile, the compiler might optimize this line by directly assigning the value 20 to i



A compiler might use a symbol table to track the values of variables during peephole optimization.

# Before optimization
x = 2 * 3
y = x + 5
z = y / (x - 1)
print(z)

# Symbol table after constant folding and propagation
# x: 6
# y: 11
# z: 11 / 5

# After optimization
x = 6
y = 11
z = 11 / 5
print(z)





These optimizations often work on an Abstract Syntax Tree (AST) or Control Flow Graph (CFG) representation of the code.

    +
   / \
  a   *
     / \
    b   c

    to     +
   / \
  a   6




if (a > b) {
    c = a;
} else {
    c = b;
}


  Start
   |
   v
a > b? ----No---> c = b
   |
 Yes
   |
   v
c = a
   |
   v
 End


   Start
   |
   v
a > b? 
   |
 Yes
   |
   v
c = a
   |
   v
 End




