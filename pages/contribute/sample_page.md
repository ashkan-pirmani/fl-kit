---
page_id: sample_page
title: Title of the sample page
description: This is a description
page_citation: true

search_exclude: true # note we want to exclude this "sample" page

contributors: [Ashkan Pirmani, Goran Vinterhalter]
affiliations: [VIB, KU Leuven]

related_pages:
  your_tasks: [data_steward, researcher]
  tool_assembly: [infrastructure, wrangling]
  
training:
  - name: Example of a generic link (no registry mentioned)
    url: https://tess.elixir-europe.org/search?q=data+governance#materials
  - name: Data Governance Training
    registry: TeSS
    url: https://tess.elixir-europe.org/search?q=data+governance#materials
    
dsw:
- name: Do you have data governance policies in place?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac
  
faircookbook:
- name: Data Governance Framework
  url: https://w3id.org/faircookbook/FCB034
---

Linking to other pages:
- This is how we link to other pages (in this case this page): [this sample page](sample_page).
- This is an example of a tool {% tool "zotero" %}.
  - [Click here for how to add a new tool](tool_resource_update)
- This is an example of a cite {% cite Pirmani2024FL4E %}.
    - [Click here for how to add new citations](style_guide#bibliography)
    

## Bibliography
This is how we can include a bibliography in the page

{% bibliography --cited %}

## Page source code
Source code of this page:
 {% raw %}
```markdown
---
page_id: sample_page
title: Title of the sample page
description: This is a description
page_citation: true

search_exclude: true # note we want to exclude this "sample" page

contributors: [Ashkan Pirmani, Goran Vinterhalter]
affiliations: [VIB, KU Leuven]

related_pages:
your_tasks: [data_steward, researcher]
tool_assembly: [infrastructure, wrangling]

training:
- name: Example of a generic link (no registry mentioned)
  url: https://tess.elixir-europe.org/search?q=data+governance#materials
- name: Data Governance Training
  registry: TeSS
  url: https://tess.elixir-europe.org/search?q=data+governance#materials

dsw:
- name: Do you have data governance policies in place?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac

faircookbook:
- name: Data Governance Framework
  url: https://w3id.org/faircookbook/FCB034
---

Linking to other pages:
- This is how we link to other pages (in this case this page): [this sample page](sample_page).
- This is an example of a tool {% tool "zotero" %}.
  - [Click here for how to add a new tool](tool_resource_update)
- This is an example of a cite {% cite Pirmani2024FL4E %}.
  - [Click here for how to add new citations](tool_resource_update)


## Bibliography
This is how we can include a bibliography in the page

{% bibliography --cited %}
``` 
{% endraw %}