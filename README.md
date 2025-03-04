# Building an LMM API With GoLang
## Langchain + GinGonic + GoLang

Running And Testing
All of the pieces are built - let's run it! Let's open
two terminals:

1. One to run the API
2. One to run cURL calls to the API

In the first terminal, let's run our API: 
```shell
# Don't forget your openAI API Key!
$ export OPENAI_API_KEY=sk...
$ go run main.go
```

In the second terminal, let's run a cURL call with our parameters:

```shell
$ curl -X POST -H"Content-type: application/json" \
    -d'{"favorite_season": "summer", "hobbies": ["surfing","running"], "budget":1000}' \
    http://localhost:8080/vacation/create
```

If we flip back to our first terminal, we can see that the idea generation starts and eventually
finishes.

In our second terminal, let's see what the LLM thinks we should do: 
```shell
$ curl -X GET -H"Content-type: application/json" \
    http://localhost:8080/vacation/b2289b6a-88a5-43b6-8217-e2855908e230
```
Note that the UUID (`255f732f-4960-439b-93db-58972d076d61`) will vary between your system and
mine!
