1. install pi. <p>
`curl -fsSL https://pi.dev/install.sh | sh`

2. install ollama.  <p>
`curl -fsSL https://ollama.com/install.sh | sh`

3. Start ollama.  <p>
`ollama serve`

4. validate.  <p>
`curl http://localhost:11434`

5. download the model(s) aka pick your poison.  <p>
`ollama pull <model>`

MODEL examples
- qwen3:8b
- llama3.1:8b
- deepseek-coder-v2
- qwen2.5-coder:7b
- deepseek-r1:8b

6. create config dir.  <p>
`mkdir -p ~/.pi/agent`

7. create pi config.  <p>
`<editor> ~/.pi/agent/models.json`

```
{
  "providers": {
    "ollama": {
      "baseUrl": "http://localhost:11434/v1",
      "api": "openai-completions",
      "apiKey": "ollama",
      "compat": {
        "supportsDeveloperRole": false,
        "supportsReasoningEffort": false
      },
      "models": [
        {
          "id": "qwen2.5-coder:7b"
        },
        {
          "id": "llama3.1:8b"
        },
        {
          "id": "deepseek-r1:8b"
        }
      ]
    }
  }
}
```


9. Start Pi:   <p>
`pi`

10. In Pi, type:   <p>
`/model`

You should see the ollama provider and your local model available. 

11. happy hallucinations
