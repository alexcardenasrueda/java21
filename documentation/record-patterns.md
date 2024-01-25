# Record Patterns

## Context
Enhance the Java programming language with record patterns to deconstruct record values. 
Record patterns and type patterns can be nested to enable a powerful, declarative, and composable 
form of data navigation and processing.

So far, pattern matching in Java is mainly restricted to matching types:

```
// BEFORE JAVA 16
if (obj instanceof String) {
String str = (String) obj;
System.out.println(str);
}

// JAVA 16+
if (obj instanceof String str) {
System.out.println(str);
}
```
Java 21 extended the concept to be usable in switch statements and expressions:

```
// BEFORE JAVA 21
static String asStringValue(Object anyValue) {
  String result = null;

  if (anyValue instanceof String str) {
    result = str;
  } else if (anyValue instanceof BigDecimal bd) {
    result = bd.toEngineeringString();
  } else if (anyValue instance Integer i) {
    result = Integer.toString(i);
  } else {
    result = "n/a";
  }

  return result;
}

// JAVA 21+
static String asStringValue(Object anyValue) {
  return switch (anyValue) {
    case String str    -> str;
    case BigDecimal bd -> bd.toEngineeringString();
    case Integer i     -> Integer.toString(i);
    default            -> "n/a";
  };
}
```