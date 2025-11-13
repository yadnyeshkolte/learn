---
layout: default
title: Scripting
parent: Linux
nav_order: 2
---

# Scripting Concepts

**Exit and Break Difference**
- `exit` - Terminates the entire script (and returns control to the shell)
- `break` - Exits only the current loop and continues executing any code after the loop

**This is about understanding the different types of conditional operators in Bash. Let me explain why `(( ))` and `[[ ]]` work in different contexts:**

## The Key Difference

### `(( ))` - Arithmetic Evaluation
- **Purpose**: Performs **arithmetic/mathematical** operations
- **Works with**: Numbers and arithmetic expressions
- **Does NOT work with**: String comparisons

### `[[ ]]` - Conditional Expression
- **Purpose**: Performs **conditional tests** (strings, files, patterns)
- **Works with**: String comparisons, pattern matching, file tests
- **Does NOT work with**: Arithmetic expressions (without `$`)

---

## Detailed Explanation with Examples

### Example 1: Why `(( ))` works for numbers

```bash
#!/bin/bash

num=5
i=3

# ✅ WORKS - (( )) is designed for arithmetic
if (( i != num ))
then 
    echo "Numbers are different"
fi

# ✅ ALSO WORKS - [[ ]] with arithmetic operators
if [[ $i -ne $num ]]
then
    echo "Numbers are different"
fi

# ❌ FAILS - [[ ]] with (( )) style operators
if [[ i != num ]]  # This compares strings "i" and "num", not their values!
then
    echo "This treats i and num as strings"
fi
```

### Example 2: Why `[[ ]]` works for strings

```bash
#!/bin/bash

dir_name="mydir"
folder="mydir"

# ✅ WORKS - [[ ]] is designed for string comparison
if [[ "$dir_name" == "$folder" ]]
then
    echo "Strings match"
fi

# ❌ FAILS - (( )) cannot compare strings
if (( dir_name == folder ))  # Error! Treats them as variables with value 0
then
    echo "This will fail or give unexpected results"
fi
```

---

## Complete Comparison Table

```bash
#!/bin/bash

num1=10
num2=20
str1="hello"
str2="world"

echo "========================================="
echo "ARITHMETIC COMPARISONS (Numbers)"
echo "========================================="

# ✅ Method 1: Using (( )) - MODERN & RECOMMENDED
if (( num1 < num2 ))
then
    echo "(( )): $num1 is less than $num2"
fi

if (( num1 != num2 ))
then
    echo "(( )): $num1 is not equal to $num2"
fi

# ✅ Method 2: Using [[ ]] with -eq, -ne, -lt, -gt, -le, -ge
if [[ $num1 -lt $num2 ]]
then
    echo "[[ ]]: $num1 is less than $num2"
fi

if [[ $num1 -ne $num2 ]]
then
    echo "[[ ]]: $num1 is not equal to $num2"
fi

echo ""
echo "========================================="
echo "STRING COMPARISONS"
echo "========================================="

# ✅ Method 1: Using [[ ]] - RECOMMENDED for strings
if [[ "$str1" == "$str2" ]]
then
    echo "Strings are equal"
else
    echo "[[ ]]: '$str1' is NOT equal to '$str2'"
fi

if [[ "$str1" != "$str2" ]]
then
    echo "[[ ]]: Strings are different"
fi

# Pattern matching (only works with [[ ]])
if [[ "$str1" == h* ]]
then
    echo "[[ ]]: '$str1' starts with 'h'"
fi

echo ""
echo "========================================="
echo "COMMON MISTAKES"
echo "========================================="

# ❌ WRONG: Using == inside (( )) for strings
# if (( str1 == str2 ))  # This would fail!

# ❌ WRONG: Using <, >, != inside [[ ]] for numbers without $
# if [[ num1 < num2 ]]  # This compares strings "num1" and "num2"

# ✅ CORRECT: Variable expansion in [[ ]]
if [[ $num1 -lt $num2 ]]
then
    echo "Correct: Using \$num1 and -lt operator"
fi
```

---

## Quick Reference Guide

### For **ARITHMETIC** (Numbers):

| Operator | `(( ))` | `[[ ]]` | `[ ]` (old style) |
|----------|---------|---------|-------------------|
| Equal | `(( a == b ))` | `[[ $a -eq $b ]]` | `[ $a -eq $b ]` |
| Not Equal | `(( a != b ))` | `[[ $a -ne $b ]]` | `[ $a -ne $b ]` |
| Less Than | `(( a < b ))` | `[[ $a -lt $b ]]` | `[ $a -lt $b ]` |
| Greater Than | `(( a > b ))` | `[[ $a -gt $b ]]` | `[ $a -gt $b ]` |
| Less or Equal | `(( a <= b ))` | `[[ $a -le $b ]]` | `[ $a -le $b ]` |
| Greater or Equal | `(( a >= b ))` | `[[ $a -ge $b ]]` | `[ $a -ge $b ]` |

### For **STRINGS**:

| Operator | `[[ ]]` | `[ ]` (old style) |
|----------|---------|-------------------|
| Equal | `[[ "$a" == "$b" ]]` | `[ "$a" = "$b" ]` |
| Not Equal | `[[ "$a" != "$b" ]]` | `[ "$a" != "$b" ]` |
| Pattern Match | `[[ "$a" == p* ]]` | ❌ Not supported |
| Regex Match | `[[ "$a" =~ regex ]]` | ❌ Not supported |
| Empty | `[[ -z "$a" ]]` | `[ -z "$a" ]` |
| Not Empty | `[[ -n "$a" ]]` | `[ -n "$a" ]` |

---

## Practical Example - Your Code Fixed

```bash
#!/bin/bash

# Example 1: Number comparison
num=5
for i in {1..10}
do
    # ✅ CORRECT: (( )) for arithmetic
    if (( i != num ))
    then 
        echo -n "$i "
    fi
done
echo ""

# Example 2: String comparison
dir_name="myproject"
folder="myproject"

# ✅ CORRECT: [[ ]] for string comparison
if [[ "$dir_name" == "$folder" ]]
then
    echo "Found directory: $folder"
    ls -la "$folder" 2>/dev/null || echo "Directory doesn't exist"
fi

# Example 3: Mixed - both in one script
count=10
name="test"

# ✅ Arithmetic
if (( count > 5 ))
then
    echo "Count is greater than 5"
fi

# ✅ String
if [[ "$name" == "test" ]]
then
    echo "Name is test"
fi
```

---

## Why This Design?

1. **`(( ))` for numbers**: More intuitive syntax (`<`, `>`, `==`) like other programming languages
2. **`[[ ]]` for strings**: Safer string handling, pattern matching, no word splitting
3. **Separation of concerns**: Different tools for different data types

## Best Practices

✅ **DO**:
- Use `(( ))` for **all arithmetic** operations
- Use `[[ ]]` for **string comparisons** and **file tests**
- Always quote variables in `[[ ]]`: `"$var"`

❌ **DON'T**:
- Mix arithmetic operators with string comparisons
- Use `(( ))` for strings
- Forget to use `$` before variables in `[[ ]]`
