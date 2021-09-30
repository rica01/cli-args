# cli-args
Java Command Line Argument Parser by JJenkov.

A command line argument parser implemented in Java. Use it to parse command line arguments passed to the main method
of your Java application. Read how it works here:

http://tutorials.jenkov.com/java-howto/java-command-line-argument-parser.html

## Note
I forked this so I could make a stand-alone source code of it. No jar, no libs, no nothing. Get the .java, put it in your project, Start using!

## MWE
Demo.java:
```
public class Demo {

    public static void main(String[] argv) {

        CliArgs cliArgs = new CliArgs(argv);

        double A = cliArgs.switchDoubleValue("-A");
        double B = cliArgs.switchDoubleValue("-B");
        String Op = cliArgs.switchValue("-Op");
        
        double result = 0.0;
        switch(Op)
        {
            case "+":
                result = A + B;
                break;
            case "/":
                result = A / B;
                break;
        }

        System.out.println(result);
    }
}
```


Compiling with:
```
javac Demo.java
```

Run with:
```
java Demo -A 10 -Op + -B 20
```

Output:
```
30.0
```

