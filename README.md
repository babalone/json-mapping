# json-mapping
a tool to to mappings of one json-format to another using jsonpath

## Idea
In the last years I was many times confronted with "copy this value V at key X to the new dataset at key Y with value modify(V)". All based on [JSON](https://en.wikipedia.org/wiki/JSON). Goal of this library is to build a tool that uses [json-path](https://github.com/json-path/JsonPath) to map these values.
Using this library might look like
```java
someThing.map("$.someKey.something[0]", "$.someKey", this::someFunction);
```
which would map 
```json
{
  "bla": 23,
  "blub": 42,
  "someKey": {
    "foo": "a",
    "bar": "b",
    "something": [2, 3, 5, 7, 11, 13]
  }
}
```

to a structure containing
```
{
  ...
  "someKey": someFunction(2)
  ...
}
```

## TODO
- First some research has to be done on if this was already implemented.
- is the existing solution sufficient?
- is the existing license sufficient?
- after evaluation still seeing necessasity for this library? If no then stop here and help there, if still wanted continue
-- find a good way to do the mapping.
-- document it with many examples
-- test according to documentation and maybe adapt documentation
