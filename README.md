# AutoCut Studio

A local-first AI video editor built with React + FastAPI.

## Architecture overview

AutoCut Studio is organized as a monorepo with a React + Vite frontend and a FastAPI backend that orchestrates project management, media analysis, scene planning, and FFmpeg-based rendering. The workflow is intentionally local-first: videos stay on disk, metadata is stored in SQLite, and long-running work runs as background jobs that can be reviewed, cancelled, and retried.

## Implementation checklist

- [x] Monorepo structure with frontend, backend, storage, scripts, and docs
- [x] FastAPI project API with health checks, upload handling, and project metadata
- [x] SQLite-backed job and project persistence
- [x] FFprobe metadata extraction and scene analysis workflow
- [x] EDL generation and edit-plan schema
- [x] FFmpeg render pipeline and MP4 validation
- [x] Frontend dashboard and project workflow
- [ ] Optional AI model integration and deeper transcript/vision features are available but not mandatory for local execution
- [ ] Production stewardship for large-video workflows, GPU tuning, and deployment hardening

## Quick start

1. `python3 -m venv .venv`
2. `source .venv/bin/activate`
3. `pip install -r backend/requirements.txt`
4. `cd frontend && npm install`
5. `cd .. && ./scripts/start.sh`

## Notes

This project is designed to work without paid APIs in the default local workflow. Optional enhancements, such as local Whisper or Ollama integrations, are supported by design, but the app continues to function with rule-based analysis when those tools are unavailable.
