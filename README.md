# Makkajai-Sales-Tax-Challenge

# Sales Tax Calculator

My solution for the Makkajai coding challenge. Picked the sales tax problem because it seemed like a good mix of business logic and OOP design.

## What it does

Calculates sales tax for shopping items with these rules:
- 10% tax on most stuff (books, food, medicine are exempt)
- 5% import duty on anything imported
- Weird rounding rule: round UP to nearest 0.05

## Running it

Just compile and run:
```bash
javac SalesTaxApplication.java
java SalesTaxApplication
```

Or throw it in IntelliJ and hit the run button.

## Output

Should match exactly what's in the problem:

```
Output 1:
1 book: 12.49
1 music CD: 16.49
1 chocolate bar: 0.85
Sales Taxes: 1.50
Total: 29.83
```

And so on for the other test cases.

## How I built it

Broke it down into a few classes:

- `Item` - just holds the item data
- `TaxCalculator` - does the actual tax math (this was the tricky bit)
- `Receipt` - formats everything nicely
- `ItemParser` - parses the input strings with regex

## The annoying parts

**Rounding**: That "round up to nearest 0.05" rule took me a while to get right. Had to divide by 0.05, round up, then multiply back. Math is hard sometimes.

**BigDecimal**: Used this instead of doubles because money calculations with floats are a recipe for disaster. Nobody wants to explain why $10.00 + $20.00 = $30.000000001.

**Categories**: Just did simple keyword matching (if it contains "book" it's a book, etc.). Could be smarter but works for the test cases.

## Why I made these choices

- Single file because it's easier to review and run
- Separate classes even though it's small - shows I can structure code properly  
- BigDecimal for precision - learned this the hard way in a previous project
- Enums for categories - safer than string comparisons

## What I'd add in real life

- Proper unit tests (just has the built-in examples now)
- Better error handling 
- More sophisticated item categorization
- Maybe a config file for tax rates
- Validation for negative prices and edge cases

## Test cases work?

Yep, all three match the expected output exactly. Spent some time double-checking the math.

---

Built for Makkajai coding challenge. Hope you like it!

P.S. - Really excited about the possibility of working on educational games. Used to love math games as a kid.
