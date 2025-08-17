## Theory
Suppose you want to write new data, but you don't want to rewrite the old data, or append to that, and maintain the integrity of each related file.

This subset of conditionals, inspired by Yoda Conditionals, allows one to write three files per functions. The thing to keep in mind is each function is designed to append, except when writing to a new file which happens once.

~~~
that             "apple1.txt" has "the apple is red-green."; That            "banana1.txt" has "the banana is yellow-green.";
but that         "apple2.txt" has     "the apple is green."; That            "banana2.txt" has       "the banana is yellow.";
otherwise "apple_generic.txt" has      "that apple is red."; otherwise "banana_generc.txt" has        "the banana is brown.";
end
~~~

## Use Cases
You can write different classifications in naive bayes and decision trees to different files by specifying the name of the file, and its exact contents.

## Implementation

~~~ruby
##########################################################################################################
#                           Writing distinct files with distinct descriptions.                           #
##########################################################################################################

def ouvert(a, b, c, d, e, g)
  File.open(a, "a") { |f|
    f.puts b
  }

  File.open(c, "a") { |f|
    f.puts d
  }

  File.open(e, "a") { |f|
    f.puts g
  }
end

##########################################################################################################
#                                     Parallel File In / Out                                             #
##########################################################################################################
ouvert("apple1.txt",        "the apple is red-green",
       "apple2.txt",            "the apple is green",
       "apple_generic.txt",      "the apple is red.")
~~~
