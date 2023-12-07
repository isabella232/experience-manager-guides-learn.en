---
title: Native PDF | Support for language variables
description: Use language variables in the PDF output and output templates
exl-id: 2335a7d5-251b-4266-8bba-9c9935e7bbf4
---
# Support for language variables

AEM Guides provides the feature to use language variables. You can use language variables to define localized strings in the PDF output or to localize any static text in the output templates. You can use CSS styles to localize the strings coming from a CSS.

## Use language variables in the PDF output

You can use language variables to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output. The variable name is the same for all languages but can have different values for the various languages. You can update the value for these variables in one or more languages, and then the localized value is automatically picked in the PDF output.

For example, you can have the following ways to present the label `Note` in the PDF output:

- English: Note

- French: Remarque

- German: Hinweis

 <img alt= "output ot the document that contains language variables" src="./assets/language-variable-output.png" width="550">

 *A sample note in English, French, and German languages.*
 
>[!NOTE]
>
> If the value for any variable isn’t defined in a particular language, then AEM Guides picks the string from the language of the UI (User Interface of the application) as a fallback mechanism. 
>
> If you have not defined the value in the language of the UI, it looks for English (`en_us`), or else it picks the English(`en`) value and displays the same in the PDF output. 

## Types of language variables

AEM Guides supports two types of variables: Application and User variables.

### Application variables

AEM Guides provides a set of predefined or out-of-the-box application variables. You can use these predefined variables to add information about a document specific to AEM Guides. For example, the `chapter-number` variable, if included in a page, displays the chapter number to which the page belongs. The `author-label` variable displays the name of the document author. 

>[!NOTE]
>
> You can override the value for an application variable.


### User variables

You can also create new language variables. For example, you can create a user variable Publisher for the label of the publisher for the document. 

>[!NOTE]
>
>  You should have administrative privileges to create user variables and edit the application variables.
 
<img alt="langiage variables window" src="./assets/add-language-variables.png" width=550>

*Add and view the language variables for a selected language.*  

## Add a new language variable 

1. In the Web Editor, go to the Output tab.
1. Select **Language Variables** <img src="./assets/language-variables.svg" width="25"> in the left panel.
1. Select **Edit** to open the **Language Variables** window. The application and the user variables present in the selected language are listed in alphabetical order. The values are displayed according to the selected language. For example, if you select the French language, “Tip” is displayed as “Conseil.” 
1. From the **Language** dropdown, select the desired language in which you want to edit a variable.

   >[!NOTE]
   >
   > If you do not view the desired languages, enable the desired language from the **Language Variable Settings**. Select Settings <img src="./assets/settings-icon.svg" width="25">  to open the **Language Variables Settings** dialog.

1. Enter the variable name in the **Name** column and its value in the **Value** column.

   >[!NOTE]
   >
   >You can use any HTML content as a variable value to display the variable value in specific formatting. For example, you can add `<b>` tag to the variable value to display the Publisher in bold.

1. Select **Add Language Variable** <img src="./assets/add-language-variable.svg" width="25"> to add a new language variable to the selected language. Adding a variable to one language automatically adds it to all languages. You cannot create a variable with the same name as an existing variable. An error is displayed. 

  >[!NOTE]
  >
  > If you don’t select **Add Language Variable**, the variable is not created and added to the list

## Export and import language variables

Experience Manager Guides provides the support to export and import the language variables present in the selected language. You can easily export all the language variables along with the defined values. This includes both application and user variables. Use the exported file to make the desired changes in the values or get them localized to other languages. 

You can also import the XML file, which contains the language variables. Experience Manager Guides only imports the language variables that are already defined, including both application and user variables. It does not import any variables that are not already defined. 

### Export language variables

To export the language variables for a language, select the language from the dropdown and select **Export** <img src="./assets/language-variable-export-icon.svg" alt="export icon" width="25">. 
It creates an XML file with the format `language_variable_<ln>` where `<ln>` is the code of the selected language. For example, `language_variable_en.xml` for English and `language_variable_fr.xml` for French.

>[!NOTE]
> 
>If you have any unsaved changes in the language variables, you cannot export them. Save the changes to view the enabled **Export** <img src="./assets/language-variable-export-icon.svg" alt="import icon" width="25"> icon. 

### Import language variables

 To import the language variables:

1. Select a language from the dropdown and select **Import** <img src="./assets/language-variable-import-icon.svg" width="25">. 
2. Browse and select the XML, which contains the language variables. For example, language_variable_en.xml.
You can import XML files in the following format:

```
<?xml version="1.0" encoding="UTF-8"?>
<variables>    
<variable id="note-important">Important: </variable>    
<variable id="note-caution">Avertir: </variable>    
<variable id="image-with-text">Text and image &lt;img src=&quot;/content/dam/assets/images/image_with_text.png&quot; /&gt; </variable> 
</variables> 
```

