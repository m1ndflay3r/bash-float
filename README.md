<h4>Introduction</h4>
-----------------------------------------------------------------------------------------------------------------------------------------------------------

This is my floating point arithmetic library for bash. While functional, it is slow as all bloody blue hell - especially on division. You won't feel that slowness too much with smaller numbers, but on larger numbers you'll see what I mean. It's also uncommented spaghetti noodle code (coincidentally totalling 666 lines, counting whitespaces), held together via a delicate balance of popsicle sticks, duct tape, and prayers (to Brian Fox, that he might find humour in my folly and decide to allow this into being).

Seriously - if you're at the point of needing this library, you should probably just switch to another programming language. Bash was never meant to be used this way, and I am a madwoman for having created this. 


If you choose not to heed this warning, then continue reading below for instructions. May Brian Fox have mercy on your unfortunate soul.
<h4>Instructions</h4>
-----------------------------------------------------------------------------------------------------------------------------------------------------------

<h5>Step 1:</h5>

Pray to whatever it is you believe in for mercy, for bash will show none.

<h5>Step 2:</h5>

Clone this repository

   ``` git clone https://github.com/m1ndflay3r/bash-float ```

<h5>Step 3:</h5>

That's it. The library is located in lib/libfloat within the root directory of this repository. Source it in bash to use, like so:

   ``` source /path/to/repo/lib/libfloat ```
<h4>Usage</h4>
-----------------------------------------------------------------------------------------------------------------------------------------------------------

This library contains the following functions:

   ``` gth value1 value2   -   Greater than. Returns 0 if value is greater, 1 if it's less than, and 2 if it's equal to. ```

   ``` lth value1 value2   -   Less than. Basically just runs gth and inverts the return codes. ```

   ``` eql value1 value2   -   Equal to. Runs gth, returning 0 if gth returns 2 and 1 otherwise. ```

   ``` geq value1 value2   -   Greater or equal to. Returns 0 if either gth or eql return 0, and 1 otherwise. ```

   ``` leq value1 value2   -   Less than or equal to. Returns 0 if either lth or eql return 0, and 1 otherwise. ```

   ``` add value1 value2   -   Adds two values together, and stores the result under the variable RETURN. ```

   ``` sub value1 value2   -   Subtracts value2 from value1, and stores the result under the variable RETURN. ```

   ``` mul value1 value2   -   Multiplies two values together, and stores the result under the variable RETURN. ```

   ``` div value1 value2   -   Divides value2 into value1, and stores the result under the variable RETURN. ```

As you've probably gathered, all return values for add, sub, mul, and div are stored under the variable **RETURN** as bash doesn't let you use return for anything besides execution result codes (thanks, Brian). 
<h4>Extra</h4>
-----------------------------------------------------------------------------------------------------------------------------------------------------------

You can test this library using the proof-of-concept application **floater** found within the root of the cloned repository, which is basically just a wrapper that executes a function in the library and spits out the result.

   ``` ./floater -a val1 val2       # add ```
   
   ``` ./floater -s val1 val2       # sub ```
   
   ``` ./floater -m val1 val2       # mul ```
   
   ``` ./floater -d val1 val2       # div ```
   
   ``` ./floater -gth val1 val2     # gth ```
   
   ``` ./floater -lth val1 val2     # lth ```
   
   ``` ./floater -eql val1 val2     # eql ```
   
   ``` ./floater -geq val1 val2     # geq ```
   
   ``` ./floater -leq val1 val2     # leq ```
