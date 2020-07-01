---
layout: page
permalink: /support/google-add-on/document-generation
title: Custom Documentation Generation Support
---

# Custom Documentation
The custom adoption paperwork adds specific information about the animal so you can automatically send a single file.  You can change or add additional documents using the folder in your RescueDen Google Drive.

# Templates
The base document is treated as a template, where anything between {{ and }} is replaced with the animal value. Valid examples include `{%raw%}{{ .Name }}{%endraw%}` and `{%raw%}{{ .ShelterCode }}{%endraw%}`.  The template replacement is based upon [Golang Html Templates](https://golang.org/pkg/html/template/). See [Golang Html Templates](https://golang.org/pkg/html/template/) for additional information on standard template functions (if, and, etc.).  The following keys are supported.

# Functions
Functions can be used for special format cases.  Place function between {%raw%}{{ }}{%endraw%}.
|Function|Info|
|---|---|
|`his .`|Used to place either his or hers into the document.|
|`him .`|Used to place either him or her into the document.|
|`formatDate .Date` |Any date can be formated using this function.|
|`yesNo .Boolean`|Format any boolean as yes or no|
|`picture 200 .`|Insert the animal picture with the specified width|
|`pageBreak`|Force a page break at this location|
