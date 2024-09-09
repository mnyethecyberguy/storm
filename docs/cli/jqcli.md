# jq CLI Cheat Sheet

## Installation

=== "Debian / Ubuntu"
    
    ``` bash
    sudo apt update
    sudo apt install jq
    ```

=== "Windows"

    On Windows, you can download the executable from the `jq` website.  You will need to add the executable to your PATH environment variable.

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

## Mapping & Transforming


## Additional References
https://jqlang.github.io/jq/
https://github.com/jqlang/jq