The variables with the same ID are imported once you import the file. The values for the variables in the selected language are updated with those in the XML file.  A message about the number of variables updated is displayed. 

>[!NOTE]
> 
><ul><li>If the file isn't an XML file, or if the file contains an incorrect format that doesn't map with the language variables, you view an error that there is an issue with the XML file. 
><li>If the file contains no variables with the same ID, you view a warning that no matching language variable is found in the imported file.

### Options for a language variable

Hover over the variable to view the **Options** menu for it.
 
<img width="550" alt="options menu for language variables" src="./assets/language-variable-user-options.png"> 

*Use the **Options** menu to  delete, preview, or duplicate a language variable.*

You can preview both application and user variables. To view how the variable's value is displayed in the output, select **Preview** from the **Options** menu of the selected variable. 
You can also choose to **Delete** or **Duplicate** the user variables. Deleting a variable from one language automatically deletes it from all languages.

### Edit or revert the application variables

You can also edit the values for an application variable. Later, you can revert an application variable to the original value. **Revert Variable** <img src="./assets/application-variable-revert.svg" width="25">  appears for an application variable with a changed value. 

## Use language variables in the output templates

You should add language variables in your localized documents. You can insert these language variables within the page layout that appears across different pages in your localized documents. For example, you can add the language variable for the `author-name` that appears in the page layout’s header area (or any other part like the footer or body). 



<img alt="page-layout of a pdf" src="./assets/language-variable-page-layout.png" width="550">


*The author and the brand name localized in the PDF output generated for the French language.* 

To insert a language variable like your `copyright-label` in the header area, perform the following steps:

1. Open the required page layout for editing.

    >[!NOTE]
    >
    > View [Customize a page layout](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) section for opening a page layout for customization or editing.

1. Select the header to make it active to insert a variable.
1. Select **Insert Variable**  <img src="./assets/insert-language-variable.svg" width="25"> in the toolbar. 
1. In the **Insert Variable** pop-up, select the name of the language variable to be inserted and click **Insert** to insert it in the header area.

    >[!NOTE]
    >
    > You can also enter the search string in the text box. The variable names containing the given string are filtered and displayed in the list. 
    > The selected language variable is inserted in the header area. 



<img alt="insert variable in the header area" src="./assets/language-variable-header.png" width="550">
 
 *The `copyright-label` added in the header area.*

### Apply content style to language variables

Besides the value you assign to a language variable, you can also use HTML tags to display the variable value in specific formatting. For example, you can display the value of the `publisher-label` in bold.

- You can also format the styles of the values using <span> tag. For example, using the page-number language variable, you can display the page number in Roman number format in English and specify the format for other languages. 

  Value for English: 
`<span data-field="page-number" data-format="upper-roman">1</span>`

  Value for Tamil:
`<span data-field="page-number" data-format="tamil">1</span>`

Similarly, you can add language variables and format other fields listed in the Insert Fields feature of the page layouts. For more details on adding fields, view [Add fields and metadata](../native-pdf/design-page-layout.md#add-fields-metadata). 

- You can also add localized images in the values. For example, you can add an image icon in the chapter-number language and get localized images of the icon in the PDF output. 

    For English, the variable value for an image can be like `<img src="banner-en.jpg">`, and for the same variable in German, it can be `<img src="banner-de.jpg">`. So, it picks up the images depending on the language.

## Localize the strings using CSS styles

Using CSS styles, you can also localize the strings used in Autonumber like Chapter, Section, Figure, and Table. As these strings come from CSS files, you cannot localize them using language variables. To localize these strings, you can create CSS styles for each language in which you want to localize them. 
For example, you can use the following CSS to display the Chapter prefix and the corresponding number format in various languages. 
For example, you can use the following CSS to display Chapter as Hoofdstuk in German and the chapter number in decimal format. While for Japanese, you can use the Japanese number format to show the chapter numbers in the TOC.

```
// for English
h1:before {
  counter-increment: h11;
  content: "Chapter " counter(h11, decimal)".";
}

// for German
:root:lang(de) h1:before {
  content: "Hoofdstuk " counter(h11, decimal)".";
}

// for Japanese
:root:lang(ja) h1:before {
  content: "章 " counter(h11, japanese-formal)".";
}
```

The following screenshots display the strings localized in German and Japanese PDF output .
 
 <img alt=" japanese output with language variable" src="./assets/localize-chapter-german.png" width="550">

 

 <img alt="German output with language variable" src="./assets/localize-chapter-japanese.png" width="550">



### Format the prefixes 

Using CSS styles, you can also format the prefixes. For example, you can format the label `Note` to appear in red color in the PDF output of various languages.

```
.note .prefix-content 
{
color: red;
} 
```
