##Float and Double
You've already learned about the String and Int types; Strings are values like "hello" or "eat your vegetables", and Ints are whole number values like 34 and 9561.  

Strings may form the backbone of displaying instructions and values to the user, but numbers (and especially mathematical operations on those numbers) are necessary for actually drawing that text to the screen, as well as pretty much every thing the operating system and your applications do, from computing how many days are left in a subscripton to centering a button in window.  

Another kind of number are Float and Double, which represent decimal values such as 0.5 or 3.14159.  The difference between Float and Double is magnitude and precision: Floats are represented in 32 bits and Doubles are represented in 64 bits, so Doubles have the potential for greater magnitude and precision.

You can recognize Floats and Doubles by value because they will have a decimal point; the Swift compiler will interpret any number with a decimal point as a Double unless you specify that it should be recognized as a Float.  Any number without a decimal point will be interpreted by the compiler as an Int.

##Mathematical Operations
The four primary operators in math are addition (+), subtraction (-), multiplication (*), and division (/); the fifth operator is remainder (%).  For example:

```Swift
5 / 3 = 1
5 % 3 = 2
````
 
 Similarly, you can assign Int and Float values to variables and perform math operations.  For example:

 ```Swift
 let a = 4
 let b = 12
 let n = b / a   (3)
 let r = b % a   (0)
 let product = a * b   (48)
 let sum = a + b   (16)
 let difference = b - a   (8)
 ````

 and using Floats...  (because there's a decimal the compiler knows it's a Float)

````Swift
 let x = 5.5
 let y = 10.0
 let n = y / x  (1.8181...)
 let r = y % x   (4.5)
 let proudct = x * y   (55)
 let sum = x + y  (15.5)
 let difference = y - x  (4.5)
 ````
 
 So far this should all remind you of your days back in math class with Mr. Mcgregor.  There is, however, something that you may find surprising about how Swift handles math.
 
 What if we multiply an Int and Float, like a * x as shown above?  Well, the compiler gives us an error which seems very unfriendly!  Why is that?
 
Remember that one of the key features of Swift is that it's a type-safe language; that means its very, very particular about what kind of types it expects in any given situation and will unceremoniously give you an error whenever you provide it a type it doesn't like.

In Mathematical operations Swift only lets you use values of the same type because (as we've learned over the past several decades with langauges which "helpfully" convert and combine types for us) mixing types can lead to unexpected results such as loss of precision.

If you want to mix types in mathematical expressions you must tell Swift explicitly what you want to convert.
 
````Swift
 let sum = a + Int(x)    (9)
 let sum = Double(a) + x   (9.5)
 ````
 
 You can easily explore and experiment with mathetimatical operations in a Playground.
 
 
##Functions
 Functions, as mentioned in an earlier unit, are the primary means of reducing complexity and making programs easier to read.  Instead of having hundreds or thousands (or tens of thousands) of lines of code, you can break that up in functions to make you code easier to understand.  Some functions are just a single line and others are hundreds of lines of code but a good rule of thumb is that a function should be between 10 and 100 lines of code; fewer lines of code than that and creating the function may not be worth the trouble, and more lines of code than that means you probably have more complexity than you want and should probably break that function into two or more functions if possible.
 
 Most functions return some kind of value; either something which is retrieved, computed, or just a code indicating success or failure.  For example, here's a function which returns the average of two Doubles:

````Swift
 func average(a:Double, b:Double, c:Double) -> Double {
 	return ( a + b + c ) / 3.0
 	}
 	````
 	
 You can also have a function which returns the average of three Ints:

````Swift
 	 func average(a:Double, b:Double, c:Double) -> Double {
 	return ( a + b + c ) / 3.0
 	}
 	````
 	
It's also perfectly OK to have a function which doesn't take any arguments or return any value:
 
````Swift
 	func sayHello() {
 		print("Hello")
 	}
````

##Summary
In addition to Ints, which are whole numbers, we also have Floats and Doubles which are used to represent decimal values.  We have built-in mathematic operators for addition (+), subtraction (-), multipilcation (*), division (/) and remainder (%).

Swift is type-safe and only allows mathematical operators to be used on the same types (Int and Int, Long and Long, Float and Float, Double and Double) ; if you want to perform math on two different types you must either cast one to the type of the other (e.g. 3.0 * Double(4)) or cast them both to some other type (e.g.	  Double(5) * Double(13) ).

Functions are the primary way of reducing and managing complexity in your application code.  Functions can take one parameter, multiple parameters, or no paramters, and can return a single value or no value.

 	
 
