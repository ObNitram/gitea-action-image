# gitea-action-image

This repository automatically builds and publishes Docker images based on Gitea's runner images, separated by architecture.

## Images

Two Docker images are built weekly:

- **AMD64**: `ghcr.io/obnitram/gitea-action-image:ubuntu-latest-amd`
- **ARM64**: `ghcr.io/obnitram/gitea-action-image:ubuntu-latest-arm`

Both images are based on `docker.gitea.com/runner-images:ubuntu-latest`.

## Build Schedule

The images are automatically rebuilt:
- **Weekly**: Every Sunday at 00:00 UTC
- **Manually**: Via GitHub Actions workflow dispatch
- **On push**: When changes are pushed to the main branch

## Usage

Pull the image for your architecture:

```bash
# For AMD64
docker pull ghcr.io/obnitram/gitea-action-image:ubuntu-latest-amd

# For ARM64
docker pull ghcr.io/obnitram/gitea-action-image:ubuntu-latest-arm
```

## Architecture

The repository contains:
- `Dockerfile.amd64`: Dockerfile for AMD64/x86_64 architecture
- `Dockerfile.arm64`: Dockerfile for ARM64/aarch64 architecture
- `.github/workflows/build-images.yml`: GitHub Action workflow for building and publishing images