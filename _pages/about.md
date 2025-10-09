---
permalink: /
title: "Hi! I'm Alvin Zou :D"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am Alvin Zou, currently a second year master's student pursuing a Master's of Science in Robotics at Carnegie Mellon University advised by Maxim Likhachev in the Search Based Planning Lab. My research interests are in path and motion planning, as well as search algorithms. Currently, I am researching on developing planning algorithms that are more memory efficient and run faster than conventional planners. Examples include improving the memory usage of best first search, speeding up A* through parallelization, and making multi agent path finding algorithms more scalable.

More generally, I am passionate about robotics, especially mobile robots and autonomous vehicles!


Research 
======

[Attractor-based Closed List Search: Sparsifying the Closed List for Efficient Memory-Constrained Planning](https://www.ijcai.org/proceedings/2025/1004)

Best-first search algorithms such as A* and Weighted A* are widely used tools. However, their high memory requirements often make them impractical for memory-constrained applications, such as on-board planning for interplanetary rovers, drones, and embedded systems. One popular strategy among memory-efficient approaches developed to address this challenge is to eliminate or sparsify the Closed list, a structure that tracks states explored by the search. However, such methods often incur substantial overhead in runtime, requiring recursive searches for solution reconstruction. In this work, we propose Attractor-based Closed List Search (ACLS), a novel framework that sparsely represents the Closed list using a small subset of states, termed attractors. ACLS intelligently identifies attractor states in a way that enables efficient solution reconstruction while preserving theoretical guarantees on the quality of the solution. Furthermore, we also introduce a lazy variant, Lazy-ACLS, which defers the computation of attractor states until necessary, substantially improving planning speed. We demonstrate the efficacy of ACLS used in conjunction with A*, Weighted A*, and Dijkstra’s searches across multiple domains including 2D and 3D navigation, Sliding Tiles, and Towers of Hanoi. Our experimental results demonstrate that ACLS significantly reduces memory usage, maintaining only 9% of the states typically stored in a Closed list, while achieving comparable planning times and outperforming state-of-the-art approaches. Source code can be found at github.com/alvin-ruihua-zou/ACLS.


Projects
======

{% for post in site.talks reversed %}
{% if post.type == "complete" %}
{% include archive-single-talk.html %}
{% endif %}
{% endfor %}



Education
======
<div class="grid__wrapper">
  <div class="grid__item">
    <div class="archive__item">
      <div class="archive__item-teaser" style="width: 170px; margin-right: 20px; align-items: center;">
        <img src="/images/CMU_logo_287x287.png" alt="Carnegie Mellon University logo" style="width: 100%; height: auto;">
      </div>
      <div class="archive__item-body">
        <h3 class="archive__item-title">Carnegie Mellon University</h3>
        <p>Master of Science in Robotics, 2024-present</p>
        <p>Advisor: Maxim Likhachev</p>
        <p>Search Based Planning Lab</p>
      </div>
    </div>
  </div>
</div>

<div class="grid__wrapper">
  <div class="grid__item">
    <div class="archive__item">
      <div class="archive__item-teaser" style="width: 170px; margin-right: 20px; align-items: center;">
        <img src="/images/CMU_logo_287x287.png" alt="Carnegie Mellon University logo" style="width: 100%; height: auto;">
      </div>
      <div class="archive__item-body">
        <h3 class="archive__item-title">Carnegie Mellon University</h3>
        <p>B.S. in Electrical & Computer Engineering, 2020-2024</p>
        <p>Additional Major in Robotics</p>
      </div>
    </div>
  </div>
</div>



<!-- A data-driven personal website
======
Like many other Jekyll-based GitHub Pages templates, Academic Pages makes you separate the website's content from its form. The content & metadata of your website are in structured markdown files, while various other files constitute the theme, specifying how to transform that content & metadata into HTML pages. You keep these various markdown (.md), YAML (.yml), HTML, and CSS files in a public GitHub repository. Each time you commit and push an update to the repository, the [GitHub pages](https://pages.github.com/) service creates static HTML pages based on these files, which are hosted on GitHub's servers free of charge.

Many of the features of dynamic content management systems (like Wordpress) can be achieved in this fashion, using a fraction of the computational resources and with far less vulnerability to hacking and DDoSing. You can also modify the theme to your heart's content without touching the content of your site. If you get to a point where you've broken something in Jekyll/HTML/CSS beyond repair, your markdown files describing your talks, publications, etc. are safe. You can rollback the changes or even delete the repository and start over -- just be sure to save the markdown files! Finally, you can also write scripts that process the structured data on the site, such as [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb) that analyzes metadata in pages about talks to display [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html).

Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the Academic Pages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring Academic Pages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. -->
