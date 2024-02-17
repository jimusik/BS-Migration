# BS-Migration

Bash Script for walking folders/files and importing into Bookstack using BS from https://github.com/Yetangitu/bs.git

Use-case: We currently have our repository inside a Gitlab CE environment for change tracking.  They are markdown files already so we are using this tool to pull all the MD files inside a folder and add it to a book or chapter.  

Use: migrate FUNCTION

FUNCTIONS
======

The following functions will process files inside a specific folder on your computer.  

create_books
-------

```
Please provide a folder for walking the books:
$HOME/Gitlab/knolwedgebase/
Any folder names to skip (or Enter to finish)?
images
```

Program will then look at folders only inside '$HOME/Gitlab/knolwedgebase/' and try to find Books with the same name as the sub-folders - if they exists it will skip and if they do not exist, it will create books for you.


create_chapters
------
```
Please provide a folder for walking the chapters:
$HOME/Gitlab/knolwedgebase/First-Book/

Any folder names to skip (or Enter to finish)?
images
```

Program will then look at folders only inside '$HOME/Gitlab/knolwedgebase/First-Book/' and try to find Chapters for the book "First-Book" - if they exists it will skip and if they do not exist, it will create chapters for you.

create_pages
-------
```
Please provide a folder for walking the pages:
$HOME/GitLab/Knowledgebase/First-Book/
Is this a root folder y/n?
y
```
To make sure pages can be placed at the root of the book, we ask if the folder listed is a root folder.  If it's a sub-folder, it's in the book and under that chapter.  

This will then walk the folder entered, looking for .md filenames and searching for their titles already in BookStack.  If it does not find it, it will create a page and upload the MarkDown file.

pull_book
-------

Code is not finished.  This is my attempt to automate the whole process of walking a book folder and uploading chapters and pages automatically.  