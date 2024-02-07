   <h1 class="title",font-size:40px;align="center">Regular expressions </h1>
 
# Regex 
- The pattern is same but implementtion many diffrent on prgraming languages 
- on python 

        import re
        a = re.("PATTERN","SERACHING FILE").group(0)
        # Regex on python
        print(a)

# Metacharacters
-  . ^ $ * {}  ? + [] () \  |
### A. Dot(.)
- used for to get all the line except new lines 
- It can give all lines except new lines like jumped lines 
### B. Caret(^) 
- Used to get line that start with pattern 
- syntax ``^Hello`` it filters one  of words start with hello lines 
### C. Dollar($)
- Used for filter that the end with some patterns
- Syntax ``hello$`` It can filter some pattern end with hello
### D. Plus(+)
- Used for filter some pattern that occours 1 and more times 
- Syntax ``^hello+`` It filters start from hello and it occurs end one and more times 
### E. Astriks(*)
- Used for get line have patterns occurs zero and more times 
- Syntax ``^hellos*`` It used start with hellos and filter the patterns have occurs zero times and more than
- It can filter ```hello ,hellos,helloss```
### F. Question Mark(?)
- It used for get lines have patterns occurs 0 and 1 times li
- Syntax ``^hellos?``It can only filters hello and hellos cuze it ocurrs 1 and 0
### G. Curly Bracket ({min,max})
- Used to get lines have pattern occurs min and max times 
- Syntax ``hellos{1,3}`` It filter Minmum 1 times courrs "hellos" and Maximum 3 times that occurs  "hellosss"
### H. \w
- It used for get all Alphanumeric data except new lines 
- Syntax ``\w``
### I. \W

- Used to get all except alphanumeric
- Syntax ``\W``
### J. \s
- used to get whitspace 
- Syntax ``\s``
### K. \S
- Used for get all except whitespace
- Syntax ``\S``
### L. \d
- used for get Digits/Numbers
- Syntax ``\d``
### M. \D 
- used for get all except numbers/digits 
- Syntax ``\D``
### N. pip(|) Or
- Used for search two diffrent things like a|b it it used for search all of a and b
-  Syntax``B|R`` this regex used for search B and R spelling / we can used word 
### O. Escape(\)
- Used for search symbols that are Metacaracters
- Syntax ``\``
### P. Square Brackets([])
- Used for creat your own pattern 
- Syntax ``[A-Z]``
## Bash for Regex
- **If you went to use regx in bash you can use thier own patterns**
- when we use regex we must use tilda (~) use =~ 

          read -p "Enter ypur number" num
          patter="[0-9]"
          if [[ $num =~ ${pattern} ]]
          then
          echo "You inserted number is ${num}"
          else
          echo "Please enter Number only"

