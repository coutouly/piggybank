piggybank
=========

Contribution from the French Observatory to the UDF Pig Functions

FixedWidthBinaryLoader.java
===========================

Usage
=====

 A fixed-Binary-width file loader. 
  from org.apache.pig.piggybank.storage.FixedWidthLoader.java
  
 Takes a string argument specifying the ranges of each column in a unix 'cut'-like format.
 Ex: '-5, 10-12, 14, 20-'
  Ranges are comma-separated, 1-indexed (for ease of use with 1-indexed text editors), and inclusive.
 A single-column field at position n may be specified as either 'n-n' or simply 'n'.

 A second optional argument specifies whether to skip the first row of the input file,
 assuming it to be a header. As Pig may combine multiple input files each with their own header
 into a single split, FixedWidthLoader makes sure to skip any duplicate headers as will.
 'SKIP_HEADER' skips the row; anything else and the default behavior ('USE_HEADER') is not to skip it.

 A third optional argument specifies a Pig schema to load the data with. Automatically
  trims whitespace from numeric fields. Note that if fewer fields are specified in the
 schema than are specified in the column spec, only the fields in the schema will
 be used.
 
 A fourth argument specifie the fixed length


 Column spec idea and syntax parser borrowed from Russ Lankenau's implementation
  at https://github.com/rlankenau/fixed-width-pig-loader 
