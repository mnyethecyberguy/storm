# jq CLI Cheat Sheet

## Installation

=== "Debian / Ubuntu"
    
    ``` bash
    sudo apt update
    sudo apt install jq
    ```

=== "Windows"

    ``` pwsh
    winget install jqlang.jq
    ```

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

[^1]: https://jqlang.github.io/jq/
[^2]: https://github.com/jqlang/jq