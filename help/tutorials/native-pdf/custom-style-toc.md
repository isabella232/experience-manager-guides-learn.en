---
title: Native PDF Publish Feature | Apply custom style on TOC entries and topic content 
description: Learn how to create use styleheets and create styles for your content.
---

# Apply custom style on TOC entries and topic content 

At times, you might want to apply custom styling on the TOC entries or a particular topic. This can be achieved by associating an `outputclass` attribute with the `<topicref>` element in your DITA map. Also, in case you want to apply a custom format to an entire topic, then that can also be achieved by extending the attribute's style definition in the CSS.

Let's take an example of a new topic that you want to send for review. For easy identification of the updated topic, you need to add an `outputclass` attribute to the `<topicref>` element in your DITA map and then define a custom styling for the same in the CSS.

In the following example, the *History of flights* topic has been assigned an `outputclass` attribute with the value of `new-topic`. 

<img src="./assets/new-topic-attribute-in-map.png" width=500>

The class definition of the `new-topic` in a CSS can let you define the style for the following items: 
* The main entry in the TOC or mini-TOC
* The title of the topic in the main content
* The entire content of the topic, including the title

Let's see how each of these scenarios can be defined in the CSS. In the following CSS definition of the `new-topic` class, the text color has been changed.

```css
…
.new-topic {
  color: #CC5309
}
…
```

This definition controls the color of the text in the TOC and the topic's title. The following PDF output shows the different color applied on the TOC entry:

<img src="./assets/pdf-output-toc-entry.jpg" width=500>

The topic's title is also styled using the same color. 

<img src="./assets/pdf-output-topic-title.jpg" width=500>

If you want the TOC entry and the topic's title to have different styles, then you can define them separately as shown below:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Finally, you can also apply styles on the entire content within the topic. For this, you need to add a suffix "`-content`" to the class name. In the following example, a change bar has been added on the entire content of the topic:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Using the above styling attributes, a change bar is added to the left of the *History of flight* topic, as shown below:

<img src="./assets/pdf-output-topic-content.jpg" width=500>


