## Purpose

Repository for hosting GitHub Pages
Programming section of personal website at www.rhysshea.com


## Layout

Built using Jekyll - a static site generator (written in Ruby)

Using tagging, pages are created based on a default template and pull in resources with the corresponding tags

For example a `%machine-learning%` tag will pull a sidebar, navigation bar, and a list of related articles for a taglogic contents table

`_includes` 
- using an `include` tag allows insertion of a resource from the _includes folder
- this site has includes for sidebars and top navigation bars, as well as the taglogic for each to dynamically pull in the correct resources for a page

`_layouts` 
- templates for different types of pages that the site contains
- in this case there are templates for articles, posts, and the default template, which is the base template that others inherit from

`_data`
- contains well-formatted site data
- this contains different sidebar information for varying sections of the site

Article data for different topics are stored in directories with corresponding names
- `algorithms`
- `ctf`
- `machine-learning`
- `programming`