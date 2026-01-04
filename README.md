# rpai

A tmux plugin for managing multiple AI coding agent sessions (opencode, claude, codex, aider, cursor).

## Features

- Scan for running AI agent processes
- Display session details: PID, agent type, working directory, status, CPU/memory usage
- Status detection: Active, Idle, Stale
- Session renaming (coming soon)
- Session termination (coming soon)

## Installation

```bash
# Clone and build
git clone <repo-url>
cd redpandai
cargo build --release

# Add to PATH
export PATH="$PATH:$(pwd)/target/release"
```

## Usage

```bash
rpai scan          # Scan and display AI agent sessions
rpai help          # Show help message
```

## Output Example

```
╔══════════════════════════════════════════════════════════════════════╗
║                        AI Agent Sessions                            ║
╠══════════════════════════════════════════════════════════════════════╣
║ [ 1] opencode        | Idle     | 8m       | 0.0%     ║
║     PID:    69971 | Mem:    749MB                                ║
║     /Users/rado/Programming/Projects/redpandai                ║
╚══════════════════════════════════════════════════════════════════════╝
```

## Status Definitions

- **Active**: High CPU usage or very recent start (less than 1 minute)
- **Idle**: Running but with low activity (1-30 minutes)
- **Stale**: Running but inactive for 30+ minutes

## Tmux Integration (Coming Soon)

- Automatic pane identification
- Session renaming via tmux
- Key bindings for quick actions
