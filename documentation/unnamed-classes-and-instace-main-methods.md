# Unnamed classes and instance main methods

## Context

Evolve the Java language so that students can write their first programs without needing to 
understand language features designed for large programs. Far from using a separate dialect of Java,
students can write streamlined declarations for single-class programs and then seamlessly expand their 
programs to use more advanced features as their skills grow. This is a preview language feature.

Consider the classic Hello, World! program that is often used as the first program for Java students:

```
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
There is too much clutter here — too much code, too many concepts, too many constructs — for what the program does.

First, we enhance the protocol by which Java programs are launched to allow instance main methods. Such methods are not static, need not be public, and need not have a String[] parameter. Then we can simplify the Hello, World! program to:
```
class HelloWorld {
    void main() {
        System.out.println("Hello, World!");
    }
}
```
Second, we introduce unnamed classes to make the class declaration implicit:
```
void main() {
    System.out.println("Hello, World!");
}
```