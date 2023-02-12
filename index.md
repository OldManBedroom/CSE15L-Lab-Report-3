In this report, I will show four options of **find** command.

type
==========

Example 1
-----

```
[cs15lwi23ald@ieng6-202]:skill-demo1-data:274$ find written_2 -type d -name "b*"
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```

In this example, I used **-type d** in the command to show only directories that start with "b".

files that start with "b" are not shown.

This is a useful option when you only want to search for directories.

Example 2
------

```
[cs15lwi23ald@ieng6-202]:skill-demo1-data:275$ find written_2 -type f -name "Vallarta*"
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

In this example, I used **-type f** in the command to show only files that start with "Vallarta".

direcotries that start with "Vallarta" are not shown.

This is a useful option when you only want to search for files.

I found this option from this [link](https://linuxhandbook.com/find-command-examples/).

iname
======

Example 1
-------

```
[cs15lwi23ald@ieng6-202]:skill-demo1-data:276$ find written_2 -iname "vallarta*"
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

In this example, I used **-iname** to make a case-insensitive search for anything that start with "vallarta".

I found three results that start with "Vallarta" with a capital "V".

This is very useful when you are not sure whether the thing you are seaching for is in uppercase or in lowercase.

Example 2
-------

```
[cs15lwi23ald@ieng6-202]:skill-demo1-data:281$ find written_2 -type d -iname "B*"
written_2/non-fiction/OUP/Berk
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```

In this example, I used **-iname** to make a case-insensitive search for any directories that start with "B".

I found five directories that start with "B" or "b".

This is very useful when you want to find anything that start with a certain character and don't care about their cases.

I found this option from this [link](https://linuxhandbook.com/find-command-examples/).

size
======

example 1
-----

```
[cs15lwi23ald@ieng6-202]:skill-demo1-data:282$ find written_2 -size +120k
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
```

In this example, I used **-size +120k** to find only files that are larger than 120KB.

The "+" sign in this option means "larger than".

This is very useful when you want to set an upperbound for the sizes of a bubch of files and you need to find files larger than a certain upperbound in order to delete some content from those files.

example 2
------

```
[cs15lwi23ald@ieng6-202]:skill-demo1-data:285$ find written_2 -size -3k
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
```

In this example, I used **-size -3k** to find only files that are smaller than 3KB.

The "-" sign in this option means "smaller than".

This is very useful when you want to set a lowerbound for the sizes of a bunch of files and you need to find files smaller than a certain lowerbound in order to add some content to those files.

I found this option from this [link](https://linuxhandbook.com/find-command-examples/).

maxdepth
======

example 1
-------

```
[cs15lwi23ald@ieng6-202]:written_2:300$ find . -maxdepth 1 -type d
.
./non-fiction
./travel_guides
```

In this example, I used **-maxdepth 1** to find directories only in this current directory, not in its subdirectories.

the number after "maxdepth" can be changed to represent how many layers of subdirectories will be searched.

This will be helpful if there are too many subdirectories and you only want to focus on the current directory.

example 2
------

```
[cs15lwi23ald@ieng6-202]:written_2:301$ find . -maxdepth 2 -type d
.
./non-fiction
./non-fiction/OUP
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
```

In this example, I used **-maxdepth 2** to find directories only in this current directoy and its subdirectories, not in its subdirectories' subdirectories.

This will be helpful it there are too many layers of subdirectories and you only want to focus on the current directory and its subdirectories.

I found this option from this [link](https://linuxhandbook.com/find-command-examples/).
