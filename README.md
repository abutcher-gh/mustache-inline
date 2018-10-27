```
NAME
   mustache-inline - Include data as frontmatter of template

SYNOPSIS
   mustache-inline [FILE]

DESCRIPTION
   Separate FILE (or stdin if FILE not specified) into a
   YAML file and mustache template and run mustache with the
   resulting data and template.

   The file must start with a line containing only three
   dashes marking the start of the data block.  The data
   block is delimited by a terminating line of three dashes.

   The rest of the file is the mustache template.

EXAMPLE
   mustache-inline <<EOF
   ---
   list:
     - {test: data}
     - {test: more data}
     - {test: and more}
   ---
   {{#list}}
   : {{test}} {{test}}
   {{/list}}
   EOF
   : data data
   : more data more data
   : and more and more
```
