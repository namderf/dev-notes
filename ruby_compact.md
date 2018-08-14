# Ruby compact
+ number, string, boolean with implicit typing (e.g. `my_num=25`)
+ 'nil' null value
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

+ `a||=b` Conditional Assignment. Assigns b to a only if a is nil

## String methods
+ `my_string.length` length of my_string
+ `my_string.reverse` reverse my_string
+ `my_string.upcase` my_string to uppercase
+ `my_string.downcase` my_string to downcase
+ `my_string.include?"search_string"` check if search_string is inlcuded in my_string
+ `my_string.gsub(/old_string/ "new_string")` substitute old_string with new_sring in my_string
+ `my_string.split("split_string")` splits my_string based on split_string. returns array
+ apply method result to invoke string via `!` after method name (e.g. `my_string.downcase!`)
+ `"Combined " << "String"` or `"Combined " + "String"` String interpolation 

## Data type conversion
+ `my_number.to_s` returns string represaentation of my_number
+ `(1..10).to_a` returns array with values 1 to 10
+ `"symbol".to_sym` or `"symbol".intern` returns :symbol

## Control flow
+ `if [expr] - elsif - else - end`
+ `unless [expr] - else - end`
+ `while [expr] do - end`
+ `until [expr] do - end`
+ `for x in n..m - next if [expr] - end` (m included)
+ `for x in n...m - next if [expr] - end` (m not included)
+ `loop do - next if [expr] - break if [expr] - end`
+ `x.times {[code]}` repeat [code] x times
+ `1.upto(10) {|num| [code]}` iterates from 1 to 10 and execudes code
+ `10.downto(1) {|num| [code]}` same thing with decending iterator

Case Statement:

    case variable
      when value1
        [code]
      when value2
        [code]
      else
        [code]
    end

or

    case variable
      when value1 then [code]
      when value2 then [code]
      else [code]
    end

## Simple if/unless

`expression if boolean`

`expression unless boolean`

`boolean ? expresion_if_true : expression_if_false`


## Comparison operators
`==` `!=` `<` `<=` `>` `>=` (self explanatory)

Combined Comparison Operator `<=>`:

+ returns 0 if both operands are equal
+ returns 1 if first operand is greater than second
+ returns -1 if first operand is less than second

## Boolean operators
`&&` `||` `!`

## Arrays
+ `my_array=[1,2,3,4,5]`
+ `my_array.each do |x| - end`
+ `my_array.each  {|x| [code]}`
+ access by index `my_aray[x]`
+ `my_array.reverse` 
+ `my_array.sort` sort array in ascending order (per default)
+ `my_array.sort { |firstElement, secondElement| firstElement <=> secondElement}` sort array in ascending order (explicit)
+ `my_array.sort { |firstElement, secondElement| secondElement <=> firstElement}` sort array in descending order (explicit)
+ `my_array.push(value)` add value to array
+ `my_array << value` add value to array
+ `my_array.collect {|value| [code]}` applies the code expression to every element in the array

## Hash
+ `my_hash = { key1=>value1, key2=>value2,key3=>value3}`
+ `my_hash = Hash.new` (empty hash)
+ `my_hash = Hash.new(default_value)` creates empty hash. default value is returned if non existing key is accessed
+ `my_hash[key]=value` add/update key/value
+ `my_hash.each {|k,v| [code]}`
+ `my_hash.sort_by {|k,v| v}` sort hash by value
+ `my_hash.select {|k,v| k == :symbol}` select value from my_hash where key is :symbol
+ `my_hash.each_key {|k| [code]}` iterate over keys of my_hash
+ `my_hash.each_value {|v| [code]}` iterate over values of my_hash
+ `my_hash.delete(k)` delete value by key

##Symbols

Defined by `:my_symbol`

symbols as keys in Hashes (for faster lookup):

    my_hash = {
    	:key1 => value1,
    	:key2 => value2,
    	:key3 => value3
    }

or

    my_hash ={
    	key1: value1,
    	key2: value2,
    	key3: value3
    }

## Blocks

Defined by `do`and `end` or `{}`.

## Procs

`name = Proc.new {[code]}`

+ proc doesnt check number of arguments (assigns nil to missing arguments)
+ does not return to calling method

call:

`object.method(&name)`

or

`name.call` 

## Lambdas

`lambda {|param| [code]}` 

+ Lambda checks number of arguments and throws error
+ passes control to calling method after return


## Methods

method definition:

    def my_method(input)
      [code]
    end

method call:

    my_method(x)

splat arguments (method can receive one or more args):

    def my_method(input, *splat_input)
      splat_input.each {|x| [code]}
    end

splat method call:
   
    my_method(x,a,b,c,d,e)

default parameter values

    def my_method (arg1, arg2=false)
      [code]
    end

Return values with `return` or implicit by last expression

definiton of method accepting blocks(yield):

    def method
      [code]
      yield
      [more code]
    end

yield with parameter:

    def method (param)
      [code]
      yield(param)
      [more code]
    end

call method with parameter and block

    method(param) {|n| [block code]}

## Respond to

`object.respond_to?(:symbol)` returns true if object can receive method (e.g. `[1,2,3].respond_to?(:push)`).