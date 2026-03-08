# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

PandaWiki is an AI-driven open-source knowledge base system built with Go (backend) and React (frontend). It provides AI-powered documentation, Q&A, and search capabilities.

## Architecture

### Backend (Go)
- Echo web framework with JWT
- PostgreSQL + GORM
- Redis cache
- NATS JetStream
- MinIO (S3-compatible)
- Cloudwego Eino for LLM, RAGLite for vector search

### Frontend (React)
- pnpm workspaces monorepo
- Admin console + Wiki site
- MUI components

## Common Commands

### Backend
```bash
cd backend

# Build for local development
export GOPROXY=https://goproxy.cn,direct
CGO_ENABLED=0 GOOS=linux GOARCH=arm64 go build -o /tmp/panda-wiki-api-linux ./cmd/api
```

### Frontend
```bash
cd web
pnpm install
pnpm dev
```

## Docker Services Required
- PostgreSQL (port 15432)
- Redis (port 16379)
- NATS with JetStream (port 4222)
- MinIO (port 9000/9001)
