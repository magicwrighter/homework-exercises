# homework-exercises

## ACH Toggle

The directory ach_toggle_files contains 2 example files to use with this exercise:

- add_line_breaks.ach
  - This is an example file that does not contain any line breaks.
- remove_line_breaks.ach
  - This is an example file that contains line breaks.


## CSV to Fixed Width
A comma-separated values (CSV) file is a delimited text file that stores tabular data using the comma (',') character to separate plain text column (field) values, with each data record (row) separated by new line characters. A fixed length table file, in contrast, does not use a delimiter such as a comma to separate field values, but instead makes each field value for a given column across all records the same length by appending or prepending a padding character such as a whitespace, so that when viewed each column of data is vertically aligned. The csv_to_fixed directory contains a simple example.  

**Requirements**

* Produce a command line application which will take a single column width value, a Comma-Separated Value (CSV) filepath, and an output filepath, then write out the values from that file into a fixed length format text file where each column is the length of the given width value.

`$ yourappname 4 /path/to/input.csv /path/to/output/file`

**Bonus**

* If no column width value is provided, default to using the greatest field value length for each column such that output values are not truncated.  

**Resources**

* https://en.wikipedia.org/wiki/Comma-separated_values