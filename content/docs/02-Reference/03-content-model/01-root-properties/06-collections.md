---
title: collections
weight: 60
---

# Root property: collections

The ```collections``` property is optional. It can define an array with one or more
collections with pages which will get their own navigation item in the PoppyGo
Content Menu. In the above example there is a Collection Blog configured
containing blog pages in the folder _content/blog/_. Below the properties of a
single collection dictionary.

| property   | value type                    | optional  | description                                                                                                                            |
|------------|-------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| key        | string                        | mandatory | Keys are for internal use and must be unique                                                                                           |
| dataformat | string: yaml, toml,json       | mandatory | Defines the output format of the frontmatter block. Collections can only handle markdown files. the outputs regards to the frontmatter |
| extension  | ???                           | mandatory | ???                                                                                                                                    |
| title      | string                        | mandatory | The title of this page in the menu and when PoppyGo App refers to this page                                                            |
| file       | string: relative path to file | mandatory | The path to the file. This is the data storage. Can be data/somefile.{json,toml,yaml} or content/somefile.md                           |
| itemtitle  | string                        | mandatory | The singular name of the collection items                                                                                              |
| folder     | string: relative path to dir  | mandatory | The path to the directory containing all files with the configured extension.                                                          |
| fields     | array of dictionaries         | mandatory | These are the form input fields.                                                                                                       |


## Example

{{< code-toggle file="./model/base" >}}
collections:
  - dataformat: yaml
    extension: md
    fields:
      - key: title
        title: Title
        type: string
      - key: mainContent
        title: Main content
        type: markdown
      - key: publishdate
        title: Publishdate
        type: hidden
      - key: tags
        title: Tags
        type: chips
    folder: content/post/
    itemtitle: Post
    key: post
    title: Posts
{{</ code-toggle  >}}
