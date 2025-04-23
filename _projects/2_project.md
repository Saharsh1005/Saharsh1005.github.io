---
layout: page
title: SafeZoneUofI
description: Developed a dedicated platform for sharing and reporting of crime information and fostering a safer environment around UIUC campus area.
img: 
importance: 3
category: Software
giscus_comments: false
---

# UIUC Crime Web Application
Website [Link](https://cs411-puredata.uc.r.appspot.com/)

### Problem Statement & Motivation

To enhance safety and convenience in Urbana-Champaign, there is a need for an improved way to share information about security incidents around the University of Illinois at Urbana-Champaign (UIUC). The current Daily Crime Log and Daily Crime Log Map provide valuable data but lack user-friendly features. Our proposed solution is a comprehensive crime reporting web application designed to transform the accessibility and presentation of critical information, empowering the community to make informed decisions for personal safety. [Figma Link](https://www.figma.com/file/Tz0FeMd87schOVflPeQ2Rc/SafeZone-UofI?type=design&node-id=1669%3A162202&mode=design&t=1w1nHRWBZ9Fed3aL-1)


### User Problems being solved

- **Improve data accessibility:** The current tabular format of the Daily Crime Log is ineffective. Our application provides a more user-responsive framework for better data accessibility, ensuring informed decision-making for personal safety.

- **Community Safety:** By enhancing access to and understanding of campus crime data, the application contributes to the safety and security of the entire Urbana-Champaign community.

### Basic interactions our app supports in service of our goal

- **Data Retrieval:** Users can access crime data, including incident reports, locations, and relevant details through the application.

- **Reporting Tips:**  A distinctive feature involves enabling users to report crime tips directly to the police through a submission form, providing an easy and efficient online platform for reporting tips that can be investigated further.


- **Historical Data Visualization:** The app displays historical crime data through charts and visualizations, empowering users with insights into trends and patterns over time.

- **Interactive Mapping:** An interactive map interface allows users to visualize crime incidents for location-based decision-making.

- **User Authentication:** Users and Admins can signup and login to make the most of all our functionalities.

### How our app is different

* Unique Focus: Our app distinguishes itself by specifically catering to the Urbana-Champaign community, offering more relevant and targeted information compared to general platforms like Crimemapping.com or Citizens.
* Data Accuracy and Reliability: Unlike apps allowing user-generated content, such as Citizens, we exclusively rely on official sources for data, enhancing the app's overall reliability.
* Holistic Information Delivery: In contrast to UIUC-specific websites like the Daily Crime Log or Police Blotter, our app provides more comprehensive insights through data visualization rather than presenting raw data alone.
* Reporting Tips: A distinctive feature involves enabling users to report crime tips directly to the police through a submission form, providing an easy and efficient online platform for reporting tips that can be investigated further.

## Citation and References
1. [Daily Crime Log](https://police.illinois.edu/info/daily-crime-log/)
2. [Daily Crime Log Map](https://police.illinois.edu/info/map/)

## Team Information

- Mukta Jaiswal: [muktaj2]
- Palveet Kaur Saluja: [psaluja2]
- Saharsh Sandeep Barve: [ssbarve2]
- Shubham Jayraj Thakar: [sthakar3]
- Sakshil Verma: [sakshil2]
    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
