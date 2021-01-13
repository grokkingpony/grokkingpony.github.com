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
    


# Anatomy of a Pony program

# Compiling and running
