# Constantes

Ahoy! mis compañeros desarrolladores, hasta ahora ya hemos visto los tipos de datos primitivos en Go y las diferentes aplicaciones que podemos darle a las variables que tienen datos primitivos, los cuales son parte fundamental en cualquier programa creado con el lenguaje de programcion Go.

En esta seccion veremos las constantes en el lenguaje de programcion Go y las diferentes aplicaciones que podemos darles en un programa escrito con este lenguaje.

Lo mas imporante que debemos recordar, es que en Go, los valores de las constantes no pueden ser cambiados despues de su asignacion

```golang

func main() {
    const myStr string = "I AM A CONSTANT STRING"
    myStr = "I WANT TO CHANAGE MY VALUE" // If we run this code we are going to have an error
}
```

Como sabemos, en algunos lenguajes existe la convecion de nombrar a las constantes en letras mayusculas separando las palabras que forman el nombre con un guin bajo, ejemplo: MY_CONSTANT, pero, debemos recordar que al escribir una variable o en este caso una constante, en la cual su nombre inicie con mayuscula el compilador de Go la exportara fuera del paquete donde fue declarada. Por lo tanto, la convencion para escribir constantes en Go, es la misma que usamos para las variables: "camelCase"

```golang

func main() {
    const camelCase string = "I AM A CONSTANT STRING NAMED CORRECTLY"
    const CAMEL_CASE string = "BAD" // constante publica y nombrada erroneamente 
}
```


// TYPED CONSTANTS
Now assuming that we're going to be working with an internal
constant, then we're going to switch this back to a lowercase first letter. And then

let's talk about how we can create what's called a typed constant. Now a typed constant

is created very similarly to a typed variable. So we can start with the const keyword, then

the name of our constant, and then we're going to list the type of the content, and then

we can set it equal to a value, then if we want to prove that that worked out the way

we expected it to, then we can go ahead and print out the value in the type of the constant.


// INMUTABILITY
And we will do that by using this printf statement here. And then when we run this, we see that

the constant is in fact created. It's got the value 42 that we assigned, and it's got

the type that we assigned to it. Now the reason it's a constant and not a variable is it has

to remain constant. So if we tried to do something like this, change this to the value 27, then

the compiler throws an error, because we're not allowed to change the value of a constant.


// Assignation at compilation
Another characteristic of a constant is that it has to be assignable at compile time. So

for example, if I wanted to have a constant that represented the sine of pi over two,

then I might be tempted to do something like this. I'll create a float 64 constant. And

I'll set it equal to the result of the sine function from the math library. And I'll pass

in 1.57, which is approximately pi over two. And then I can run this right? Well, the problem

with that is in order to determine the sine of that value, that actually requires the

function to execute, which is not allowable at compile time. And so you can't set your

constants equal to something that has to be determined at runtime. And that includes things

like setting it equal to flags that you pass into your application, when you run, if you're

going to do that you can't use a constant to store that value. Now constants can be

made up of any of the primitive types that we talked about in the last video. So if we

have this example, here, we've got an integer constant, we've got a string constant, a floating

point constant and a Boolean constant. And if we run this, we see that all of those printout

exactly the way that we expect. We've got the integer the string, the floating point

value and the boolean value. Now in an upcoming video, we're going to talk about the collection

types and the collection types. are inherently mutable. So for example, you couldn't create

an array and declare that to be a constant type. Arrays are always going to be variable

types. Now another characteristic that constants have in common with variables is they can

be shadowed. So if we create a constant at the package level, and let's just make this

an integer 16, and set it equal to the value 27, then we'll delete these guys. And also

these guys. Now we've got a constant called a declared at the package level, that's an

integer 16. And then we got a constant in the main function, that's also called a and

it's an integer type. So if we update This printf statement to print the type of variable,

we see that the looks like I need to print my variable twice, we see that the inner declaration

of the constant wins. So not only can we change the value of the constant, but we can also

change the type because the inner constant shadows that outer constant. And we can prove

that by commenting this line out, running again. And we see that the package level constant

wins. So you want to be a little careful here, because if you're going to reuse constant,

it's going to feel like those values are changing. So I wouldn't recommend that you take advantage

of this. But if you do get into a situation where constants aren't evaluating the way

that you expect them to, this is one possible reason. Now when we're working with constants,

