# Prompt ETL Studio

Install guide for the Prompt ETL Studio container. The designed page is published with GitHub Pages from `index.html`.

## Run

```bash
docker pull ghcr.io/nirmalk960/prompt-etl:0.2.1

docker run -d --name prompt-etl \
  -p 8080:8080 \
  -v prompt-etl-data:/data \
  --add-host=host.docker.internal:host-gateway \
  ghcr.io/nirmalk960/prompt-etl:0.2.1
```

Open http://localhost:8080.

## Sign in

The first start writes an access token on the data volume. Paste it into Settings.

```bash
docker exec prompt-etl cat /data/access_token
```

## Optional model

Install [Ollama](https://ollama.com) on the host, then:

```bash
ollama pull qwen2.5-coder:7b
```

The container looks for Ollama at `http://host.docker.internal:11434`.

## Issues

Bug reports and feature requests: https://github.com/nirmalk960/prompt-etl-studio/issues
