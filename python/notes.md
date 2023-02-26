#Notes on Python

# Python Data Types:
# Numbers
# Strings
# Booleans

# Variables: 
    # Can start with upper or lowercase letters. However, they are case-sensitive.
    # For example Income and income are two different variable.
    # Numbers can be part of variables but variables cannot begin with numbers. income12 is valid but 12income is not.
    # _ can appear anywhere in the variable.
    # Spaces are not allowed.
    # ** A good idea is to be descriptive with variables for example instead of inc or income something like weekly_income**

# Integers:
    # Comprised of all the positive and negative whole numbers.
    # Different integer takes up different amounts of memory.
# Example of Integer:
print(10)  # A positive integer
print(-3000)  # A negative integer

num = 123456789  # Assigning an integer to a variable
print(num)
num = -16000  # Assigning a new integer
print(num)  # Prints new value for num

# Floating Point Numbers
    # Floats refer t positive or negative decimal numbers.
    # Occupies 24 bytes of memory.
    # In Python 5 is considered an integer while 5.0 is considered a float.
# Example of Float:
print(1.00000000005)  # A positive float
print(-85.6701)  # A negative float

flt_pt = 1.23456789
print(flt_pt)

# Complex Numbers
    # Just like the print() statement is used to print values, complex() is used to create complex numbers.
    # It requires two values.
    # Complex numbers are useful for modelling physics and electrical engineering.
    # The first one will be the real part of the complex number, while the second value will be the imaginary part.
    # complex(real, imaginary)
    # Takes up 32 bytes of memory.
print(complex(10, 20))  # Represents the complex number (10 + 20j)

# Booleans
    # Also knows as bool, allows us to choose between two values: True and False
    # *** The first letter of a bool needs to be capitalized in python.***
# Example
print(True);

f_bool = False
print(f_bool);
    # Output
    # True
    # False

# Strings
    # A string is a collection of characters closed within single, double or triple quotation marks.
    # A string can contain a single character or be entirely empty.
    # To add a multi-line string we can use triple quotes.

print("Harry Potter!")  # Double quotation marks

got = 'Game of Thrones...'  # Single quotation marks
print(got)
print("$")  # Single character

empty = ""
print(empty)  # Just prints an empty line

multiple_lines = '''Triple quotes allows
multi-line string.'''
print(multiple_lines)   # Multiple lines

        # The Length of a String
            # The length of a string can be found using the len() built in function.
random_string = "I am Batman"  # 11 characters
print(len(random_string))   # Prints the length of the string.
            # Each character is given a numerical index based on its position.
            # It is indexed from 0 to n-1 where n is its length."
        # Indexing
        # Each character in a string can be accessed using its index
batman = "Bruce Wayne"

first = batman[0]  # Accessing the first character
print(first)
                # Will output B
                # Can also reverse index using -
batman = "Bruce Wayne"
print(batman[-1])  # Corresponds to batman[10]
print(batman[-5])  # Corresponds to batman[6]

                # ASCII Versus Unicode#
                # In Python 3.x, all strings are unicode.
                # But, older versions of Python (Python 2.x) support only ASCII characters.
            # To use unicode in Python 2.x, preceding the string with a u is must.
            # For example:

string = u"This is unicode"

                # None Keyword
                # None is used to define a null value or Null object in Python.
                # It is not the same as an empty string, False, or a zero.
                # It is a data type of the class NoneType object.



# declaring a variable as None
var = None

# checking it's value
if var is None:
    print("var has a value of None")
else:
    print("var has a value")
    # This outputs "var has a value of None"

# String Slicing
    # Slicing is the process of obtaining a portion (substring) of a string by using its indices.
    # The template to slice string is sting[start:end]
    # start being the index we want the substring to start.
    # end is the index where we want our substring to end.
    # The apces in the sting count towards the index.
    # For Example:
my_string = "This is MY string!"
print(my_string[0:4]) # From the start till before the 4th index
print(my_string[1:7])
print(my_string[8:len(my_string)]) # From the 8th index till the end
        # This will print:
        # This
        # his is
        # MY string!
# Inserting Strings Within a String.
    # You can instert strings within a string.
    # Integer within a string.
    # And floats within a string.
# For example:
string1 = "I like %s" % "Python"
print(string1) # 'I like Python'

temp = "Educative"
string2 = "I like %s" % temp
print(string2)      # 'I like Educative'

string3 = "I like %s and %s" % ("Python", temp)
print(string3)      # 'I like Python and Educative'
    # The %s is a format specifier, which tells python to insert the text there.
    # We can also enter mltiple strings by putting multiple instances of %s inside out string.

my_string = "%i + %i = %i" % (1,2,3)
print(my_string) # '1 + 2 = 3'
    # The %i is the format specifier, which tells Python to insert the integers here.

string1 = "%f" % (1.11)
print(string1)      # '1.110000'

string2 = "%.2f" % (1.11)
print(string2)      # '1.11'

string3 = "%.2f" % (1.117)
print(string3)      # '1.12'
    # Specifiying %.2f limits the decimal places to 2
    # If the float is greater than two decimal places %.2f will round off the number.

# Comparisons
    # *** The result of a comparison is always a bool. ***
    # The == and != operators compare the values of both operands.
    # However, the identity operators, is and is not, check whether the two operands are the exact same object.

# Assignment Operators
    #