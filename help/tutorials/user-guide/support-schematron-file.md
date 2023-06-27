---
title: Support for Schematron files
description: Learn how to validate your topics with scehmatron
exl-id: e5912fa1-af26-42f4-b5e5-a6d2afd45bc8
---
# Support for Schematron files

"Schematron" refers to a rule-based validation language used to define tests for an XML file. Web editor supports Schematron files. You can import the Schematron files and also edit them in Web Editor. Using a Schematron file you can define certain rules and then validate them for a DITA topic or a map.

>[!NOTE]
>
> Web editor supports ISO Schematron.


## Import Schematron files

Perform the following steps to import the Schematron files:

  ![](images/scematron-panel-add.png){width="300" align="left"}

1. Navigate to the required folder (where you want to upload the files) in *Repository View*.
1. Click the **Options** icon to open the context menu and choose **Upload Assets**.
1. In the **Upload Assets** dialog, you can change the destination folder in the **Select Asset Folder** field.
1. Click **Choose Files** and browse to select the Schematron files. You can select one or more Schematron files and then click **Upload**.

## Validate a DITA topic or map with Schematron

After importing Schematron files, you can edit them in the Web Editor. You can use the Schematron files to validate the topics or a DITA map. For example, you can create the following rules for a DITA map or topic:

* A title is defined for a DITA map.
* A short description of a certain length has been added.
* There should be at least one topicref in the map.

When you open a topic in the Web Editor, a Schematron Validation panel appears in the right. Perform the following steps to add and validate a topic or map with a Schematron file:
![](images/schematron-validate.png){width="300" align="left"}

1. Click the Schematron icon (), to open the Schematron panel.
1. Use Add Schematron File to add Schematron files. 
1. If the Schematron file has no errors, it is added and listed in the Validation panel. An error message is displayed for the Schematron file containing errors.
    >[!NOTE]
    >
    >You can use the cross icon near the Schematron file name to remove it.
1. Click Validate with Schematron to validate the topic. 

    * If the topic breaks no rules, the validation success message is displayed for the file.
    * If the topic breaks a rule, for example, if it doesn't contain a title and is validated for the above given Schematron, it displays a validation error.

1. Click the error message to highlight the element containing the error in the opened topic/map.

The Schematron support in the Web Editor helps you in validating the files against a set of rules and maintaining consistency and correctness across the topics.

## Use assert and report statements to check for rules{#schematron-assert-report}

AEM Guides also supports the assert and report statements in Schematron. These statements help you validate your DITA topics.

### Assert statement

An assert statement  generates a message when a test statement evaluates to false. For example, if you want your title to be bold, you can define an assert statement for it.

```XML
<sch:rule context="title"> 
    <sch:assert test = "b"> Title should be bold </sch:assert>
  </sch:rule>
```

When you validate your DITA topics with the Schematron, you get a message for the topics where the title is not bold.

### Report statement

A report statement generates a message when a test statement evaluates to true. For example, if you want the short description to be less than or equal to 150 characters, you can define a report statement to check the topics where the short description is more than 150 characters. 
When you validate your DITA topics with the Schematron, you get a complete report of the rules where the report statement evaluates to true. So, you get a message for the topics where the short description is more than 150 characters. 

 
```XML
<sch:rule context="shortdesc"> 
        <sch:let name="characters" value="string-length(.)"/> 
        <sch:report test="$characters &gt; 150">  
        The short description has <sch:value-of select="$characters"/> characters. It should contain more than 150 characters.      
        </sch:report>   
    </sch:rule> 
```

>[!NOTE]
>
> Use only Xpath 2.0 expressions while writing the Schematron rules.

## Use Regex expressions{#schematron-regex-espressions}

You can also use Regex expressions to define a rule with matches() function and then perform validation using the Schematron file. 

For example, you can use it to display a message if the title contains only one word.  

```XML
<assert test="not(matches(.,'^\w+$'))"> 
No one word titles.
</assert>  
```
 

## Define abstract patterns{#schematron-abstract-patterns} 

AEM Gudies also supports abstract patterns in Schematron. You can define generic abstract patterns reuse these abstract patterns.  You can create placeholder parameters that specify the actual pattern. 


Using abstract patterns can simplify your Schematron schema by reducing the duplication of rules and making it easier to manage and update your validation logic. It can also make your schema easier to understand, as you can define complex validation logic in a single abstract pattern that can be reused throughout the schema. 


For example, the following XML code creates an abstract pattern and then the actual pattern refers to it using the id.  
 
```XML
<sch:pattern abstract="true" id="LimitNoOfWords"> 

<sch:rule context="$parentElement"> 

<sch:let name="words" value="string-length(.)"/> 

<sch:assert test="$words &lt; $maxWords"> 

You have <sch:value-of select="$words"/> letters. This should be lesser than <sch:value-of select="$maxWords"/>. 

</sch:assert>  

<sch:assert test="$words &gt; $minWords"> 

You have <sch:value-of select="$words"/> letters. This should be greater than <sch:value-of select="$minWords"/>. 

</sch:assert>  

</sch:rule> 

</sch:pattern> 

<sch:pattern is-a="LimitNoOfWords" id="extend-LimitNoOfWords"> 

<sch:param name="parentElement" value="title"/> 

<param name="minWords" value="1"/> 

<param name="maxWords" value="8"/> 

</sch:pattern> 
```
