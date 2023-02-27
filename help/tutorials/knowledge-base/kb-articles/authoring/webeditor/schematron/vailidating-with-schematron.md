
# Controlling quality of content within web-editor

This article gives an overview of validation possibilities within AEM Guides web-editor. 
By design web-editor leverages the DITA schema setup in the system to enforce users to create DITA compliant content. With this, all the content stored in the sytem is structured, reusable and valid DITA content.

Beyond support for DITA rules, web-editor also supports validation of content based on "*Schematron*" rules.

"*Schematron*" refers to a rule-based validation language used to define tests for an XML file. You can import the Schematron files and also edit them in Web Editor. Using a "Schematron" file you can define certain rules and then validate them for a DITA topic or a map. Schematron rules can ensure consistency of XML structure by imposing restrictions defined as rules. These restrictions are driven by SMEs who own the quality and consistency of the content. 

    NOTE: Web editor supports ISO Schematron. 


## Knowing how "Schematron" works in web-editor

### Configuring Schematron rules

Refer section "Support for Schematron files" in the [User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Can you run validation manually?

Yes, as a author/user while creating content you can use the Schematron panel in webeditor to upload a schematron file and run validations on the file open in editor.

![Choose Schematron file](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)

![Run validation](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)

    For this to work, folder profile admin must allow all users to add Schemtron files in Validation panel

### Enforce validation rules on file save

Webeditor settings allows the power users to setup Schematron rules/files that will be executed each time a user updates the content. For more details refer section "Validation" in [User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Set rules from web-editor settings](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### Supported rules

Current version of AEM Guides support validation using "Assertion" based rules only. (see [asset vs report](https://schematron.com/document/205.html))
Any rules based on "Reports" are not supported yet. 


### Samples and more help on Schematron rules

#### Sample use cases

- Check if a link is external and if it has scope "external"
    ```
    <sch:pattern>
        <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
            <sch:assert test="@scope = 'external' and @format = 'html'">
                All external xref links must be with scope='external' and format='html'
            </sch:assert>
        </sch:rule>
    </sch:pattern>
    ```

- Check if there is atleast one "topicref" in a map or atleast one "li" under a "ul"
    ```
    <sch:pattern>
        <sch:rule context="map">
            <sch:assert test="count(topicref) > 0">
                There should be atleast one topicref in map
            </sch:assert>
        </sch:rule>

        <sch:rule context="ul">
            <sch:assert test="count(li) > 1" >
                A list must have more than one item.
            </sch:assert>
        </sch:rule>
    </sch:pattern>
    ```

- The "indexterm" element should always be present in a "prolog"
    ```
    <sch:pattern>
        <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
            <sch:assert test="ancestor::node()/local-name() = 'prolog'">
                The indexterm element should be in a prolog.
            </sch:assert>
        </sch:rule>
    </sch:pattern>
    ```

#### Resources

- Understanding  [Schematron basics](https://da2022.xatapult.com/#what-is-schematron)
- More about [Assertion rules in Schematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Sample Schematron file](../../../assets/authoring/sample_schematron.sch) 