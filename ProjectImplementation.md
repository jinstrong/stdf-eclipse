# Introduction #

In what follows a proposition is made on how the tasks at hand can be implemented.

# Details #

In the end what we want to come to is a way to "define" a **Report**.

A **Report** provides the reader with the "condensed" information that he needs. If in the report the reader discovers something strange, then he needs to go in and investigate (manually).

Now this whole process shouldn't be limited to STDF files (although easiest), it should also be able to read WAT and other kinds of useful files that belong to the "project".

So it means we need an infrastructure to select the data files, and parse them ... into what ... memory ... ok ... and then, to make a Report, we make subsets of information ... basically what we are doing is selecting items from memory ...

Isn't it more convenient to parse the date in a database (then we don't have size limitations) and the subsequent actions start to read from this database in a structured way with SQL statements ???