1. install pi
curl -fsSL https://pi.dev/install.sh | sh

2. install ollama
curl -fsSL https://ollama.com/install.sh | sh

3. Start ollama
ollama serve

4. validate
curl http://localhost:11434

5. download the model(s)
ollama pull <model>

MODELNAMES
qwen3:8b
llama3.1:8b
deepseek-coder-v2

6. create config dir
mkdir -p ~/.pi/agent

7. create pi config
<editor> ~/.pi/agent/models.json

```
{
  "providers": {
    "ollama": {
      "baseUrl": "http://localhost:11434/v1",
      "api": "openai-completions",
      "apiKey": "ollama",
      "models": [
        { "id": "qwen3:8b" } # Add more if needed
      ]
    }
  }
}
```
9. Start Pi:
pi

10. In Pi, type:
/model

You should see the ollama provider and your local model available. 

11. happy hallucinations
