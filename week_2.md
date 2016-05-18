# Type
```ruby
   Integer : a = 1234; call : a
   Float : a = 1.001; call : a
   String : 
    Khai bao : strs = "I am "a" string" == strs = %|I am "a" string| == strs = %+I am "a" string+; 
     call : strs
       str = strs.upcase() # chuyen strs toan bo sang chu viet hoa
       str = strs.downcase() # chuyen strs toan bo sang chu thuong
       strs.each_char do |element|
            puts element
        end # se duyet qua tung phan tu va output ra

    strs = "line 1\nline 2\nline 3"
      strs.each_line do |element|
        puts element
      end # se duyet qua tung dong va output ra

    if strs.include? "I"
        puts "yes"
    end #kiem tra trong strs co string sau hay ko?

    strs.insert(3, "add")
      puts strs # output la: "I aaddm a string"

    strs = "prytanes"
      a = strs.center(10)
      puts "[" + a + "]" # output ra string length = 10 
      b = strs.center(13, "*") puts b # output ra string length = 13 la:"**prytanes***"

    strs = "england\r\n"
      a = strs.chomp # remove "\r\n" in strs
      b = strs.chomp "and" # remove "and\r\n" => strs = "engl"

    strs = "I am a string"
      strs << "string aad"
      puts strs => strs = "I am a stringstring add"

    strs = "Plutarch"
      a = strs.count "a" => output: 1  # dem so phan tu "a"
      b = strs.count "ar" => output: 2 # dem so phan tu "a" va "c"
      c = strs.count "a-c" => output: 2 # dem so phan chu tu "a" den "c"

    strs = "tar" 
      strs.reverse! => output: strs = "cat" #dao nguoc string

    strs = "abc abc"
      a = strs.sub("abc", "--") => output a = "-- abc" #thay the phan tu dau tien
      b = strs.gsub("abc", "--") => output b = "-- --" #thay the toan bo cac phan tu trong string
      strs["abc"] = "def" => output strs = "def abc" #thay the phan tu bat ky

    split : chia string ra string nho hon
      strs = "one two three"
      str = strs.split(" ") => output str = ["one", "two", "three"]

  Array: array = [1, 2, 4 5], Array.new(3), Array.new(3, 1)
    array.firts == array[0] # gia tri = 1
    array.last == array[array.length - 1] # gia tri la 5
    array.push(6) # duoc array = [1, 2, 3, 4, 5, 6]
    array.push("string") # duoc array = [1, 2, 3, 4, 5, 6, "string"]

    items = array[]
      items << "cat" << "dog" # items = ["cat", "dog"]
      items << "bird" # items = ["cat", "dog", "bird"]

    arr = ["orange", "lemon", "lime"]
      a = arr.delete_at(1) # a = ["orange", "lime"]
      b = arr.delete("lime") # b = ["orange", "lemon"]

    numbers = [10, 20, 30, 40, 50]
      numbers.delete_if { |e| e > 30 } # numbers = [10, 20, 30]

    names = ["Hung", "Nam"]
      names.index("Hung") # 0 la chi so cua phan tu
      a = names.pop() # a = ["Hung"] :xoa di phan tu cuoi cua mang
      arr =["Hung", "Nam", "Ha"]
      arr.pop(2) # arr = ["Hung"] :xoa di 2 phan tu cua mang tinh tu cuoi mang
    prime = [3, 5, 10, 15]
      prime.each do |number|
        Puts number
      end # duyet qua cac phan tu cua mang
  tuong duong : prime.each {|number| puts number}
      prime.each_index do |index|
        puts index
      end # in ra chi so cua cac phan tu trong mang: 0, 1, 2, 3, 4

    values = ["cat", "dog", "rabbit", "giraffe"]
      for element in 0..values.length-1
        puts values[element]
      end # in ra cac phan tu cua mang

    remove non-unique element in-place
      values = [1, 1, 2, 3, 4, 4]
      values.uniq! # values = [1, 2, 3, 4]

    tac dong den all cac element trong array
      array = [1, 3, 4, 6]
      result = array.collect{|element| element *2}
      #result = [2, 4, 6, 8]

    elements = [10, 20, 30, 40, 50]
      elements[1..3] = [100, 200]
      # elements = [10, 100, 200, 50] ;thay the bang array con vao 

  Hash = {key: value}
    Create a new hash: items = Hash.new() or items = {}
      items["milk"] = 5 => items = {"milk"=> 5}
      items["eggs"] = 10 => items = {"milk"=> 5, "eggs"=> 10}
        items[:milk] = 5; items[:eggs] = 10 => items = { milk: 5, eggs: 10 } == items = {:milk=> 5, :eggs=> 10 }

    values = {cat: 1, dog: 2, rabbit: 4}
      values.delete_if{|key, value| key.length > 3}
      #values = {cat: 1, dog: 2}

    goi key tra ve values: values[:cat] tra ve 1

    names = {"charlotte"=> "stant", "maggie"=> "verver", "adam"=> "verver"}
    for key in names.keys()
      print key, "/", names[key], "\n"
    end # output: charlotte/stant;...
    tuong duong : 
    names.each do |key, value|
    print "KEY: ", key, "\n"
    print "VALUE:", value, "\n"
    end
    tuong duong :
    names.each {|key, value| print key, " ", value, "\n"}
  
  items = Hash.new()
  if items.empty?
    puts "Empty"
  end

# noi 2 hash
  onw = {"a"=> 1, "b"=> 2}
  two = {"b"=> 3, "c"=> 0, "d"=> 3}
  both = two.merge(one)
  # both = {"b"=> 2, "c"=> 0, "d"=> 3, "a"=> 1}

# dao nguoc 1 hash
  onw = {"a"=> 1, "b"=> 2}
  two = onw.invert()
  # two = {1 => "a", 2 => "b"}

# kiem tra su ton tai cua key
  one = {"spoon" => 10, "fork" => 20}
  if one.key?("spoon")
    puts "found: spoon"
  end
  tuong duong
  if one.has_key?("spoon")
    puts "found: spoon"
  end

# chuyen hash thanh array
  hash = {"a" => 1, "b" => 2}
  has = hash.flatten()
  puts has
  # has = ["a", 1, "b", 2]

# kiem tra 2 hash co giong nhau ko?
  fruit1 = {"apple" => 1, "pear" => 2}
  fruit2 = {"guava" => 3, "apricot" => 4}
  fruit3 = {"pear" => 2, "apple" => 1}
  if !fruit1.eql?(fruit2)
    puts "1 khong giong 2"
    end
  if fruit1.eql?(fruit3)
    puts " 1 giong 3"
    end

# convert hash thanh string de tinh do dai, or tinh memory
  values = {"a" => 10, "b" => 20}
  s = values.inspect
  # s = "{\"a\"=>10 ,\"b"=>29}"
  # puts s.length ; output la 20
# sap xep thu tu hash theo key tang dan a-z
plants = {"carrot" => 5, "turnip" => 10, "apple" => 8}
plants.sort.each do |key, value|
puts key + ": " + String(value)
end
# output:
# apple: 8
# carrot: 5
# turnip: 10
```

