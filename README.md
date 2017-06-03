# MongoDB by Example

1. Import data into the collection (shell)

    ```bash
    mongoimport --db <DATABASE_NAME> --collection <COLLECTION_NAME> --drop --file <YOUR_JSON_FILE>.json
    ```

__Note.__ If JSON file is not generated by `mongoexport` then use `--jsonArray` option in your _mongoimport_ command.
    
    
    mongoimport --db <DATABASE_NAME> --collection <COLLECTION_NAME> --drop --file <YOUR_JSON_FILE>.json --jsonArray
    