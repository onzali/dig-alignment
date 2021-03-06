## extracted_calguns.json

### PyTransforms
#### _uri_
From column: _crawler_
>``` python
return uri_from_url_timestamp(getValue("url"),getValue("timestamp"))
```

#### _content_clean_
From column: _posts / content_
>``` python
return atf_body_clean(getValue("content"))
```

#### _iso_date_posted_
From column: _posts / date_posted_
>``` python
return iso8601date(getValue("date_posted"),"%m-%d-%Y, %I:%M %p")
```

#### _signature_clean_
From column: _posts / signature_
>``` python
return signature_clean(getValue("signature"))
```

#### _title_clean_
From column: _posts / title_
>``` python
return signature_clean(getValue("title"))
```

#### _post_uri_
From column: _posts / post_id_
>``` python
return atf_article_uri(getValue("url"), getValue("post_id"))
```

#### _user_uri_
From column: _posts / user_id_
>``` python
return calguns_user_uri(getValue("user_id"))
```

#### _location_uri_
From column: _posts / Unfold: label / location / Values_
>``` python
return postal_address_uri(getValue("Values"))
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Values_ | `schema:name` | `schema:PostalAddress1`|
| _content_clean_ | `schema:text` | `schema:WebPageElement2`|
| _iso_date_posted_ | `schema:dateCreated` | `memex:Post1`|
| _location_uri_ | `uri` | `schema:Place1`|
| _organization_uri_ | `uri` | `schema:Organization1`|
| _post_id_ | `schema:name` | `memex:Identifier2`|
| _post_uri_ | `uri` | `memex:Post1`|
| _rawtextdetectedlanguage_ | `schema:inLanguage` | `memex:Thread1`|
| _signature_clean_ | `schema:text` | `schema:WebPageElement3`|
| _title_clean_ | `schema:text` | `schema:WebPageElement4`|
| _topic_id_ | `schema:name` | `memex:Identifier1`|
| _topic_title_ | `schema:text` | `schema:WebPageElement1`|
| _uri_ | `uri` | `memex:Thread1`|
| _url_ | `schema:url` | `memex:Thread1`|
| _user_id_ | `schema:name` | `memex:Identifier3`|
| _user_uri_ | `uri` | `schema:Person1`|
| _username_ | `schema:name` | `schema:Person1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `memex:Identifier1` | `memex:hasType` | `xsd:http://dig.isi.edu/weapons/data/thesaurus/identifier/calguns/thread`|
| `memex:Identifier2` | `memex:hasType` | `xsd:http://dig.isi.edu/weapons/data/thesaurus/identifier/calguns/post`|
| `memex:Identifier3` | `memex:hasType` | `xsd:http://dig.isi.edu/weapons/data/thesaurus/identifier/person/calguns`|
| `memex:Post1` | `memex:hasBodyPart` | `schema:WebPageElement2`|
| `memex:Post1` | `memex:hasSignaturePart` | `schema:WebPageElement3`|
| `memex:Post1` | `memex:hasTitlePart` | `schema:WebPageElement4`|
| `memex:Post1` | `memex:identifier` | `memex:Identifier2`|
| `memex:Post1` | `schema:author` | `schema:Person1`|
| `memex:Post1` | `memex:isPostOf` | `memex:Thread1`|
| `memex:Thread1` | `memex:hasTitlePart` | `schema:WebPageElement1`|
| `memex:Thread1` | `memex:identifier` | `memex:Identifier1`|
| `memex:Thread1` | `schema:publisher` | `schema:Organization1`|
| `memex:Thread1` | `memex:hasPost` | `memex:Post1`|
| `schema:Organization1` | `schema:name` | `xsd:calguns.net`|
| `schema:OrganizationRole1` | `schema:memberOf` | `schema:Organization1`|
| `schema:Person1` | `memex:identifier` | `memex:Identifier3`|
| `schema:Person1` | `schema:location` | `schema:Place1`|
| `schema:Person1` | `schema:memberOf` | `schema:OrganizationRole1`|
| `schema:Person1` | `memex:isAuthorOf` | `memex:Post1`|
| `schema:Place1` | `schema:address` | `schema:PostalAddress1`|
