# About
I've been writing my documents in TeX for a while now, actually around 15 years I guess. But never have I ever created own classes or
packages. Since I don't like to write texts in word and not always simple text files like this are appropriate, I started writing documents
for the students representation in TeX.
Once I decided to write templates for our documents which almost ended in a mess. While having a bad sleep I woke up and wrote down notes
which types of documents we were writing and how they were always formatted. Probably this is a good chance to write some own classes,
improve my skillset and reduce the mess by a lot.
This doc should be explanation enough, so can be refered to as usage.

# Classes
## formalLetter
As the name suggests a letter we write when requesting funds, official documents or similiar. This class also has the option _signature_
which will append 2 a signature field for each of our chairs. 
The doc usually has the structure as follows. 

### structure
- header w/ logo leftbound, 1pt rule
- letterhead w/ own adress, recipent and letter date in line w/ recipent
- subject centered, bold
- text, not specified
- closing, optional signature
- footer w/ 3 cols: infos

### parameters
All parameters are optional and should be provided in \\documentclass[PARAMS]{formalLetter}.
symbol | example | default | desc 
---|---|---|---
signature | --- | NONE| add signature field per chair member
siglen | siglen=.3\\textwidth | .35\\textwidth | length of signature field
--- | 11pt | 10pt | fontsize
hrulew | hrulew=.5pt | 1pt | header rulewidth
frulew | frulew=.5pt | 1pt | footer rulewidth
rulew | rulew=.5pt | 1pt | header and footer rulewidth; __overwrites hrulew, frulew if also defined__
a4paper | --- | a4paper | set doc is a4paper-format; for future changes
top/bottom/left/right | top=2.5cm | (t,l,b,r)=(2.5, 3, 3.5, 3.5)cm | page borders 
border | border=3cm | NONE | all borders set to 3cm; __overwrites tlbr__
splitratio | splitratio=.5 | .5 | margin left + right of signature is half of space between signatures

### commands
Commands are easy text replacements. They are used as placeholder as \command in the text and will be substituted. Some are optional. Refer to table. 
They should be set via \commandSet{VALUE}.
command | optional | default | desc
---|---|---|---
recipent | false | --- | String, letter receipent
subject | false | --- | String, ...
date | true | \\today | \\formatdate{DD}{MM}{YYYY}

### environments
Environments are written in \begin{ENVIRONMENT}[OPT_ARGS]{ARG}...\end{ENVIRONMENT}.
environment | desc
---|---
letterText | literally the content of the letter

## handout
As the name suggests any nonformal letter. Depending on the Situation could be with or without header.

### structure
### parameters
### environments