they work very similar to variables when we're using them in operations. So if we bring this

line back, and set it equal to 42, and then what I want to do is declare a variable. So

we'll declare a variable b as an integer, and set that equal to the value 27. And then

we can do a plus b. And let's see what happens when we do that. So if we run that, we in

fact, get the ability to add a constant to a variable, and the result is going to be

a variable. And so since the constant and the variable are of the same type, we can

perform the addition operation on there. Now, our constant is of a different type. For example,

if we made variable b in 16, and run this, then we get exactly the same failure that

we get when we try and add two variables of different types together. Now, so far, all

we've been talking about are these type constants, we're after the constant name, we list the

type. But we don't have to do that, we can use the compilers ability to infer the type

for us. So let's just go ahead and do that with this example here. When we run this,

we see that the constant a is inferred to be an integer with the value 42. Now given

that, given that the compiler is inferring the value, what do you think is going to

happen? If we do something like this, if we restore that previous example, where we're

going to add this constant to an integer 16? Well, in fact, in this case, the operation

succeeds, which might be a little bit confusing. But the reason that works is because what

the compiler is actually doing, when it sees this constant is it's basically replacing

every instance. So the way the compiler sees this program is it sees it like this. So since

we're taking a literal 42, and adding an int 16 to it, that 42 is interpreted as being

an integer 16. So the compiler doesn't say, oh, constant, a equals 42, that's an integer

and always an integer. Instead, the compiler is going to look for every time that we use

the symbol a, and it's going to replace that with the value of the constant. And so we

can do these implicit conversions when we're working with constants, which is something

that we can't really do when we're working with variables. The next thing that I want

to talk about are what are called enumerated constants. So let me go ahead and start that

conversation out by wiping out what we have here, clean up our code just a little bit.

And then I'm going to do this at the package level. Because this is where I've seen these

most commonly applied, you could do these in a function level, if that made sense in

your application. So I'm going to declare a constant a, and I'm going to have that as

an untyped constant. And I'm going to set it equal to this special symbol called Iota.

So when I run this, you see that a is evaluated to have the value zero, and it's inferred

to have the type integer. So what is Iota? Well, Iota is a counter that we can use when

we're creating what are called enumerated constants. So in this example, having an enumerated

constant isn't terribly valuable. But one of the things that I can do with constants

is I can actually work with them in a constant block like this. So when I'm doing this, I

can create another constant set that equal to Iota and another constant and set that

equal to it, let's go ahead and clean up this because we already know what the type is going

to be. So we don't need to be printing that out. And then let's print this command out

two more times, switching to B, and C. So now we're using Iota three times and when

we get the result we actually see Iota is changing its value as the constants are being

evaluated. So the first constant that's assigned has the value of zero than one and then to

know another special feature that we can take advantage of with Iota is that if we don't

assign the value of a constant after the first one, then the Pilar is going to try and infer

the pattern of assignments. So in this example, we would expect to have an error because B

and C don't have a value assigned. But since we've established a pattern for how to name

the constants in this block, when we run, we actually get the same result. And that's

because the compiler is going to apply the same formula. So it's going to apply b equals

Iota and C equals Iota for us. Now that value of Iota is scoped to that constant block.

So we create another constant block. And in this case, we create a constant called a two

and set that equal to Iota, copy this line, bring it down, and print out the value of

a two, then what we're gonna find is Iota resets to zero. So Iota is scoped to a constant

block. And what that lets you do is you can actually create related constants together,

ensure that they have different values. And then if you have another set of related constants,

you can start another constant block and ensure that they have unique values, but allow duplication

between the values in one constant block in another. So what's an example where you might

use this? Well, let me just drop in this simple application. And what we're doing here is

we're setting up a constant block, where maybe we're trying to store the specialty of veterinarians

in a veterinarian clinic so that our narine could be a cat specialist or a dog specialist,

or maybe we can take his neck specialist to. Now as you can see, inside the cost box, I'm

setting the cat specialist equal to Iota. And then in the main block, I'm creating a

variable and setting its value equal to cat specialist. So if I check to see if the specialist

type is a cat specialist, then I in fact, get the value true. Now, that works just fine.

And this also works if I, for example, use a dog specialist, assign that specialist type

to be a dog specialist run that, then that's going to work out just fine. So everything

