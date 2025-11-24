SHELL := /bin/bash
ROOT  := $(shell dirname $(realpath $(firstword $(MAKEFILE_LIST))))

CONDA_ENV_NAME = fullstack

# -----------------------------------------------------------------------------
# backend
# -----------------------------------------------------------------------------

.PHONY: backend
backend:
	@@conda run --no-capture-output --live-stream --name "$(CONDA_ENV_NAME)" --cwd "${ROOT}/backend" \
		python app.py

.PHONY: backend-test
backend-test:
	@@conda run --no-capture-output --live-stream --name "$(CONDA_ENV_NAME)" --cwd "${ROOT}/backend" \
		pytest

# -----------------------------------------------------------------------------
# frontend
# -----------------------------------------------------------------------------

.PHONY: frontend
frontend:
	@@conda run --no-capture-output --live-stream --name "$(CONDA_ENV_NAME)" --cwd "${ROOT}/frontend" \
		npm run dev

.PHONY: frontend-install
frontend-install:
	@@conda run --no-capture-output --live-stream --name "$(CONDA_ENV_NAME)" --cwd "${ROOT}/frontend" \
		npm install

.PHONY: frontend-test
frontend-test:
	@@conda run --no-capture-output --live-stream --name "$(CONDA_ENV_NAME)" --cwd "${ROOT}/frontend" \
		npm test