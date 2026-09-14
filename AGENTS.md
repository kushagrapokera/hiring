# Repository Guidelines

## Project Structure & Module Organization

This repository is an index of Alchemyst hiring drives. Each drive is self-contained and should remain easy to review independently.

- `README.md` is the top-level index for all drives.
- `june-2025/` contains Markdown-only role assignments.
- `may-2026/` contains assignment docs plus `devops/quickstart/`, a worker-based sample project.
- `June-2026_FullStackAI/` contains the Full Stack AI assignment and `agent-server/`, a TypeScript mock backend.
- Source code lives under `*/src/`; generated output such as `dist/`, dependency folders, logs, and local environment files should stay untracked.

## Build, Test, and Development Commands

Run commands from the relevant subproject, not the repository root.

- `cd June-2026_FullStackAI/agent-server && npm install` installs the mock backend dependencies.
- `npm run dev` starts the TypeScript WebSocket agent server with `tsx`.
- `npm run build` compiles TypeScript using `tsc`.
- `npm start` runs the compiled server from `dist/index.js`.
- `node test.mjs` runs the agent-server smoke/integration checks.
- `cd may-2026/devops/quickstart/workers/caller-worker && npm install && npm run build` verifies the TypeScript caller worker.
- `cd may-2026/devops/quickstart/workers/inference-worker && pip install -r requirements.txt` prepares the Python inference worker.

## Coding Style & Naming Conventions

Use TypeScript ES modules in Node projects. Keep existing two-space indentation in JSON and TypeScript config files. Prefer descriptive file and symbol names such as `agent-server`, `caller-worker`, `inference_worker.py`, and `*-assignment.md`. Keep assignment prose direct, candidate-facing, and consistent with nearby README tone.

## Testing Guidelines

There is no repository-wide test harness. Validate the specific subproject you touch. For `agent-server`, run `npm run build` and `node test.mjs`. For worker examples, run the local build or dependency install commands listed above. Add small, executable tests next to the subproject when changing runtime behavior.

## Commit & Pull Request Guidelines

Recent history uses short, imperative summaries such as `Update platform-assignment.md` and scoped labels like `[REVAMP] Revamped the hiring repo`. Keep commits focused on one drive or subproject. Pull requests should include a brief summary, affected paths, validation commands run, and screenshots or terminal output when changing runnable examples or candidate-facing workflows.

## Security & Configuration Tips

Do not commit API keys, tokens, resumes, candidate data, or local `.env` files. Keep sample configuration sanitized and document required secrets as placeholders.
