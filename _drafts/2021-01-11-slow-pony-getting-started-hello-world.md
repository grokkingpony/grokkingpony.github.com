It's traditional, after installing a new language, to test out your tool chain by writing and running a "Hello World!" program.  Pony is no exception. 

# Create a project directory
We start by creating a place to put our Pony program.  Unline in most other languages, the name of this directory matters because it's what your program will be called.

    $ mkdir projects
    $ cd projects
    $ mkdir helloworld
    $ cd helloworld

# Write and run a Pony program
Next we need a file to put our Pony code into Pony source files always have a ```.pony``` extension. All Pony programs must have a ```main``` file which is what we'll call our file, so go ahead, open your editor of choice, and create a file called ```main.pony``` in your new ```helloworld``` directory.

Then you can type in (or copy and paste) the following code listing:

    actor Main
      new create(env: Env) =>
        env.out.print("Hello, world!")
        
Save the file, and go back to your terminal window. On MacOs and Linux, enter the following command to compile and run your first program:

    $ ponyc
    $ ./helloworld
    Hello, world!
    
Regardless of Operating System differences (I've only shown the Mac bits as thats my platform) you'll see the ```Hello, world!``` printed.  If you don't, check your code, check the compilation worked properly (I haven't shown the compilation output) and if it still doesn't work head back to the [previous post]() and check everything you need installed correctly.

# Anatomy of a Pony program
Lets take a look at what happened in our small first program. There's a lot we need just to priint this message.

The first piece is the first line:

    actor Main
    
This line defines your first ```Actor``` in Pony.  Actors are a big deal in Pony. They are a bit like classes in other languages, but they have other special features which make distributed and multi-threaded programming a _lot_ easier.

The ```Main``` actor is special. Just like other programming languages with their ```main()``` functions, the ```Main``` actor is where a program starts.

You might also notice that we _don't_ have curly braces. Neither do we have semi-colons. Indentation is also convention and signifies nothing to the compiler. (We could have this code on a single line and it would compile and run.)

The next line declares a constructor function (but not it's body which comes next) for our Actor:

    new create(env: Env) => 
    
The fact it's a constructor is revealed by the ```new``` keyword and the name of this constructor function is ```create```. When it's called it creates a new instance of the ```Main``` actor.  For the construction we are passing in a single parameter called ```env``` of type ```Env```, where ```env``` represents the environment where the program is running, and lets us interact with it, for example by printing things to ```sdtout```.

The final line takes this ```env``` and does something with it.  It's the exciting (and non-boiler-plate) part of your program:

    env.out.print("Hello, world!")
   
This line starts with our reference ```env``` to an instance of ```Env```. The dot-notation here indicates two things. The first dot is us accessing a field, ``out``, on ```env```. The second dot is a function call; we're calling the method ```print()``` on the ```out``` field, and passing a String parameter. (The message that we want printed to *stdout*.)

# What happens when we compile?
You’ve just run a newly created program, so let’s examine each step in the process.

Before running a Pony program, you must compile it using the Pony compiler by entering the ```ponyc``` command in your project directory:

    $ ponyc
    
Note, you _don't_ need to specify your Pony source code file, ```main.pony```.  This is because this is the default name for Pony code which contains the required ```Main``` actor.

If you have a C or C++ background, you’ll notice that this is similar to ```gcc``` or ```clang```. What ```ponyc``` has done is built the current directory, ```.```, plus the stuff that is built into Pony, ```builtin```, it generated some code, optimised it, created an object file (don’t worry if you don’t know what that is), and linked it into an executable with whatever libraries were needed. 

Wait, it linked too? Yes. You won’t need a build system (like make) for Pony. It handles all this for you.

Then you have a self-contained, platform-specific binary; ```helloworld```; which contains your program and everything it needs to run. 
