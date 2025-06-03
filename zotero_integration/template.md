---
category: literaturenote
tags: {% if allTags %}{{allTags}}{% endif %}
citekey: {{citekey}}
status: unread
dateread:
---
# Notes

{% if markdownNotes %}
{{markdownNotes}}
{% else %}
_No personal notes yet._
{% endif %}

# Key questions



---
> [!Cite]
> {{bibliography}}

> [!Synth]
> **Contribution**::  
>   
> **Related**:: {% for relation in relations | selectattr("citekey") %} [[@{{relation.citekey}}]]{% if not loop.last %}, {% endif %}{% endfor %}

> [!Metadata]
> **Authors**:: 
{%- for type, creators in creators | groupby("creatorType") %}
{%- for creator in creators -%}
{%- if creator.name -%}
{{ creator.name }}{% if not loop.last %}, {% endif %}
{%- else -%}
{{ creator.lastName }}, {{ creator.firstName }}{% if not loop.last %}, {% endif %}
{%- endif -%}
{%- endfor -%}
{%- endfor %}
> **Title**:: {{title}}  
> **Year**:: {{date | format("YYYY")}}  
> **Citekey**:: {{citekey}}  
{%- if itemType %}> **Item Type**:: {{itemType}}{% endif %}
{%- if itemType == "journalArticle" %}> **Journal**:: *{{publicationTitle}}*{% endif %}
{%- if volume %}> **Volume**:: {{volume}}{% endif %}
{%- if issue %}> **Issue**:: {{issue}}{% endif %}
{%- if itemType == "bookSection" %}> **Book**:: {{publicationTitle}}{% endif %}
{%- if publisher %}> **Publisher**:: {{publisher}}{% endif %}
{%- if place %}> **Location**:: {{place}}{% endif %}
{%- if pages %}> **Pages**:: {{pages}}{% endif %}
{%- if DOI %}> **DOI**:: {{DOI}}{% endif %}
{%- if ISBN %}> **ISBN**:: {{ISBN}}{% endif %}

> [!Link]
{%- for attachment in attachments | filterby("path", "endswith", ".pdf") %}
> [{{attachment.title}}](file://{{attachment.path | replace(" ", "%20")}})
{%- endfor %}

> [!Abstract]
{%- if abstractNote %}
> {{abstractNote | replace("\n", "\n> ") }}
{%- else %}
> *No abstract available.*
{%- endif %}
---

# Annotations

### Imported: {{importDate | format("YYYY-MM-DD h:mm a")}}

{% for a in annotations %}
{%- if a.type == "highlight" %}
<mark style="background-color: {{a.color}}">Quote</mark>  
> {{a.annotatedText | replace("\n", "\n> ") }}
{% endif %}
{%- if a.type == "text" %}
**Note**  
> {{a.text | replace("\n", "\n> ") }}
{% endif %}
{% endfor %}

