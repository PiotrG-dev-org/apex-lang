#CSVParser Documentation

##Introduction

CSVParser is useful class to parse CSV file, the result will store in a `List<List<String>>` variable.

To use the CSVParser, you need to new a CSVParser instance first. Then set the properties to satisfy you requirement. Then call the parse method to get the result.

##Properties

  * ###textQualifier

  `public String textQualifier {get; set;}`

  The character to use as a text qualifier in the data. for example, you can use the ' and ".

  Default value is the double quotes (").

  * ###delimiter

  `public String delimiter {get; set;}` 

  The character to use as the column delimiter.

  Default value is the comma (,).

  * ###escapeMode

  `public String escapeMode {get; set;}`

  The way to escape an occurrence of the text qualifier inside qualified data. You can use [#ESCAPE_MODE_DOUBLED CSVParser.ESCAPE_MODE_DOUBLED] or [#ESCAPE_MODE_BACKSLASH CSVParser.ESCAPE_MODE_BACKSLASH].

  Default value is [#ESCAPE_MODE_DOUBLED CSVParser.ESCAPE_MODE_DOUBLED].

##Methods

  * ###parse
  `public List<List<String>> parse(String contents)`

  Parse the `contents` in the CSV format to `List<List<String>>`

##Constants

  * ####ESCAPE_MODE_DOUBLED

  `public static String ESCAPE_MODE_DOUBLED`

  Double up the text qualifier to represent an occurrence of the text qualifier.
  
  * ####ESCAPE_MODE_BACKSLASH

  `public static String ESCAPE_MODE_BACKSLASH`

  Use a backslash character before the text qualifier to represent an occurrence of the text qualifier.

##Example

```apex
CSVParser parser = new CSVParser();
parser.textQualifier = '"';
parser.delimiter = ',';
parser.escapeMode = CSVParser.ESCAPE_MODE_DOUBLED;
String contents = 'Mode,Price,Count\nFerrari 458 Italia,"$225,325,5"\nFerrari 599 GTB Fiorano,"$336,541,2"';
List<List<String>> result = parser.parse(contents);
```
