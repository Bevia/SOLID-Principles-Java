# SOLID-Principles-Java

LISKOV principle

```
public class Main {

    public static void main(String[] args) {
        /*The Liskov Principle is summarizes by Robert C. Martin like so:
         Subtypes must be substitutable for their base types.

         Lets say ClassA is my base type and ClassB is my subtype in this example!

         Substitutability is a principle in object-oriented programming introduced
         by Barbara Liskov in a 1987 conference keynote stating that...

         ...if classB is a subclass of classA, then wherever A is expected, B can be used instead
         because B is going to contain all of A + more of its own stuff (extends)! */

        //ClassA a = new ClassA();
        ClassA a = new ClassB();
        a.superMethod(new ClassB());
        a.superPrint();

        //Belongs to classB only
        ClassB a_ = new ClassB();
        a_.myMethod();

    }
}

class ClassA {

    public void superMethod(Object o) {
        if (o instanceof ClassB) {
            ((ClassB) o).superMethod();
        }
    }

    public void superPrint() {
        System.out.println("superclass");
    }
}

class ClassB extends ClassA {

    public void superMethod() {
        System.out.println("object class B");
    }

    public void myMethod() {
        System.out.println("this belong to classB alone!");
    }

}
```
