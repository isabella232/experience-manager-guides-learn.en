---
title: Configure the JSON-based mapping between a topic and a content fragment model.
description: Learn how to configure the JSON-based mapping between a topic and a content fragment model.
exl-id: 18abf538-7e88-4b9c-a18d-5d1eacd57ab0
---
# Create a mapping between a topic and a content fragment

AEM Guides provides the feature to create a JSON-based mapping between a topic and a content fragment model. You can use this mapping to publish content present in some or all elements within a topic to a content fragment. 

1. To download the *contentFragmentMapping.json*, log into Adobe Experience Manager as an administrator.
1. Select the Adobe Experience Manager link at the top and choose **Tools**.
1. Select Guides from the list of tools and select the **Folder Profiles**.
1. Select the **Global Profile** tile.
1. Select the **XML Editor Configuration** tab and select the **Edit** icon on the top.
1. Select the **Download** icon to download the *contentFragmentMapping.json*  file on your local system. You can then make changes to the file and then upload the same.

1.  You need to follow the following validations:

    1. It should be a JSON file
    2. It should contain an array containing at least one object, and every object should contain the following:


        `"name": string `

        `"mapping": array`

        Each object of mapping must contain the following:
        
       `"modelField": string`

        `"xpath": string`

        `"outputType": string`
1. Save the file and upload it.

Sample file:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

 You can publish the whole topic with the default mapping. Select the `Full Topic` mapping from the dropdown in the **Publish As Content Fragment** dialog box and have "topicData" field in the content fragment model.
