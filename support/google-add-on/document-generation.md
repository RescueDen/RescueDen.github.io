---
layout: page
permalink: /support/google-add-on/document-generation
title: Custom Documentation Generation Support
---
The custom adoption paperwork adds specific information about the animal so you can automatically send a single file.  You can change or add additional documents using the folder in your RescueDen Google Drive.

# Templates
The base document is treated as a template, where anything between {{ and }} is replaced with the animal value. Valid examples include `{%raw%}{{ .Name }}{%endraw%}` and `{%raw%}{{ .ShelterCode }}{%endraw%}`.  The template replacement is based upon [Golang Html Templates](https://golang.org/pkg/html/template/). See [Golang Html Templates](https://golang.org/pkg/html/template/) for additional information on standard template functions (if, and, etc.).  The following keys are supported.

* ShelterCode
* Id
* ShelterId
* Name
* DisplayName
* Microchipped
* MicrochipImplantedBy
* Microchip
* OnShelter
* Age
* Breed
* Color
* Species
* Sex
* AdoptionFee
* DateBroughtIn
* DateOfBirth
* EstimatedDOB
* Neutered
* NeuteredDate
* NeuteredByVet
* IsGoodWithCats
* IsGoodWithDogs
* IsGoodWithChildren
* IsHouseTrained
* HasSpecialNeeds
* LastUpdateFromShelter
* LastChangeInShelter
* Bio
* Flags
* RabiesTag

# Functions
Functions can be used for special format cases.  Place function between {%raw%}{{ }}{%endraw%}.

|Function|Info|
|---|---|
|`heShe .`|Used to place either he or she into the document.|
|`himHer .`|Used to place either him or her into the document.|
|`hisHer .`|Used to place either his or her into the document.|
|`hisHers .`|Used to place either his or hers into the document.|
|`formatDate .Date` |Any date can be formated using this function.|
|`yesNo .Boolean`|Format any boolean as yes or no|
|`picture 200 .`|Insert the animal picture with the specified width|
|`pageBreak`|Force a page break at this location|

# Metadata
You can add specific metadata to documents that are used by the document generator outside of the document.


|Metadata|Info|
|---|---|
|`emailTemplateId`|When the document is selected, the referenced document is used for email body.|
|`emailSubject`|When the document is selected, the provided text is used an email subject.|

The metadata must be provided in json format and in the document's [description field](https://www.bettercloud.com/monitor/the-academy/how-to-add-descriptions-to-google-docs-for-better-docs-search/).

```json
{
	"emailTemplateId":"1NrkUAoaefadPEJOwfMjeh8H7SqmhJMHafeaX1HF9_l234ad",
	"emailSubject":"{%raw%}{{.DisplayName}}{%endraw%}'s Adoption"
}
````
