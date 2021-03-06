XLSXI18N
========
Simple command line utility to generate language files for your app from xlsx files

Configuration
-------------
You need to start writing your xlsx file, specifying LABELs, FILEs and translations in a table like this:
```
------------------------------------------------------------------
    LABEL    |      FILE      |  ENGLISH  |        ITALIAN 
------------------------------------------------------------------
app_name     | ui_strings.xml | App name  | Nome dell'applicazione
------------------------------------------------------------------
app_version  | ui_strings.xml |  Version  | Versione
------------------------------------------------------------------
weat_array   | ui_weather.xml |[Sun, Rain]|[Sole, Pioggia]
------------------------------------------------------------------
```
You don't need to escape ' or " and if you want to specify an array you just need to put your string between square brackets, separated by commas.

After that, you need to write your config.json file, specifying default language, the corresponding column number in the xlsx file for the label, file and provided translations.
```
{
    "default": "en",
    "label": 0,
    "file": 1,
    "translations" : {
        "en": 2,
        "it": 3
    }
}
```
Usage
-----
```
$ ./xlsxi18n path_file.xlsx
```
A 'res' folder will be created. Everytime you launch the script, 'res' folder's files 
get overwritten and a backup copy is created.