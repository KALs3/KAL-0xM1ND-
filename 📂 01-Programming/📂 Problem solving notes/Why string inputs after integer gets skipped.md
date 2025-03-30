when taking in a string after an it or double you should use the scan.nextLine() method so you could why ?

This is a common problem, and it happens because the [`nextInt`](http://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextInt\(\)) method doesn't read the newline character of your input, so when you issue the command [`nextLine`](http://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextLine\(\)), the Scanner finds the newline character and gives you that as a line.

A workaround could be this one:

```java
System.out.println("Enter id");
id1 = in.nextInt();

in.nextLine();   // skip the newline character

System.out.println("Enter name");
name1 = in.nextLine();
```

Another way would be to always use [`nextLine`](http://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextLine\(\)) wrapped into a `Integer.parseInt`:

```java
int id1;
try {
    System.out.println("Enter id");
    id1 = Integer.parseInt(input.nextLine());
} catch (NumberFormatException e) {
    e.printStackTrace();
}
System.out.println("Enter name");
name1 = in.nextLine();
```

### Why not just `Scanner.next()` ?

I would not use [`Scanner.next()`](http://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextInt\(\)) because this will read only the next token and not the full line. For example the following code:

```java
System.out("Enter name: ");
String name = in.next();
System.out(name);
```

will produce:

```java
Enter name: Mad Scientist
Mad
```

It will not process _Scientist_ because _Mad_ is already a completed token per se. So maybe this is the expected behavior for your application, but it has a different semantic from the code you posted in the question.

