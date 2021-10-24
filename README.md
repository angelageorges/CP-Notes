# CP-Notes

## UNIT-I Basic Techniques
### 1. Introduction

- Input and output is sometimes a bottleneck in the program. The following lines at the beginning of the code make input and output more efficient:
ios::sync_with_stdio(0);
cin.tie(0);

- Note that the newline "\n" works faster than endl, because endl always
causes a flush operation.

- The C functions scanf and printf are an alternative to the C++ standard
streams. They are usually a bit faster, but they are also more difficult to use. The
following code reads two integers from the input:
int a, b;
scanf("%d %d", &a, &b);

The following code prints two integers:
int a = 123, b = 456;
printf("%d %d\n", a, b);

- Sometimes the program should read a whole line from the input, possibly
containing spaces. This can be accomplished by using the getline function:
string s;
getline(cin, s);

- Sometimes, the answer to a problem is a very large number but it is enough
to output it ”modulo m”, i.e., the remainder when the answer is divided by m (for
6
example, ”modulo 10^9 + 7”). The idea is that even if the actual answer is very
large, it suffices to use the types int and long long.

- An important property of the remainder is that in addition, subtraction and
multiplication, the remainder can be taken before the operation:

- Thus, we can take the remainder after every operation and the numbers will
never become too large.

- However, in
C++ and other languages, the remainder of a negative number is either zero or
negative. An easy way to make sure there are no negative remainders is to first
calculate the remainder as usual and then add m if the result is negative:
x = x%m;
if (x < 0) x += m;

- It is risky to compare floating point numbers with the == operator, because it
is possible that the values should be equal but they are not because of precision
errors. A better way to compare floating point numbers is to assume that two
numbers are equal if the difference between them is less than Ɛ, where Ɛ is a
small number.
In practice, the numbers can be compared as follows (Ɛ= 10^-9):
if (abs(a-b) < 1e-9) {
// a and b are equal
}

**Shortening Code**

Type Names

- Using the command typedef it is possible to give a shorter name to a datatype.
For example, the name long long is long, so we can define a shorter name ll:
 typedef long long ll;
 
The command typedef can also be used with more complex types. For example,
the following code gives the name vi for a vector of integers and the name pi for
a pair that contains two integers.
typedef vector<int> vi;
typedef pair<int,int> pi;
  
Macros
  
- Another way to shorten code is to define macros. A macro means that certain
strings in the code will be changed before the compilation. In C++, macros are
defined using the #define keyword.
For example, we can define the following macros:
#define F first
#define S second
#define PB push_back
#define MP make_pair

- A macro can also have parameters which makes it possible to shorten loops
and other structures. For example, we can define the following macro:
#define REP(i,a,b) for (int i = a; i <= b; i++)
                                         
- #define SQ(a) (a)*(a)
                                      
                              
