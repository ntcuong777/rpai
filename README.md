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
AI Agent Sessions:

○ [1] opencode | Idle | 2m
    PID: 70351 | Mem: 419MB | CPU: 0.0%
    /Users/rado

○ [2] opencode | Idle | 21m
    PID: 69971 | Mem: 808MB | CPU: 0.0%
    /Users/rado/Programming/Projects/redpandai
```

## Status Definitions

- **Active**: High CPU usage or very recent start (less than 1 minute)
- **Idle**: Running but with low activity (1-30 minutes)
- **Stale**: Running but inactive for 30+ minutes

## Tmux Integration (Coming Soon)

- Automatic pane identification
- Session renaming via tmux
- Key bindings for quick actions

## Future Enhancements

- Token usage tracking (tokens used, context window, cost estimation)
- Session activity monitoring (last message, current task)
- Jump to session functionality
- Session persistence across restarts
