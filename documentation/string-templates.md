# String templates

## Context

Enhance the Java programming language with string templates. String templates complement Java's 
existing string literals and text blocks by coupling literal text with embedded expressions and 
template processors to produce specialized results. This is a preview language feature and API.

### Interpolation vs Templates
Interpolation of string has some problems ... ${name}

Template
```
String name = "Alex";
String info = STR."My name is \{name}";
```

When
STR = Template

name = value to evaluate

Change way to define variables


### Multi-line String templates
```
String title = "Example title";
String text = "News Java21"
String html = STR."""
    <html>
        <head>
            <title> \{title}</title>
        </head>
        <body>
            <p> \{text}</p>
        </body>
    </html>
"""; 
```
