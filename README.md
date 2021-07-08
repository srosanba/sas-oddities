Some SAS oddities are difficult to troubleshoot. This repository contains a quasi-random collection of graphics-related oddities.

# ERROR: Template 'Styles.YourStyleHere' was unable to write to template store!

We started seeing this error when we went from PC to Grid. The solution is to add the following line of code to your program.

```
ods path work.templat(update) sasuser.templat(read) sashelp.tmplmst(read);
```

https://support.sas.com/techsup/notes/v8/4/739.html

# Bar charts that used to look good in RTF don't look so good any more

SAS changed the default output format from PNG to EMF. If you have to run old bar chart code on SAS 9.4, add the following option to your `ods graphics` statement.

```
outputfmt=png
```
