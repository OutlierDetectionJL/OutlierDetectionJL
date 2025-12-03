# OutlierDetection Workspace (Pattern A)

This workspace provides a lightweight, flexible development setup for working across repositories in the
**OutlierDetectionJL** organization.

---

## Overview

This repository acts as a **meta-workspace**. It contains a `Taskfile.yml` that automates cloning, environment setup,
development linking, and testing. Each developer creates their own Julia environment locally, depending on which
repositories they intend to work on.

---

## Getting Started

### 1. Clone this workspace

```bash
git clone <this-workspace-repo>
cd <workspace>
```

### 2. Clone the repositories you want to work on

You can clone *all* OutlierDetectionJL repos:

```bash
task clone
```

Or manually clone only the repos you need:

```bash
git clone https://github.com/OutlierDetectionJL/OutlierDetection.jl
```

The workspace does not enforce which repos must be present.

---

## Julia Environment

### Creating the environment

Since the environment is not versioned, each developer creates it locally:

```bash
task env
```

This creates `Project.toml` and `Manifest.toml` on your machine only.
They should **not** be committed.

### Developing the cloned repositories

Link all cloned repositories into the environment:

```bash
task dev
```

Only the repos that exist locally will be `develop`ed.

---

## Testing

Run tests for all repositories you have cloned:

```bash
task test
```

Each package is tested independently.
Packages that are not cloned locally will simply not be tested.
