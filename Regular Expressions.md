# Regular Expressions

Regular expressions are used to help simplify code to establish a pattern. This is best practice in web development
to ensure that code is reusable at different points of your program. Ensuring this structure helps in business situations
that tend to have high turnover of developers so that a new developer can be ramped easily. Overall, this principle is a 
way to ensure effieciency whereever possible.

## Summary

The regular expression I will be dissecting below is a simple email validation function. I will describe the various elements
of the below code snippet:

function validateEmail(email) {
  const pattern = /^([a-zA-Z0-9._%+-]+)@([a-zA-Z0-9.-]+\.[a-zA-Z]{2,})$/;
  return pattern.test(email);
}

 Example usage
const email1 = "user@example.com";
const email2 = "invalid.email@.com";

console.log(`Email 1 is valid: ${validateEmail(email1)}`);
console.log(`Email 2 is valid: ${validateEmail(email2)}`);


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

The above code segment contains anchors, grouping constructs to support those anchors,
and other components within those parent elements to add to the complexity of the 
email validator.

### Anchors

example given: ([a-zA-Z0-9._%+-]+ )@ ([a-zA-Z0-9.-]+\ . [a-zA-Z]{2,})$/

This anchor is acting as an array of characters that will be apart of the validation process.
In this example, the anchor is validating any of these characters as part of a valid username and domain.

### Quantifiers

There are a variety of quantifiers in the above code. There functions are to set the conditions based on the 
anchor. for example, the first string, ([a-zA-Z0-9._%+-]+ ), has a + quantifier on the end of it. This is telling the 
function that of these characters established, there needs to be at least one character used from the established
set of characters. Another example would be the quantifier in: [a-zA-Z]{2,}. This one is going to authenticate that there must be two
alphabetic characters in the TLD (i.e. .com, .eu).

### Grouping Constructs

In theory, the purpose of grouping contracts is to build an array of values from the defined anchor, and then utilize its quantifier to
apply its contained logic to the anchor. In the example given, the + sign is one construct. The other construct would be the expression {2,}
telling the email verication function that there needs to be two characters in the TLD.

### Bracket Expressions

We have explored the grouping of the anchors and quantifiers. They make up the constructs. That is the exterior of the car in this case. When you
look under the hood, you see that everything is driven by the bracket expressions contained within the Constructs themselves. the bracket expressions 
hold character classes, which in this case allow you to apply rules to the local part, domain part, and top level domain of the email addresses, seperately.

### Character Classes

Character classes are going to be the values that are held within the bracket expressions. They are what make up the constructs them selves. Their direct 
parent being the bracket expression that they are held within. Each bracket expression will be its own character class. 

### The OR Operator

The OR operator is usually denoted by the | symbol. In this case, there are two instances of the combination of two characters acting in the same way.

The first block of code that shows this is the first grouping construct. The + sign outside of the bracket expression, tells this function that as it goes through 
the named quantifiers, any values that fall within the constraints can be used, not just the ones named. A traversal through the values, if you will.

The second example falls between the domain and tld objects. The \ symbol tells the expressions outside of them that both parameters need to be met that this symbol
is in between for a valid email to be recognized.


## Author

Tyler Stubbs is currently a edX bootcamp student at the time of writing this. He works full time as a Solution Consultant in the AP Automation industry.
Upon finishing the program in January, he plans to continue to apply his learnings in the current career path he is in as he takes more time to master the
discipline of web development. 

[github](https://github.com/zxncho)
