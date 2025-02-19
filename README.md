# MWI Homework Exercises

Below you will find several exercises. Each was lovingly handcrafted by one of our developers to take 1-2 hours to complete. We ask that you select one, implement a solution, and send us a link to the repository with the completed solution within 24 hours. The purpose of this exercise is give you an opportunity to demonstrate your ability to deliver a result in a timely fashion. If you submit a working solution to one of the exercises we will schedule a final onsite interview. The quality of the code will not be taken into consideration, however you will be asked to explain it to us during your next interview.

For exercises that require working with files, you can find example inputs and outputs in this repository. These files will be in a directory named after the exercise.

## ACH Find Invalid Characters

ACH files are used to transfer between banks. It is a fairly old specification so it cannot handle modern unicode characters. In fact, it can only handle _alphameric_ (a-z A-Z0-9_-:.@$=/ ) characters. In this exercise you will create a program that will search for and point of invalid characters in an ACH file.

### Requirements

* Create a console application or script that takes a single parameter that is the path to the file to search for invalid characters.
* If you find a character that is not alphameric, print the character and the position in the file on screen.

### Resources

* [How ACH Works, A Developer's Perspective](https://engineering.gusto.com/how-ach-works-a-developer-perspective-part-4/)
* Example files:
  * invalid-chars.ach: an ACH file that contains invalid characters

## ACH Toggle

ACH is a fixed width file format. Each record is 94 characters long. In order to improve human readability it can be helpful to put line breaks at the end of each record. Make an application that can toggle (insert or remove) line endings in an ACH file.

### Requirements

* Create a console application or script that takes a single parameter that is the path to the file to toggle line ends on.

### Resources

* [How ACH Works, A Developer's Perspective](https://engineering.gusto.com/how-ach-works-a-developer-perspective-part-4/)
* Example files:
  * add_line_breaks.ach: example file that does not contain any line breaks
  * remove_line_breaks.ach: example file that contains line breaks

## CSV Duplicate Record Remover

A comma-separated values (CSV) file is a delimited text file that stores tabular data using the comma (',') character to separate plain text column (field) values, with each data record (row) separated by new line characters. This exercise entails making a console application that reads in a CSV file, finds duplicate entries, and writes the unique entries to a new CSV file.

### Requirements

* Read in a CSV file
* Make all the rows in the CSV unique
* Write the data back out to another CSV file
* The data in the resulting file should contain all of the unique entries in the file that was read in, without the duplicates

### Resources

* [CSV Wikipedia Article](https://en.wikipedia.org/wiki/Comma-separated_values)
* Example files:
  * DuplicateRemoverSampleInput.csv: a CSV file that contains duplicate records


## CSV to Fixed Width

A comma-separated values (CSV) file is a delimited text file that stores tabular data using the comma (',') character to separate plain text column (field) values, with each data record (row) separated by new line characters. A fixed length file, in contrast, does not use a delimiter such as a comma to separate field values, but instead makes each field value for a given column across all records a fixed length by appending or prepending a padding character such as a whitespace, so that when viewed each column of data is vertically aligned.

### Requirements

* Produce a command line application which will take a Comma-Separated Value (CSV) file, then write out the values from that file into a fixed length format file.
* Make each field in the fixed width file 9 characters long, left aligned

### Example

```
$ yourappname /path/to/input.csv /path/to/output/file
```

![Example CSV to Fixed Width](images/csv-to-fixed-width.png)

Note that the pipes shown on the right are for illustration only, and should not be in your output file.

### Resources

* [CSV Wikipedia Article](https://en.wikipedia.org/wiki/Comma-separated_values)
* Example files:
  * input-example.csv: a csv file
  * output-example: expected output based on input-example.csv

## CSV File Editor

A comma-separated values (CSV) file is a delimited text file that stores tabular data using the comma (',') character to separate plain text column (field) values, with each data record (row) separated by new line characters. CSV files also commonly have a header that denotes the meanings and order of the values. CSV files are a common file format for transferring payment information. It is also common to manipulate the data in a given CSV file to match a new format. In this exercise you will write a console application to read in a CSV file, manipulate some of the data from that file (listed in the requirements), and then write the new data to a new CSV file.

### Requirements

* Create a console application that takes a single parameter that is the path to the CSV file
  * Below is the header and a couple lines from the CSV file to be read in:

```
AccountNumber,LoanId,LastName,FirstName,AmountDue,DateDue,SocialLastFour
100000,001,Snow,John,10000,20170715,1234
100000,002,Snow,Victor,20000,20170715,1234
```

* After reading in the CSV file, make the following modifications to each record of imported data:
  * Take the LastName and FirstName field and concatenate them into one field with a space between FistName and LastName
  * Convert the AmountDue field from cents to dollars and format the field as Currency
* Write the new data into a new CSV file with a new name in the same path as the imported CSV file
  * Below is an example of what the output of the CSV file should look like

```
AccountNumber,LoanId,Name,AmountDue,DateDue,SocialLastFour
100000,001,John Snow,$100.00,20170715,1234
100000,002,Victor Snow,$200.00,20170715,1234
```

### Resources

* [CSV Wikipedia Article](https://en.wikipedia.org/wiki/Comma-separated_values)
* Example files:
  * InputBankFile.csv: an example file contain account balances
  * OutputBankFile.csv: the result of running the program with InputBankFile.csv

## Fix Homoglyphs

Sometimes we receive ACH files (and other file types) that include invalid characters that look like regular character from the English alphabet. Create an application that will replace these invalid, letter-like, characters with the nearest alphabet character.

### Requirements

Create a simple application that will take a file, search it for any homoglyph characters, replace the characters with their alphabet character equivalent then output the fixed data to another file.

- The application should take in two arguments from the command line
  - 1st argument: The input file
  - 2nd argument: The output file. This argument should be optional and a reasonable default output file should be used if an output file path is not provided.
- The application should be able to handle converting all of the characters described in the _Characters to Convert_ section.
- The file `names.txt` contains some names that include homoglyph characters.
  - The file `names-result.txt` contains the expected output from your application.

_Refer to the `fix-homoglyphs` directory in this repository for the test file and result file._

#### Characters to Convert

| Homoglyph | Alphabet Character |
|-----------|--------------------|
| Ä         | A                  |
| Å         | A                  |
| Á         | A                  |
| Â         | A                  |
| À         | A                  |
| Ã         | A                  |
| â         | a                  |
| ä         | a                  |
| à         | a                  |
| å         | a                  |
| á         | a                  |
| ã         | a                  |
| ß         | B                  |
| þ         | b                  |
| Þ         | b                  |
| Ç         | C                  |
| ç         | c                  |
| Ð         | D                  |
| É         | E                  |
| Ê         | E                  |
| Ë         | E                  |
| È         | E                  |
| é         | e                  |
| ê         | e                  |
| ë         | e                  |
| è         | e                  |
| ƒ         | f                  |
| Í         | I                  |
| Î         | I                  |
| Ï         | I                  |
| ï         | i                  |
| î         | i                  |
| ì         | i                  |
| í         | i                  |
| ı         | i                  |
| Ñ         | N                  |
| ñ         | n                  |
| Ö         | O                  |
| Ó         | O                  |
| Ô         | O                  |
| Ò         | O                  |
| Õ         | O                  |
| ô         | o                  |
| ö         | o                  |
| ò         | o                  |
| ó         | o                  |
| ø         | o                  |
| ð         | o                  |
| õ         | o                  |
| Ü         | U                  |
| Ú         | U                  |
| Û         | U                  |
| Ù         | U                  |
| ü         | u                  |
| û         | u                  |
| ù         | u                  |
| ú         | u                  |
| µ         | u                  |
| Ý         | Y                  |
| ÿ         | y                  |
| ý         | y                  |
| Ø         | 0                  |

#### Hints

- Use the table in the _Characters to Convert_ section to save time having to locate which characters are considered homoglyphs.
- Use a map (or dictionary, depending on your choice of language) to store the conversion information. Alternatively, a switch statement may be used instead.

### Example

If the character "ü" appears it should be converted to the character "u".

## Web Scraping

XKCD is a popular comic with a fairly consistent web page layout, which makes it a good candidate for an application that traverses their comic archive. If you wanted to index all of the existing comics manually, it would take ages, but with some way to read the HTML response to find the information we care about, along with the "next" button's link, we should be able to catalog them pretty quickly.

### Requirements

* Create a console application or scripts that pulls content from XKCD, reads specific information from the page, and moves to the next page.
  * Comic Number
  * Comic Title
  * Image Hover Text
  * Image Link
* Walk through all xkdc comic pages
* Grab useful information (comic number, comic title, alt text, image link) from each page

### Bonus

* Handle the change in output around comic 1100

### Example Output:

```
Comic Number: "1"
Comic Title: "Barrel - Part 1"
Hover Text:  "Don't we all."
Image Link: "imgs.xkcd.com/comics/barrel_cropped_(1).jpg"
```

### Resources

* https://xkcd.com/1/
