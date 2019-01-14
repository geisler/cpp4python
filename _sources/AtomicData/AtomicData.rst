..  Copyright (C)  Jan Pearce and Brad Miller
    This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/.

Using Data in C++
~~~~~~~~~~~~~~~~~

C++ requires the users specify the specific data type of each variable
before it is used.
The primary C++ built-in atomic data types are: integer (``int``),
floating point (``float``), double precision floating point (``double``),
Boolean (``bool``), and character (``char``). There is also a special
type which holds a memory location called ``pointer``.

Numeric Atomic Data Types
~~~~~~~~~~~~~~~~~~~~~~~~~

Numeric C++ data types include ``int`` for integer, ``float``
for floating point, ``double`` for double precision floating point.

The standard arithmetic operations, +, -, \*, and /
are used with optional parentheses to force the order of
operations away from normal operator precedence.

In Python we can use ``//`` to get integer division.
In C++, we declare all data types.
When two integers are divided in C++, the integer portion of the
quotient is returned and the fractional portion is removed.
To get the whole quotient, declaring one of the numbers as a float will
convert the entire result into floating point.

Exponentiation in C++ is done using ``pow()`` from the ``cmath`` library
and the remainder (modulo) operator is done with ``%``.

Run the following code to see that you understand each result.

.. tabbed:: intro

  .. tab:: C++

    .. activecode:: intro_1cpp
        :caption: Basic Arithmetic Operators C++
        :language: cpp

        #include <iostream>
        #include <cmath>
        using namespace std;

        int main(){

            cout << (2+3*4) << endl;
            cout << (2+3)*4 << endl;
            cout << pow(2, 10) << endl;
            cout << float(6)/3 << endl;
            cout << float(7)/3 << endl;
            cout << 7/3 << endl; //In C++ this is integer division
            cout << 7%3 << endl;
            cout << float(3)/6 << endl;
            cout << 3/6 << endl;
            cout << 3%6 << endl;
            cout << pow(2, 100) << endl;

            return 0;
        }

  .. tab:: Python

    .. activecode:: intro_1py
        :caption: Basic Arithmetic Operators Python

        def main():

            print(2+3*4)
            print((2+3)*4)
            print(2**10)
            print(6/3)
            print(7/3)
            print(7//3)
            print(7%3)
            print(3/6)
            print(3//6)
            print(3%6)
            print(2**100)

        main()

When declaring numeric variables in C++,
modifiers like ``short``, ``long``, and ``unsigned``
can optionally be used to help
to ensure space is used as efficiently as possible.

.. mchoice:: mc_integer_div
   :answer_a: 1
   :answer_b: 1.5
   :answer_c: 2
   :answer_d: A run-time error will occur.
   :answer_e: none of the above
   :correct: a
   :feedback_a: Right!  This is like ``3//2`` in Python.
   :feedback_b: No. Integer division is used. Try again.
   :feedback_c: No. Integer division is used. Try again.
   :feedback_d: No, C++ generally will try to do as you ask.
   :feedback_e: One of the above is correct.

   what is the result of dividing ``3/2`` in C++?


.. mchoice:: mc_exponentiation
  :answer_a: ``4**5``
  :answer_b: ``5**4``
  :answer_c: ``4^5``
  :answer_d: ``pow(4, 5)``
  :correct: e
  :feedback_a: No, ``**`` is used in Python, not C++.
  :feedback_b: No, ``**`` is used in Python, not C++, and the operators are reversed.
  :feedback_c: No. The ``^`` is a valid operator in C++, but it does something else.
  :feedback_d: You got it!

  How do I raise 4 to 5th power in C++?


Boolean Data
~~~~~~~~~~~~

Boolean data types are named after George Boole who was an English mathematician,
so the word "Boolean" should be capitalized. However,
the Boolean data type, in C++ uses the keyword ``bool``
which is not capitalized.
The possible state values
for a C++ Boolean are lower case ``true`` and ``false``.
Be sure to note the difference in capitalization from Python.
In Python, these same truth values are capitalized, while in C++,
they are lower case.

C++ uses the standard Boolean operators, but they are represented
differently than in Python: ``&&`` (and), ``||`` (or), and ``!`` (not).
Note that the output values for ``true`` and ``false`` are ``1``
and ``0`` respectively.

.. tabbed:: logical1

  .. tab:: C++

    .. activecode:: logical_1cpp
        :caption: Logical Operators C++
        :language: cpp

        #include <iostream>
        using namespace std;

        int main() {
          cout << true << endl;
          cout << false << endl;
          cout << (true || false) << endl;
          cout << (true && false) << endl;
          return 0;
        }

  .. tab:: Python

        .. activecode:: logical_1py
            :caption: Logical Operators Python

            def main():
                print(True)
                print(False)
                print(True or False)
                print(True and False)
            main()


Boolean data objects are also used as results for comparison operators
such as equality (==) and greater than (:math:`>`). In addition,
relational operators and logical operators can be combined together to
form complex logical questions. :ref:`Table 1 <tab_relational>` shows the relational
and logical operators with examples shown in the session that follows.

.. _tab_relational:

.. table:: **Table 1: C++ Relational and Logical Operators**

    =========================== ============== =================================================================
             **Operation Name**   **Operator**                                                   **Explanation**
    =========================== ============== =================================================================
                      less than      :math:`<`                                                Less than operator
                   greater than      :math:`>`                                             Greater than operator
             less than or equal     :math:`<=`                                    Less than or equal to operator
          greater than or equal     :math:`>=`                                 Greater than or equal to operator
                          equal     :math:`==`                                                 Equality operator
                      not equal     :math:`!=`                                                Not equal operator
                    logical and     :math:`&&`                          Both operands true for result to be true
                     logical or     :math:`||`        One or the other operand is true for the result to be true
                    logical not      :math:`!`   Negates the truth value, false becomes true, true becomes false
    =========================== ============== =================================================================


.. tabbed:: basiclogical

  .. tab:: C++

    .. activecode:: locicalcpp
        :caption: Basic Relational and Logical Operators C++
        :language: cpp

        #include <iostream>
        using namespace std;

        int main(){

            cout << (5 == 10) << endl;
            cout << (10 > 5) << endl;
            cout << (5 >= 1 && 5 <= 10) << endl;

            return 0;
        }

  .. tab:: Python

    .. activecode:: logicalpy
        :caption: Basic Relational and Logical Operators Python

        def main():

            print(5 == 10)
            print(10 > 5)
            print((5 >= 1) and (5 <= 10))

        main()


A C++ variable can be created when declared and initialized with a type on
the left-hand side of an assignment statement. Assignment statements
provide a way to associate a name with a value. The variable will hold a
piece of data. Consider the
following session:

.. activecode:: booleanpitfall
    :language: cpp

    #include <iostream>
    using namespace std;

    int main(){

        int theSum = 4;
        cout << theSum << endl;

        theSum = theSum + 1;
        cout << theSum << endl;

        bool theBool = true;
        cout << theBool << endl;

        theBool = 4;
        cout << theBool << endl;

        return 0;
    }

The assignment statement ``int theSum = 0;`` creates a variable called
``theSum`` and initializes it to hold the data value of ``0``.
As in Python, the right-hand side of the assignment
statement is evaluated and the resulting data value is
“assigned” to the variable named on the left-hand side.
Here the type of the variable is integer.
In Python, if the type of the data
changes in the program, so does the type of the variable.
However, in C++, the data type cannot change.
This is a characteristic of C++'s static typing. A
variable can hold ever only one type of data.
Pitfall: C++ will often simply try to do the assignment you requested without
complaining. Note what happened in the code above in the final output.

Character Data
~~~~~~~~~~~~~~

In Python strings can be created with single or double quotes.
In C++ single quotes are used for the character (``char``) data type,
and double quotes are used for the string data type.

Consider the following code.


.. tabbed:: basiclogical

  .. tab:: C++

    .. activecode:: charcpp
        :caption: Considering characters and strings
        :language: cpp

        #include <iostream>
        #include <string>
        using namespace std;

        int main(){

            string strvar = "b";
            char charvar = 'b';

            cout << ('b' == charvar) << endl;
            cout << ("b" == strvar) << endl;
            //cout << ('a' == "a") << endl; // will error!

            return 0;
        }

  .. tab:: Python

    .. activecode:: charpy
        :caption: Python strings

        def main():

            strvar = "b"
            charvar = 'b'

            print('b' == charvar)
            print("b" == strvar)
            print('a' == "a")

        main()

.. mchoice:: mc_cpp_strings
   :answer_a: ' '
   :answer_b: " "
   :answer_c: ' ' or " " may be used
   :answer_d: It depends upon the implementation.
   :answer_e: none of the above
   :correct: b
   :feedback_a: No, single quotes are only used for single characters.
   :feedback_b: Good job reading!
   :feedback_c: No. Try again.
   :feedback_d: No. Try again.
   :feedback_e: One of the above is indeed correct.

   If I want to create a string in C++, what set of symbols may be used?


Pointers
~~~~~~~~

A C++ **pointer** is a variable that stores a memory address.

We know that variables in a computer program are used to label data with a
descriptive identifier so that the data can be accessed and used by that
computer program. However, some differences in how variables are implemented
in Python and in C++ are worthy of discussion.

Let's look at some examples of storing an integer in Python and C++.

In Python every single thing is stored as an object.
Hence, a Python variable is actually a reference to an object that is stored in memory.
Hence, each Python variable requires two memory locations:
one to store the reference, and the other to store the variable value itself in an object.

In C++ the value of each variable is stored directly in memory without the need
for either a reference or an object. This makes access faster, but it is one of
the reasons we need to declare each variable because different types take differing
amounts of space in memory!

The following code declares a variable called *varName* that has in it a
value of 100:

::

    // Python reference for a single integer value
    varName = 100

.. _fig_py_reference:

.. figure:: Figures/python_reference.png
   :align: center
   :alt: "arrow from varName to box containing 100 object"

   Figure 4: Python reference

::

    // C++ variable declaration and assignment of an integer value
    int varName = 100;

In C++ the results of running this code will look like the diagram below:

.. _fig_cpp_reference:

.. figure:: Figures/cpp_var.png
   :align: center
   :alt: "Box named varName containing value of 100"

   Figure 4: C++ variable

In each case, when we want to output the value to the console, we use the variable name
to do so.

But, we can also identify the memory location of the variable,
which is sometimes very valuable. In both Python and C++, this address is
may change each time the program is run. In C++, this will always look
odd because it will be the actual memory address written in a hexadecimal code
which is a base 16 code like 0x7ffd93f25244.
In Python it is implementation dependent,
it is sometimes a hexadecimal code and sometimes just a count or another
way to reference the address.

In Python we use ``id`` to reference the address,
while in C++ we use the *address-of operator*, ``&``.

.. tabbed:: memory-addresses

  .. tab:: C++

    .. activecode:: address_cpp
        :caption: Memory addresses in C++
        :language: cpp

        #include <iostream>
        using namespace std;

        int main(){
            int varName = 101;
            cout << varName << endl;
            cout << &varName << endl;
            return 0;
        }

  .. tab:: Python

    .. activecode:: address_py
        :caption: Memory identifier in Python

        def main():
            varName = 101;
            print(varName)
            print(id(varName))

        main()


In both Python and C++, variables are stored in memory locations which are dependent
upon the run itself. If you repeatedly run the above code in either C++ or Python, you may
see the location change.

As suggested above, in Python, it is impossible to store a variable directly.
Instead, we must use a variable name and a reference to the data object.
(Hence the arrow in the image.)
In C++, variables store values directly, because they are faster to reference.

References are slower, but they are sometimes useful.
If in C++, we want to create a analogous reference to a memory location in C++,
we must use a special syntax called a **pointer**.

Pointer Syntax
^^^^^^^^^^^^^^

When declaring a pointer in C++ that will "point" to the memory address of some
data type, like all variables do in Python,
you will use the same rules of declaring variables and data types.
The key difference is that there must be an asterisk (*) between the data type and the
identifier.

::

    variableType *identifier; // syntax to declare a C++ pointer
    int *ptrx; // example of a C++ pointer to an integer

White space in C++ generally does not matter, so the following pointer declarations
are identical:

::

    SOMETYPE *variablename; // preferable
    SOMETYPE * variablename;
    SOMETYPE* variablename;

However, the first declaration is preferable because it is clearer to the
programmer that the variable is in fact a pointer because the asterisk is closer
to the variable name.

The address-of operator, ``&``
------------------------------

Now that we know how to declare pointers, how do we give them the address of
where the value is going to be stored? One way to do this is to have a pointer
refer to another variable by using the address-of operator, which is denoted by the
ampersand symbol, ``&``. The address-of operator ``&`` does exactly what it indicates,
namely it returns the address.

The syntax is shown below, where varName stores the value, and varPntr stores
the address of where varName is located:

::

    variableType varName;  // a variable to hold the value
    variableType *varPntr = &varName;  // a variable pointing to the address of varName

Keep in mind that when declaring a C++ pointer, the pointer needs to
reference the same type as the variable or constant to which it points.

Expanding on the example above where varName has the value of 100.

::

    //variable declaration for a single integer value
    int varName = 100;
    int *varPntr;
    varPntr = &varName;

The results of running this C++ code will look like the diagram below.

.. _fig_point2:

.. figure:: Figures/point2.png
   :align: center
   :alt: image

   Figure 5: FIXME2

Accessing Values from Pointers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

So, once you have a C++ pointer, how do you access the values associated with that location?
You use the asterisk before the pointer variable, which
goes to that address, effectively *dereferencing* the pointer,
meaning that it will find the location of the value stored where the pointer was
pointing.

In other words, varName and \*varPntr (note the asterisk in front!) reference the same
value in the code above.

Let's extend the example above to output the value of a variable and its address
in memory:

 _deferencing:

    .. activecode:: examplecpp
        :language: cpp

        #include <iostream>
        using namespace std;

        int main( ) {
            int varName = 100;
            int *varPntr = &varName;

            cout << "varName value: " << varName << endl;
            cout << "varPntr location: " << varPntr << endl;
            cout << "varPntr points to varName: " << endl;
            cout << "dereference varPntr: " << *varPntr << "\n\n";

            varName = 50;

            cout << "varName changed: " << varName << endl;
            cout << "varPntr still points to varName: " << endl;
            cout << "dereference varPntr: " << *varPntr << "\n\n";

            *varPntr = 2000;
            cout << "Changed *varPntr, ie varName to: " << endl;
            cout << "dereference varPntr: " << *varPntr << "\n\n";

            return 0;
        }

Compiling and running the above code will have the program output the
value in varName,
what is in varPntr (the memory address of varName),
and what value is located at that
memory location.

The second output sentence is the address of varName, which would most likely be
different if you run the program on your machine.

WARNING: What happens if you forget the asterisk
when assigning a value to a pointer
and had the following instructions instead?

.. _cpp_address_error:

    .. activecode:: cpp_address_error1
        :language: cpp

        #include <iostream>
        using namespace std;

        int main( ) {
            int varName = 100;
            int varPntr = varName; // Note no asterisk,
                // varPntr now refers to memory position 100,
                // whatever happens to be there!
                // You might get an error or you might not!

             cout << "varName value: " << varName << endl;
             cout << "varPntr location: " << varPntr << endl;
             cout << "varPntr points to varName: " << endl;
             cout << "dereference varPntr: " << *varPntr << "\n\n";


**This is BAD, BAD, BAD!**

.. _fig_point3:

.. figure:: Figures/point_broken.png
   :align: center
   :alt: image

   Figure 6: FIXME3

If your compiler does not catch that error (the one for this class may),
the first ``cout`` instruction outputs

::

    After changing *varPntr, varName now has: 50

which is expected because you changed where varPntr pointing to and
NOT the contents of where it is pointing.

The second ``cout`` instruction is a disaster because
(1) You don't know what is stored in location 100 in memory, and
(2) that location is outside of your segment (area in memory reserved
for your program), so the operating system will jump in with a message
about a "segmentation fault". Although such an error message looks bad,
a "seg fault" is in fact a helpful error because unlike the elusive logical
errors, the reason is fairly localized.

The null pointer
^^^^^^^^^^^^^^^^

Like ``None`` in Python, the ``null`` pointer in C++ points to
nothing and is often denoted by the keyword null or by 0.
The null pointer is often used in conditions and/or in logical operations.

The following example demonstrates how the null pointer works.
The variable ptrx initially has the address of x when it is declared.
On the first iteration of the loop, it is assigned the value of null (i.e. 0)
thereby ending the loop:

.. _lst_cppcode2:

    .. activecode:: nullexamplecpp
        :language: cpp

        #include <iostream>
        using namespace std;

        int main( ) {
            int x = 12345;
            int *ptrx = &x;

            while (ptrx) {
                cout << "Pointer ptrx points to " << &ptrx;
                ptrx = null;
            }

            cout << "Pointer ptrx points to nothing!\n";
        }

Helpful Tip: The null pointer becomes very useful when you must test
the state of a pointer, such as whether the assignment to an address
is valid or not.


Summary
~~~~~~~

1. All variables must be declared before use in C++.

2. C++ has typical built-in numeric types: ``int`` is for integers and ``float`` and ``double`` are used for floating point depending on the number of digits desired.

3. C++ has the Boolean type ``bool`` that holds ``true`` or ``False``.

4. The character data type ``char`` holds a single character.

5. Pointers are a type of variable that stores a memory address. To declare a pointer, an  ``*`` is used before the variable name that is supposed to store the location.


Check Yourself
~~~~~~~~~~~~~~


.. mchoice:: mc_characters
   :answer_a: ' '
   :answer_b: " "
   :answer_c: ' ' or " " may be used
   :answer_d: It depends upon the implementation.
   :answer_e: none of the above
   :correct: a
   :feedback_a: Right!
   :feedback_b: No. Double quotes are only used for strings.
   :feedback_c: No. Try again.
   :feedback_d: No. Try again.
   :feedback_e: One of the above is indeed correct.

   If I want to use the ``char`` type in C++, what set of symbols must be used?


.. fillintheblank:: memoryvar

  A/an ``___`` is used to store a memory address in C++?

 - :pointer: Right!
   :variable: Be more specific!
   :reference: That's Python, not C++!
   :default: Incorrect. Please try again


.. mchoice:: mc_memory
  :answer_a: using ``&``
  :answer_b: using ``*``
  :answer_c: using ``id``
  :answer_d: It depends upon the implementation.
  :answer_e: none of the above
  :correct: a
  :feedback_a: Right! ``&`` is the "address-of" operator, used to reference an address.
  :feedback_b: No. ``int *p;`` defines a pointer to an integer, and ``*p`` would dereference that pointer, i.e. retrieve the data that p points to.
  :feedback_c: No. This is used in Python.
  :feedback_d: No. Try again.
  :feedback_e: One of the above is indeed correct.

  How may one reference a variable's memory address in C++?