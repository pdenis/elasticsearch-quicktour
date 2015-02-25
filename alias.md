Alias
=====

Create index foo : "POST /foo"​
​
Create alias foo_alias for index foo : "PUT /foo/_alias/foo_alias"​
​
Create index new_foo : "POST /new_foo"​
​
Switch alias :​
​
```json
POST /_aliases​
{​
   "actions": [​
     { "remove": ​
        { "index": "foo", "alias": "foo_alias" }​
     },​
     { "add": ​
        { "index": "new_foo", "alias": "foo_alias" }​
     }​
   ]​
}​
```