## Theory
Implementing of that-but that-otherwise conditionals.

~~~
that             "apple1.txt" has "the apple is red-green."; That            "banana1.txt" has "the banana is yellow-green.";
but that         "apple2.txt" has     "the apple is green."; That            "banana2.txt" has       "the banana is yellow.";
otherwise "apple_generic.txt" has      "that apple is red."; otherwise "banana_generc.txt" has        "the banana is brown.";
end
~~~

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
