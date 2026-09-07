# Pi Run
Containerized [pi](https://github.com/earendil-works/pi) runner, based on plain docker solution[^1].

## Add environment variables (`.env`)
```sh
WORKSPACE=<workspace dir>
ANTHROPIC_API_KEY=<Anthropic API Key>
GEMINI_API_KEY=<Gemini API Key>
```

Provide at least one of `ANTHROPIC_API_KEY` or `GEMINI_API_KEY`.

## Run pi
```
./run
```

[^1]: https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/containerization.md
