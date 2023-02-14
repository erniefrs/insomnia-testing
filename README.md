# insomnia-testing

## Git Sync
This repo can be added as a design document in Insomnia by using the Git Sync feature and cloning this repo. These design documents, however, are OpenAPI specs which Insomnia does *not* have a visual editor for.  
<img width="485" alt="image" src="https://user-images.githubusercontent.com/34193363/218792101-aedce980-aeb4-4776-9387-751484f714fe.png">

## Importing
A better option for editing would be to import/export collections. You can import the [hightouch-collection.json](./hightouch-collection.json) file in this repo using Insomnia's file import feature.

<img width="187" alt="image" src="https://user-images.githubusercontent.com/34193363/218792378-e74cfa52-54ca-4d39-b403-321a3390ef15.png">

This collection requires a password variable in the environment. To configure this variable:
1. Click on the environment name, then **Manage Environments**
2. Click the + button to create a new **Private Environment**; this ensures the passwords are not saved to the JSON file when exporting.  
   <img width="214" alt="image" src="https://user-images.githubusercontent.com/34193363/218793788-ff3728b5-f79d-4d84-a714-9a1535eb42b7.png">
3. Name the environment and add the *token* variable. The actual value from this token is stored in 1Password in the *Secrets* field for the "Fivetran Hightouch Connector Settings" login.  
   <img width="478" alt="image" src="https://user-images.githubusercontent.com/34193363/218794248-b97ee149-d07a-47da-815a-f1f0f0d08dec.png">
4. Once the token variable is set, click **Close**.
5. Switch to the environment you just created.  
   <img width="240" alt="image" src="https://user-images.githubusercontent.com/34193363/218794632-bc0da33b-8777-4d35-8887-1c19a0b39f4a.png">
6. You'll now be able to make requests and use the variable(s) from the environment in any new requests (by using the `{{variableName}}` convention)  
   <img width="294" alt="image" src="https://user-images.githubusercontent.com/34193363/218794930-3c05cbd5-a148-4273-bd5f-077fff3e5ec6.png">
   
## Exporting
To save the requests to GitHub, this would require exporting the request collection as JSON after making the necessary changes.  
**Bad news**: This does not allow for real-time collaboration. If you re-import the file after making changes in Insomnia, your changes would be overwritten.  
**Good (i.e. neutral) news**:  The file contains a unique ID which Insomnia uses to know if the collection had already imported. If you already had a previous version of the collection, your private environment variables would *not* be overwritten; you can simply import the latest version of the collection and use it (unless it requires new variables).
