# Ruby compact
+ number, string, boolean with implicit typing *(e.g. my_num=25)*
+ no semicolon

## Comments
One line:

    #This is a comment

Multi Line:

    =begin
    This is
    a comment
    =end

## Output
+ `puts` Output to console with CR
+ `print` Output to console without CR
+ `"This is a string with a #{variable} in it."`

## Input
+ `gets` input with CR
+ `gets.chomp` input without CR

## Assignment
+ `a=b` simple assignment
+ `a+=b` corresponds `a=a+b` 
+ `a-=b` corresponds `a=a-b` 
+ `a*=b` corresponds `a=a*b` 
+ `a/=b` corresponds `a=a/b` 

## String methods
+ `my_string.length` length of my_string
+ `my_string.reverse` reverse my_string
+ `my_string.upcase` my_string to uppercase
+ `my_string.downcase` my_string to downcase
+ `my_string.include?"search_string"` check if search_string is inlcuded in my_string
+ `my_string.gsub(/old_string/ "new_string")` substitute old_string with new_sring in my_string
+ `my_string.split("split_string")` splits my_string based on split_string. returns array
+ apply method result to invoke string via `!` after method name (e.g. `my_string.downcase!`)

## Control flow
+ `if [expr] - elsif - else - end`
+ `unless [expr] - else - end`
+ `while [expr] do - end`
+ `until [expr] do - end`
+ `for x in n..m - next if [expr] - end` (m included)
+ `for x in n...m - next if [expr] - end` (m not included)
+ `loop do - next if [expr] - break if [expr] - end`
+ `x.times {[code]}` repeat [code] x times

## Comparison operators
`==` `!=` `<` `<=` `>` `>=`

## Boolean operators
`&&` `||` `!`

## Arrays
+ `my_array=[1,2,3,4,5]`
+ `my_array.each do |x| - end`
+ `my_array.each  {|x| [code]}`
+ access by index `my_aray[x]`

## Hash
+ `my_hash = { key1=>value1, key2=>value2,key3=>value3}`
+ `my_hash= Hash.new` (empty hash)
+ `my_hash[key]=value` add/update key/value
+ `my_hash.each {|k,v| [code]}`