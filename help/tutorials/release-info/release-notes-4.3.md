---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides 4.3.0 release
description: Learn about the bug fixes and how to upgrade to  4.3.0 releases of Adobe Experience Manager Guides
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
---
# 4.3.0 release of Adobe Experience Manager Guides (July 2023)

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version 4.3.0 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more information about the new features and enhancements, see [What's new in 4.3.0 release of Adobe Experience Manager Guides](./whats-new-4.3-release.md).

## Upgrade to 4.3.0 release of AEM Guides


You can easily upgrade your current version of AEM Guides to version 4.3.0. Before you proceed with upgrading to version 4.3.0 of AEM Guides, you must consider the following points:
You can upgrade your current version of AEM Guides to version 4.3.0

- If you are using version 4.2 or 4.2.x then you can directly upgrade to version 4.3.0.
- If you are using version 4.1 or 4.1.x then you need to upgrade to version 4.2 or 4.2.x before upgrading to version 4.3.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.0.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade AEM Guides section in the product-specific installation guide.



>[!NOTE]
>
>You must install AEM service pack before upgrading AEM Guides version.

For details, see [Upgrade instructions](../install-guide/upgrade-xml-documentation.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.3.0 release. 

### Adobe Experience Manager

**4.3.0 Non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15, or 14

**4.3.0 UUID**
Version 6.5 Service Pack 18, 17, 16, 15, or 14

For more details, see the *Technical requirements* section in the Install and configure Adobe Experience Manager Guides guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
|4.3.0 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
| 4.3.0 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.3.0 (Non-UUID)|  2.3-regular-5| 2.3-regular-5 |  1.6 | 1.6  |
| 4.3.0 (UUID) | 3.0-uuid-4|3.0-uuid-3 |2.3 | 2.3  |
|  |  |   |  

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- The topic file isn’t unlocked in the Web Editor, although the Unlock the File option and the Don’t Save option are selected. (12558)
- Unable to checkout a file in the Web Editor, despite choosing the NO option to discard the changes before check-in. (12557)
- The tooltips for the Lock & Unlock file icons in the main toolbar within the Web Editor are not consistent with the icons displayed in the Repository View.(12555)
- Cancel check out and Unlock option is displayed for a file in the Web Editor that isn’t yet checked out in Map View. (12556)
- Unable to select the PDF assets in the existing "topicref" links. (12477).
- On doing a merge and split in the tables, AEM Guides 4.2 generates additional table cells. (11793)
- In the Repository View, the topics or images cannot be dragged after using the Search/Filter functionality. (12396)
- Search results are disabled in the Find and Replace panel after opening one searched file. (12142)
- The “8” number key on the side keyboard isn’t working in the AEM Guides editor. (12106)
- Inline/Display attributes do not show up in the Layout view of the Web Editor. (12498)
- Global Profile UI config does not match with Folder Profile. (11970)
- Content references are broken when DITA files are copied and pasted. (11959)
- Not able to edit content fragment in column view with AEM Guides installed. (7342)
- Content is lost when an unwrapped xref is under a sub element tags. (12532)
- Approval workflow does not work when docstate is changed to "end state" from File properties of the right panel. (11026)
- Asset UI | In the List view, the overlayed available columns are not mergeable. (11528)
- Keyref is not resolved in the map view. (11490)
- Top menu does not appear when navigating through XML editor. (10868)
- `conref` in ph tag | The browse dialog shown is incorrect. (9481)
- Local links to other elements are not resolved in Web Editor. (8790)
- Matches() function do not work in schematron feature. (11224)



### Management

- The "title" field in DITA map metadata properties is overwritten by `<title>` element for the map. (10702)
- When trying to open or update the version of topics in the baseline, the "Fetching information from the server" loader runs indefinitely.(12478)


### Review

- New Review UI | The conditions highlight, and show hide work differently than how they work in Web Editor. (11628)

### Publishing

- Publishing fails on renaming a Native PDF preset. (12564)
- Duplicating a Native PDF template duplicates to the default template location instead of the provided custom template location. (12563)
- Native PDF | The language metadata cannot be set in the generated PDF to comply with WCAG 2.0. (12407)
- Publishing to AEM site fails when reading temp files from pod that may have refreshed or restarted. (12113)
- Native PDF | Custom attributes are not propagated to temporary HTML or PDF engine. (DXML-12005)
- Native PDF |  Java OutOfMemoryError occurs on publishing large content. (11789)
- Native PDF | Xref is printing the contents of href topic title instead of the Xref label. (11322)
- Native PDF | Unable to save the PDF template settings. (10751)
- Native PDF | The text extends beyond the column width on including multiple xrefs. (10876)
- Native PDF | `<note>``</note>` element does not generate extra span title of its type. (10549)
- JSON output | The `fmUuid` property on the jcr:content node of JSON is different from the "id" inside the JSON. (11564)
- JSON Output | If the map and topic with same filename are present, JSON for the map is removed. (11524)

## Known issue

Adobe has identified the following known issue for AEM Guides 4.3.0 release: 

- Common page layout defined in the Basic template is not getting applied as default template.

    Workaround:
    Add Common page layout as front and back cover then it starts coming for every page.
- Issue occurs in Site Search while searching in the AEM site output page on AEM Service Pack 16 or 17. 
    
    Workaround:
 
    1. Open file with the path: `/libs/foundation/components/search/search.jsp` in `crx/de`
    1. Replace line number 234 with the following code:

        ```
        <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>

        *(Add the missing closing anchor tag at the end).
        ```
        
    1. Save the file.
