AcmeContent
===========

Dummy project with content for Coral CMS

Project structure:

+ configuration (Contains JSON configuration files, can be actually anything - redirections, project specific configuration etc.)
+ content (site content structure)

Content structure:

- Each folder represents a page
- .properties contains page properties
    - Page title is on the first line
    - Blank lines are ignored by the parser
    - Each other line is parsed as key:value properties
        1. First occurence of ':' is found and
        2. Everything before the first occurence of ':' is 'key'
        2. Everything after the first occurence of ':' is 'value' (quotes " are trimmed from the end and beginning of the string)
    - Properties can be written as 'tree_sample_property' and then is inherited by all subpages untill overwritten by 'sample_property' or other 'tree_sample_property'
- .[directory] contains a content of widget area of specific page
    - files within the folder represents a content
    - extensions mark which file parser/renderer needs to be used and can be customized
- .[tree_directory] contains a content of widget area to be inherited by all subpages untill overwritten by .[tree_directory] or .[directory] for specific page(s)
- .sortorder represents and order of sub-pages (or content of widget area)