# LibreOffice Macros

## Date Inserter with Header 
This will automatically add a custom date format (DD.MM.1YYYY [T::HH:MM:sss]) with the Header 1 style for quick and easy 'captain logs'. I use the H.E. ([Holocene calendar](https://en.wikipedia.org/wiki/Holocene_calendar)) time format that believes theat humanity started 12,000 years ago with the advent of agriculture. Also, because I am a major [Foundation](https://sandyuraz.com/articles/foundation-time/) by Isaac Asimov nerd. 



```
REM  *****  BASIC  *****

sub Date
rem ----------------------------------------------------------------------
rem define variables
dim document   as object
dim dispatcher as object
rem ----------------------------------------------------------------------
rem get access to the document
document   = ThisComponent.CurrentController.Frame
dispatcher = createUnoService("com.sun.star.frame.DispatchHelper")

rem ----------------------------------------------------------------------
dispatcher.executeDispatch(document, ".uno:InsertDateField", "", 0, Array())

rem ----------------------------------------------------------------------
rem dispatcher.executeDispatch(document, ".uno:FieldDialog", "", 0, Array())

rem ----------------------------------------------------------------------
rem dispatcher.executeDispatch(document, ".uno:FieldDialog", "", 0, Array())

rem ----------------------------------------------------------------------
dim args4(1) as new com.sun.star.beans.PropertyValue
args4(0).Name = "Template"
args4(0).Value = "Heading 1"
args4(1).Name = "Family"
args4(1).Value = 2

dispatcher.executeDispatch(document, ".uno:StyleApply", "", 0, args4())

rem ----------------------------------------------------------------------
dispatcher.executeDispatch(document, ".uno:InsertPara", "", 0, Array())


end sub

sub Main
rem ----------------------------------------------------------------------
rem define variables
dim document   as object
dim dispatcher as object
rem ----------------------------------------------------------------------
rem get access to the document
document   = ThisComponent.CurrentController.Frame
dispatcher = createUnoService("com.sun.star.frame.DispatchHelper")

rem ----------------------------------------------------------------------
dim args1(1) as new com.sun.star.beans.PropertyValue
args1(0).Name = "Template"
args1(0).Value = "Heading 1"
args1(1).Name = "Family"
args1(1).Value = 2

dispatcher.executeDispatch(document, ".uno:StyleApply", "", 0, args1())

rem ----------------------------------------------------------------------
dim args2(5) as new com.sun.star.beans.PropertyValue
args2(0).Name = "Type"
args2(0).Value = 0
args2(1).Name = "SubType"
args2(1).Value = 0
args2(2).Name = "Name"
args2(2).Value = ""
args2(3).Name = "Content"
args2(3).Value = "0"
args2(4).Name = "Format"
args2(4).Value = 10051
args2(5).Name = "Separator"
args2(5).Value = " "

dim sText as string
sText = Format( Now, "DD.MM.1YYYY [T::HH\:mm\:ss]")

dim textFormatat(0) as new com.sun.star.beans.PropertyValue
textFormatat(0).Name = "Text"
textFormatat(0).Value = sText+CHR$(9)  
dispatcher.executeDispatch(document, ".uno:InsertText", "", 0, textFormatat())





rem ----------------------------------------------------------------------
dispatcher.executeDispatch(document, ".uno:InsertPara", "", 0, Array())


end sub
```
