# adk-course-lab
Code Lab for the Build Your First Agent with Agent Development Kit (ADK) eCourse

## Running `adk web` in GitHub Codespaces

```bash
source .venv/bin/activate
adk web --allow_origins="*"
```

Plain `adk web` (or `--allow_origins` with only the Codespaces URL) leaves the dev UI as a black page. The browser console shows `403 Forbidden` on every `/dev-ui/*.js` file.

`adk web` binds to `127.0.0.1`, and ADK 2.x's DNS-rebinding guard (`_OriginCheckMiddleware` in `google/adk/cli/api_server.py`) rejects requests that arrive through the Codespaces proxy. `--allow_origins="*"` disables that guard, so use it only in this throwaway dev container.
