## extracted_corporationwiki.json

### PyTransforms
#### _Values_date_iso_
From column: _corporation_records / Unfold: label / date filed: / Values_
>``` python
return str(pt_format_date(getValue("Values"),"day,mmdd,yyyy"))
```

#### _filing_body_uri_
From column: _corporation_records / filing_body_
>``` python
import re,string
s = getValue("filing_body").encode('UTF-8').lower()
if s!= '' and s!=None:
    regex = re.compile('[%s]' % re.escape(string.punctuation))
    return "gov_organizaion/"+str(regex.sub('', s)).replace(" ","_")
else:
    return ''
```

#### _permit_uri_
From column: _corporation_records / permit_uri_
>``` python
return uuid_uri('governmentpermit/')
```

#### _organization_uri_
From column: _name_
>``` python
return uri_from_fields('organization/', getValue("name"))
```

#### _state_uri_
From column: _corporation_records / Unfold: label / state: / Values_
>``` python
return uri_from_fields('place/unitedstates/',getValue("Values"))
```

#### _role_uri_
From column: _people / name_
>``` python
return uri_from_fields("person/",getValue("entityid"))
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Values_ | `schema:name` | `memex:Identifier1`|
| _Values_ | `schema:name` | `schema:State1`|
| _Values_ | `schema:subtype` | `schema:Organization1`|
| _Values_ | `schema:status` | `schema:GovernmentPermit1`|
| _Values_date_iso_ | `schema:validFrom` | `schema:GovernmentPermit1`|
| _city_ | `schema:addressLocality` | `schema:PostalAddress1`|
| _filing_body_ | `schema:valueName` | `schema:Organization2`|
| _filing_body_uri_ | `uri` | `schema:Organization2`|
| _name_ | `schema:name` | `schema:Person1`|
| _name_ | `schema:legalName` | `schema:Organization1`|
| _organization_uri_ | `uri` | `schema:Organization1`|
| _permit_uri_ | `uri` | `schema:GovernmentPermit1`|
| _role_uri_ | `uri` | `schema:Role1`|
| _state_ | `schema:addressRegion` | `schema:PostalAddress1`|
| _state_uri_ | `uri` | `schema:State1`|
| _url_ | `schema:url` | `schema:Organization1`|
| _values_ | `schema:name` | `schema:PostalAddress1`|
| _values_ | `memex:hasType` | `schema:Role1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `memex:Identifier1` | `memex:hasType` | `xsd:/thesaurus/government_permit/identifier/stateID`|
| `schema:GovernmentPermit1` | `memex:identifier` | `memex:Identifier1`|
| `schema:GovernmentPermit1` | `schema:audience` | `schema:Organization1`|
| `schema:GovernmentPermit1` | `schema:issuedBy` | `schema:Organization2`|
| `schema:GovernmentPermit1` | `schema:validIn` | `schema:State1`|
| `schema:Organization1` | `schema:address` | `schema:PostalAddress1`|
| `schema:Organization1` | `schema:employee` | `schema:Role1`|
| `schema:Organization1` | `memex:operatingPermit` | `schema:GovernmentPermit1`|
| `schema:Role1` | `schema:employee` | `schema:Person1`|