looks really good here, right? And this is a very common use for enumerated constants.

However, one thing

that I would warn you about is what happens if I declare this variable and don't initialize

it to a type? Well, if I check to see if it's dog specialist, I get false, which makes sense.

But remember, what is the initial value of Iota? Well, the initial value of Iota equals

the zero value for an integer. And so in fact, even though we haven't specified a specialist

type, it does show up as the value can't specialist. So what do we do about this, so there's a

couple of approaches that we can take here. The first is to use the zero value of the

constant as an error value. So we can set this equal to error, then we don't need this

statement anymore. And now when we check to see if the specialist type is a cat specialist,

we get the value false because cat specialists is equivalent to the integer value one, which

is no longer the zero value of the integer. This is a very valuable approach, if you want

to check to see if a value hasn't been assigned to a constant yet, so you can specify an error

specialist. And then you can check to see if that value is set equal to the zero value

of that constant. And if it is, you can handle that error,

because

presumably, you expect that to be initialized in some way. Now, if your application guards

against that, and there's no reasonable way for this to happen, then you can take advantage

of this underscore symbol, which is goes one and only write only variable. Now what's the

value of a write only variable? Well, with Iota, we have to have a zero value, we always

have to start with zero. But if we don't care about zero, then we don't have any reason

to assign the memory to it. So we can use this underscore symbol. And we'll see this

in quite a few places in our go applications. And basically, what that tells the compiler

is yes, I know you're going to generate a value here, but I don't care what it is go

ahead and throw that away. So if we run our application, again, everything works just

fine. But in this case, we can't actually get at the zero value of this constant block.

Now the ability to create it lists of enumerated constants with a Oda is very valuable. But

things don't actually stop there. And the reason is, remember, the value of a constant

has to be able to be determined at compile time, but there are some operations that go

is going to allow us to do for example, we can do addition. So if we do this and run,

then we get false again. But what happens if we print out the value of kept specialist

if we do that, and we're going to have to remove this line, then in fact, that expression

got evaluated. So the first line line eight is evaluated to Iota plus five, which is zero

plus five, the next line cat specialist, Iota increments, and the formula repeats. So cat

specialist is equal to the value six, dog specialist is seven, and snake specialist

is eight. So this can be valuable if you need some kind of a fixed offset. Now a common

use case for this is to use the bit shifting operators because anything that we can apply

to our primitive type, we can apply here as long as it's not a function expression. So

we can do addition, subtraction, multiplication and division, we can do remainder operations,

we can do the bitwise operations. And we can do bit shifting, which is one of the more

interesting use cases that we can take advantage of. And the reason is because we don't have

the ability to raise two powers because raising two powers and go is a function in the math

package. So we can't do that in our constant evaluations. But by bit shifting, we can raise

things to the power of two, because every time you shift the number one level, you're

actually multiplying it by two. So we have this example here. And I actually stole this

from the effect of go article on golang.org. So what we have here is we have an example

of a constant block that's giving you constants that are equivalent to kilobyte, megabyte,

gigabyte, terabyte, petabyte, and so on. So down here, in our main program, what I've

done is initialize the file size to some arbitrary value. And then I've got this printf statement.

And this is basically going to format a result to print two decimal places, and then the

literal string GB afterward. So this string here is basically saying I'm expecting to

format a floating point number, and I'm going to give it two decimal places, this GB is

a literal GB, that's going to be printed in the result. And then we've got the value that's

going to be used to fill this in. And that's going to be file size divided by the GB constant.

Now you notice this constant block is set equal to one, and then we're going to bit

shift that value 10 times Iota. So the first time we're going to bit shift 10 times one,

so we're basically going to multiply this by two to the 10th. And then we're going to

multiply by two to the hundreds for the megabyte, and then two to the 1004, gigabyte, and so

on. So when we run this, we get a really convenient way to format an arbitrary file size into

a human readable format. And in the effective go article, it actually shows you how to put

a switch block, which we haven't talked about. So you can make a decision about which constant

you're going to use based on the size of the incoming value. So here, we get this nice

way to format this relatively difficult number to read to be the very easily read 3.73 gigabytes.

Now another thing that can be very valuable to do is using bit shifting in order to set

Boolean flags inside of a single byte. So if I paste this example in, we can see an

example of that. So let's just say that we've got an application and that application has

