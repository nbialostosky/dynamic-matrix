# Utilizing setup workflows for dynamic matrix jobs

This is a proof of concept, you will need to make modifications yourself to have it work for your needs.

Example API call to kick off dynamic config:

```
curl --location --request POST 'https://circleci.com/api/v2/project/github/nbialostosky/dynamic-matrix/pipeline' \
--header 'Content-Type: application/json' \
-u '<PERSONAL_API_TOKEN>:' \
--data-raw '{
  "branch": "main",
    "parameters": {
    	"node-v-1": "2",
    	"node-v-2": "3",
    	"node-v-3": "4"
  }
}'
```

Which will result in something like:

![dynamic-matrix](https://github.com/nbialostosky/dynamic-matrix/blob/main/dynamic-matrix.png)