# Pi Run
Containerized [pi](https://github.com/earendil-works/pi) runner, based on plain docker solution[^1].

## Add environment variables (`.env`)
```sh
WORKSPACE=<workspace dir>
ANTHROPIC_API_KEY=<Anthropic API Key>
GEMINI_API_KEY=<Gemini API Key>
```

Provide at least one of `ANTHROPIC_API_KEY` or `GEMINI_API_KEY`.

## Running with Local LLM (Qwen3-Coder)

To run with the Qwen3-Coder model using llama.cpp:

```bash
llama-server -hf unsloth/Qwen3-Coder-30B-A3B-Instruct-GGUF:Q4_K_M \
  --alias qwen3-coder --jinja -c 65536 --host 0.0.0.0 --port 8080
```

This will start a local LLM server that pi will connect to using the configuration in `models.json`.

> **Note**: Make sure to run the llama.cpp server before starting pi, and ensure that the server is accessible at `http://host.docker.internal:8080/v1` from within the docker container.

## Run pi
```
./run
```

To rebuild the image first (e.g. to pick up a new pi release):
```
./run --build
```

Run `./run --help` for all options.

[^1]: https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/containerization.md#plain-docker