users and those users have certain roles. So inside of this constant block, here, I'm

defining various roles that we can have. So for example, you might be an admin, you might

be at the headquarters or out in the field somewhere, you might be able to see the financials

or see the monetary values. And then there may be some regional roles. So can you see

properties in Africa, can you see properties in Asia, Europe, North America, or South America.

So in order to define these constants, what I'm doing is I'm setting the value to one

bit shifted biota. So the first constant is admin is one bit shifted zero places, so it's

a literal one, the second one is one bit shifted one place, that's two, and then four, and

then eight, and then 16, and so on.

So what I have is each one of these constants is going to occupy one location in a byte.

So down here in the main program, I'm defining the roles in a single byte. And I'm oaring

together is admin can see financials and can see Europe now if you remember, oaring, is

going to be set to true if one of the values is true, or the other one. So his admin has

the binary representation of 0000001. I think that's enough zeros, seven zeros, followed

by one can see financials is going to end up with 100, can see Europe is going to end

up with the value 100000. And so when we order those all together, we're going to get this

byte that has these three flags set to true. So when we run this, we see that we've encoded

eight access roles for user into a single byte of data. So we're able to store this

information extremely efficiently. So if I want to see for example, if this user is an

admin, I can go ahead and print his admin, and then print out the value. And then in

order to determine if that's valid or not, then I can do a little bit of bitwise mathematics

here. So I can take the constant is admin, and that with the roles, and what that's going

to do is that's going to apply what's called a bit mask. So only the bits that are set

in the is admin constant, and our roles are going to be left as true, which means if we're

an admin, we're going to have the value one set at that first bit. And then I can compare

that to the is admin constant. So when I run this, if we have the admin role, then we're

going to get the value true. Now, if I check something that I don't have the role, so let

me go ahead and copy this down. And then let's just see if they're at the headquarters, so

we'll put that in here. And it's exactly the same bitwise operations, we're just changing

our mask. If we run this, we see that is headquarters equals false Actually, let me put in my Line

return here, and then run this again. And you see that is headquarters equals false.

So we can very quickly and very efficiently store a lot of different information about

what roles and access rights a user might have, and a simple byte. And having this constant

defined with a numeration expression makes it really fast and really efficient and really

clear in our application. Okay, so let's go into a summary and review what we've talked

about in this video. constants are another one of those foundational elements, that is

going to be a part of almost every application you're going to write. Now, the first thing

that we learned about with constants is that they're immutable, but they can be shadowed.

So we can create a constant, we cannot assign a new value to it. But if we create a constant

on an inner scope from an existing constant, then not only can we change the value, but

we can even change the type, because that inner scope is going to shadow the outer scope

constant, they have to be replaceable by the compiler at compile time, so the value must

be calculable. So we're not gonna be able to access functions or command line arguments

in order to determine the value of the constants in our application. But we are going to be

able to do simple expressions like we talked about in the enumeration section. They're

named like variables. So if you want to export the value of the constant outside of your

package, then you're going to use Pascal casing. And if you want to leave it as an internal

value to the package, then you're going to use camel casing to name that constant. Type

constants work just like immutable variables. So you can use them in arithmetic operations,

you can pass them into functions, but they can only interoperate with the same type untyped

constants have a little bit more flexibility. So they work just like the literals. So if

you replace that constant throughout your application with the literal value of that

constant, that's how it's going to work. So that's going to allow us to interoperate with

similar types. So we had the value 42 defined as an untyped constant. And we could add that

to an integer 16, we could add that to an integer, we can add that to a un 16. Any of

those would work, because the literal 42 will work in all of those cases. Then we talk about

the enumeration types that we can work with. And we learned about the special symbol Iota.

That allows us to start with as values zero and increments one time every time we use

it inside the same const block. Now the one thing that we have to watch out for is that

constant values that match the zero values of variables can cause subtle bugs in your

application, because you might have logic that you expect it to initialize the value

of the constant. And if something happens and then initialization doesn't occur, then

you're going to be working with zero value, which might give you a false match to a constant

that you're evaluating

against. Using that Iota operator, we can actually create what are called enumeration

expressions. So we can define the value of the constant dynamically by combining Iota

with any arithmetic bitwise operation, or bit shifting operation that's allowable with

the primitive type that the constant and representing, I want to talk about the first two collection