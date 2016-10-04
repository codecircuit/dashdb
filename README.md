# Dash Database Library

The dashdb is a light weight database and an alternative to JSON. You might
find dashdb useful if you must include a library, which statically links
a jsoncpp library you do not want to use, but is incompatible with your own
jsoncpp version.

The main concept is to have concatenated keys, followed by an equal sign,
followed by the value. Moreover there is a simple transformation rule from
a JSON file to a dashdb file. Imagine the following json file:
```JSON
	{
		"kernels" : [
			{
				"name" : "update_positions",
				"partitioning" : "x"
			},
			{
				"name" : "update_speed",
				"partitioning" : "x"
			}
		],
		"meta information" : "None"
	}
```
Would become in dashdb representation:
```
	kernels-0-name=update_positions
	kernels-0-partitioning=x
	kernels-1-name=update_speed
	kernels-1-partitioning=x
	meta information=None
```
**Reserved symbols:** you must not use a '-', '=', or a key beginning with a
number.  
The source code comments are written with doxygen syntax, thus building
a documentation yourself is recommended.
