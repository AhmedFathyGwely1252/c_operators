# C programming Session 2

## Table of Contents

-   [Variables](#variables)
-   [Interacting with user](#interacting-with-user)
-   [Casting](#casting)
-   [Operators](#operators)
-   [Comments](#comments)
-   [Branching](#branching)

### Variables

-   Declaration vs Initialization

          Declaration Statement :
              [data type] [variable name];

    For Example:

    ```C
        int x;
        float y;
        char z;
    ```

          Initialization Statement :
              [data type] [variable name] = [expression];

    For Example:

    ```C
        int x = 11;
        float y = 12.3;
        char z = 'z';
    ```

-   Data types

          bool : Boolean
          [signed / unsigned] char : character
          [signed / unsigned] [short / long / long long] int : integer
          float : floating decimal point
          double : double precision floating decimal point
          long double : long double precision floating decimal point

-   Naming Rules
-   Naming Convention

    For a variable represents the `online students number`

    ```C
        // Snake Case :
            int online_students_number;
        // Camel Case :
            int onlineStudentsNumber;
        // Pascal Case :
            int OnlineStudentsNumber;
        // Kebab Case :
            int online-students-number; // not valid in variable naming rules in C
    ```

-   Storage in memory

    > In C, the size of each variable depends on its data type.

    Here are the standard sizes for each data type:

        char           1 byte
        short          2 bytes
        int            4 bytes
        long           4 or 8 bytes (depending on the platform)
        long long      8 bytes
        float          4 bytes
        double         8 bytes
        long double    8 or 16 bytes (depending on the platform)

-   Behavior

    -   Overflow

        > Overflow occurs when you attempt to store inside any variable a value that is larger than the maximum value that it can hold.

        for example :

        ```C
        	unsigned char x = 250; // Maximum Value this data type can store is 255
        	x += 5;
        	printf("%d\n", x); // Now x = 255 (Maximum)
        	x++;               // After this increment x will roll back to Minimum Value
        	printf("%d\n", x); // Now x = 0

        ```

    -   Garbage value

        > A garbage value refers to an unpredictable and undefined value stored in a variable or memory location that has not been explicitly initialized.

        for example:

        ```C
        	int x; // declaring variable x without initializing it
        	printf("The value of x is: %d\n", x); // Here prints Random Number
        ```

        ```C
        	int x = 0; // initializing variable x to a specific value
        	printf("The value of x is: %d\n", x); // Here prints 0
        ```

### Interacting with user

-   Input

    > To read from input stream you can use `scanf()` function.

    Function Prototype:

    ```C
    	// scanf([format string],number of variable addresses)
    	int scanf(const char *format, ...);
    ```

    for example :

    ```C
    	// To Read One Variable
    	int x;
    	scanf("%d", &x);

    	// To Read More than one Variable
    	int x, y;
    	scanf("%d%d",&x, &y);
    ```

-   Output

    > To print to output stream you can use `printf()` function.

    Function Prototype:

    ```C
    	// printf([format string],number of expression)
    	int printf(const char *format, ...);
    ```

    for example :

    ```C
    	// To print One Variable
    	int x = 1;
    	printf("%d", x);

    	// To print More than one Variable
    	int x = 1, y = 2;
    	printf("%d%d", x, y);
    ```

-   Format String

    > It specifies the format of the input or output that the function will read or write containing conversion specifiers.

    Conversion specifiers:

        %d	Signed integer
        %u	Unsigned integer
        %f %g	Floating-point number
        %lf	Double-precision floating-point number
        %c	Character
        %s	String
        %p	Pointer

### Operators

-   Types of Operators in C

    -   Arithmetic

        -   Binary

                  +   Addition
                  -   Subtraction
                  *   multiplication
                  /   Division
                  %   Modulus [remainder of the division]



            ```C
                     c = a+b;
                     printf("a+b = %d \n",c);
                     c = a-b;
                     printf("a-b = %d \n",c);
                     c = a*b;
                     printf("a*b = %d \n",c);
                     c = a/b;
                     printf("a/b = %d \n",c);
                     c = a%b;
                     printf("Remainder when a divided by b = %d \n",c);
            
            ```

-   test1

             int x ;
    scanf("%d", &x);
    
    int num1 , num2 , num3, temp ;
    
    num1 = x % 10 ;
    temp = x / 10 ;
    num2 = temp % 10 ;
    temp = temp / 10 ;
    num3 = temp % 10 ;
    
    printf("%d %d %d", num1 , num2 , num3)


        -   Unary

                  ++ [post increment] / [pre increment]
                  -- [post decrement] / [pre decrement]

                  For Pre operators :
                      The increment comes first then the evaluation
                  For Post operators :
                      The evaluation comes first then the increment

            for example:

            ```C
                // For Post Increment
                int x = 11;
                printf("%d\n",x++); // Here Prints 11
                printf("%d\n",x);     // Here Prints 12

                // For Pre Increment
                int y = 11;
                printf("%d\n",++y); // Here Prints 12
                printf("%d\n",y);   // Here Prints 12
            ```


            What Should be the printed value here :

            ```C
                int x = 12;
                int y = 11;
                printf("%d\n",++x + y--);
                printf("%d",x++ - ++y);
            ```



    -   Assignment

            =
            +=
            -=
            *=
            /=
            %=

      ```C
         int a = 5, c;

         c = a;      // c is 5
         printf("c = %d\n", c);
         c += a;     // c is 10 
         printf("c = %d\n", c);
         c -= a;     // c is 5
         printf("c = %d\n", c);
         c *= a;     // c is 25
         printf("c = %d\n", c);
         c /= a;     // c is 5
         printf("c = %d\n", c);
         c %= a;     // c = 0
         printf("c = %d\n", c);

      ```
      



    -   Relational

            ==
            !=
            <
            >
            >=
            <=

       ```C
            int a = 5, b = 5, c = 10;

            printf("%d == %d is %d \n", a, b, a == b);
            printf("%d == %d is %d \n", a, c, a == c);
            printf("%d > %d is %d \n", a, b, a > b);
            printf("%d > %d is %d \n", a, c, a > c);
            printf("%d < %d is %d \n", a, b, a < b);
            printf("%d < %d is %d \n", a, c, a < c);
            printf("%d != %d is %d \n", a, b, a != b);
            printf("%d != %d is %d \n", a, c, a != c);
            printf("%d >= %d is %d \n", a, b, a >= b);
            printf("%d >= %d is %d \n", a, c, a >= c);
            printf("%d <= %d is %d \n", a, b, a <= b);
            printf("%d <= %d is %d \n", a, c, a <= c);
       ```





    -   Logical

            &&  Logical And
            ||  Logical Or
            !   Logical Not



       ```C
            int a = 5, b = 5, c = 10, result;

            result = (a == b) && (c > b);
            printf("(a == b) && (c > b) is %d \n", result);

            result = (a == b) && (c < b);
            printf("(a == b) && (c < b) is %d \n", result);

            result = (a == b) || (c < b);
            printf("(a == b) || (c < b) is %d \n", result);

            result = (a != b) || (c < b);
            printf("(a != b) || (c < b) is %d \n", result);

            result = !(a != b);
            printf("!(a != b) is %d \n", result);

            result = !(a == b);
            printf("!(a == b) is %d \n", result);
       ```



    -   Bitwise

            &   Bitwise And
            |   Bitwise Or
            ~   One's complement
            ^   Bitwise Xor
            >>  Right Shift
            <<  Left Shift





    -   Additional Operators in C

            Will be Discussed Later:
            ,       Comma
            .       Dot
            &       Address-of
            *       Asterisk
            sizeof  Size-of
            []      Brackets
            ?:      Ternary Operator



-   Logical vs Bitwise operators

    > Logical operators are used to evaluate the truth value of logical expressions and return `boolean` values (true or false), whereas bitwise operators are used to perform operations on `individual bits` of `integer` values.

    for example :

    ```C
        int x = 3;
        int y = 4;
        printf("%d\n",x & y);   // Here the evaluation result = 0 (all bits = 0)
        printf("%d\n",x && y);  // Here the evaluation result = 1 (True)
    ```

-   Applications of operators

    -   Get Bit

    ```C
        int bitValue = (num >> bit) & 1;
    ```
    -   Set Bit
    ```C
        num = num | (1 << bit);
    ```
    -   Clear Bit
    ```C
        num = num & (~(1 << bit));
    ```
    -   Toggle Bit
    ```C
        num = num ^ (1 << bit);
    ```

-   floating numbers comparison:

    for example:

    ```C
        #include<stdio.h>
        int main()
        {
            float x = 0.1;
            if (x == 0.1)
                printf("IF");
            else if (x == 0.1f)
                printf("ELSE IF");
            else
                printf("ELSE");
        }
    ```

    another example:

    ```C
        #include<stdio.h>
        int main()
        {
            float x = 0.5;
            if (x == 0.5)
                printf("IF");
            else if (x == 0.5f)
                printf("ELSE IF");
            else
                printf("ELSE");
        }
    ```

    for more details Read this [article](https://www.geeksforgeeks.org/comparison-float-value-c/).

### Casting

> Casting is the process of converting a value from one data type to another.

-   Implicit Casting

    > Implicit casting occurs automatically when the compiler converts a value from one data type to another in certain situations.

    for example:

    ```C
        int x = 5;
        float y = 2.5;
        float result = x + y;
        /*
        In this example, the integer value x is implicitly cast to a float value, so that it can be added to the float value y. The result of the addition is then stored in the float variable result.
        */
    ```

-   Explicit Casting

    > Explicit casting requires the use of a cast operator, which explicitly instructs the compiler to convert a value from one data type to another.

    for example :

    ```C

        // The Default Behavior in This case when dividing integers
        // the result will be casted to integer implicitly.
        // So y will hold the value of the division result = 5
        int x = 11;
        float y = x / 2;
        printf("%f",y); // Here prints 5


        // after explicitly casting x to be float before division
        // will keep the real value after the division
        int x = 11;
        float y = (float) x / 2;
        printf("%f",y); // Here prints 5.5
    ```

### Comments

-   One line Comment

    > You can use double forward slashes `//` to create a comment in C. Any text following the // on the same line will be ignored by the compiler.

    for example:

    ```C
        int x = 11; //  this will be ignored
        int y = 11;     this will not be ignored
    ```

-   Multi line Comment

    > multi-line comments can be created by enclosing the comments within `/*` and `*/` delimiters. Any text within these delimiters will be ignored by the compiler, regardless of how many lines it spans.

    for example:

    ```C
        /*
        This is an example of a multi-line comment in C.
        Anything between the opening and closing delimiters
        will be ignored by the compiler, including any code or text
        that spans multiple lines.
        */
        int x = 11;
    ```

### Branching

-   Conditional Branching

    -   if condition

        ```C
            if(/* condition */) {
                // Statement
                // Statement
            }

            /***************************************/

            if(/* condition */) {
                // Statement
                // Statement
            }
            else{
                // Statement
                // Statement
            }

            /***************************************/

            if(/* condition */) {
                // Statement
                // Statement
            }
            else if(/* condition */) {
                // Statement
                // Statement
            }
            else{

            }
        ```

    -   switch case

        ```C
            switch (/* expression */) {
                case /* Constant decimal (non floating) numerical Value */ :
                    // Statement
                    // Statement
                    break;
                case /* Constant decimal (non floating) numerical Value */ :
                    // Statement
                    // Statement
                    break;
                case /* Constant decimal (non floating) numerical Value */ :
                    // Statement
                    // Statement
                    break;
                default:
                    // Statement
                    // Statement
            }
        ```

    -   Ternary Operator

        ```C
            // short handed way to write If-else conditions
            int x;
            if(/* condition */) {
                x = 1;
            }
            else{
                x = 2;
            }
            x = (/* condition */) ? 1 : 2;

            /*
                Important Note :
                the returned expressions in a ternary operator (?:) must be of the same type or have compatible types.

                for example :

                int a = 42;
                double b = 3.14;
                int result = (a > b) ? a : b;

                [this will generate compilation error]

            */
        ```