```ruby
 h1 = { a: 1, b: 2, c: 3 }
 h2 = { :a => 1, :b => 2, :c => 3 }
 h3 = { 'a' => 1, 'b' => 2, 'c' => 3 }
 h4 = { :'a' => 1, :'b' => 2, :'c' => 3 }
```

# Operator
  + , - , *, '%', &&, ||, !, &, |, ^, ** (a.!b + !a.b) 

# Variable
  - Global var: $global_var
  - Class var: @@class_var (declear inside a class)
  - Instance var: @instance_var (declear inside a class, and share between methods)
  - local var: local_var (scope is a function, a block, {} ...)

```ruby
$global_var = "I am a global var"

class A
  @@class_a_var = "I am class a var"

  def initialize
    @instance_a_var = "I am instance a var"    
  end

  def method_1
    puts @instance_a_var + "  inside method 1"
  end

  def method_2
    puts @instance_a_var + " inside method 2"
  end

  def show_class_var
    puts @@class_a_var
  end

  def show_global_var
    puts $global_var
  end

  def show_local_var
    local_var = "I am local var"
    puts local_var
  end
end
class B
  @@class_b_var = 0

  def increase_class_var
    @@class_b_var += 1
  end

  def show_class_var
    puts @@class_b_var
  end

  def show_global_var
    puts $global_var
  end
end
```
# Loop, Iterator

```ruby
array = (1..10).to_a

for element in a
  puts element
end

array.each do |element|
  puts element
end

array.each do |element|
  next if element.even?
  puts element
end

array.each { |element| puts element }

i = 0
while(i <= array.length - 1)
  puts array[i]
  i += 1
end

i = 0
loop do
  puts array[i]
  i += 1
  break if i > array.length -1 
end
```

# Constant
  - PI = 3.14195

# Class
  - Declear class
  - initialize
  - Define methods
  - Inheritance

  class Dog < Animal
  end
 
# Module

```ruby
module Sumarry1305
  module ClassMethods
    
  end
  
  module InstanceMethods
    
  end
  
  def self.included(receiver)
    receiver.extend         ClassMethods
    receiver.send :include, InstanceMethods
  end
end

class Progammer < Employee
  include LearnRuby
  include LearnTest
  include LearnHtml
  include LearnCss
end

class HtmlCoder < Employee
  include LearnHtml
  include LaernCss
end

module LearnHtml
  module ClassMethods
    def i_am_class_method
      
    end
  end
  
  module InstanceMethods
    def learn_html_from_team_tree_house
    end

    def learn_html_from_w3_school
    end
  end
  
  def self.included(receiver)
    receiver.extend         ClassMethods
    receiver.send :include, InstanceMethods
  end
end
```

# File
  - open
  - write
  - read
  - close
