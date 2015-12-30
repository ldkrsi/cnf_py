# Conversion into CNF

Use python and regular expression

## What is CNF(Conjunctive Normal Form)?

## 

[Conjunctive normal form - Wikipedia](https://en.wikipedia.org/wiki/Conjunctive_normal_form)

## Conversion step

1.  Add brackets to match order of precedence
2.  Convert "if only if" into "implies"
3.  Replace "implies" by "and", "or", "not"
4.  Doing de morgan
5.  Doing distributive

## Input format

### Operator

*   neg .... "Negation"
*   and
*   or
*   imp ..... "implies"
*   iff ..... "if only if"
*   ()

### Symbol

Any word character but non-digit.  
ex.  
A and AA ....... ok  
A1 and B ....... not ok  

## Usage

input and output path write in

<pre>if __name__ == "__main__":
    ...
</pre>

### run

<pre>python run.py
</pre>

## Sample

After ....

<pre>python run.py
</pre>

output.txt is

<pre>((A imp C) and (C imp A)) or B
((neg A or C) and (neg C or A)) or B
((neg A or C) and (neg C or A)) or B
(A or B or neg C) and (B or C or neg A)
</pre>

## Issue

when input is

<pre>(A and neg A) or B
</pre>

the output was

<pre>(A or B) and (neg A or B)
</pre>

but it should be

<pre>B
</pre>