# jq CLI Cheat Sheet

## Installation


## General Commands

Output a JSON file, in pretty-print format
```
jq . file.json
```

Pretty-print API output
```
curl example.org/api/v1/users | jq .
```

Output all elements from arrays (or all key-value pairs from objects) in a JSON file
```
jq .[] file.json
```

Read JSON objects from a file into an array, and output it (inverse of `jq .[]`)
```
jq --slurp . file.json
```

Output the first element in a JSON file
```
jq .[0] file.json
```


## Additional References
https://jqlang.github.io/jq/
https://github.com/jqlang/jq