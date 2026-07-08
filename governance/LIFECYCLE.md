# AI-PROTOCOLS Lifecycle

STATUS=active

## States

- draft: initial proposal
- experimental: used in tests or limited sessions
- active: recommended for current use
- deprecated: kept for compatibility
- retired: removed from recommended use

## Flow

draft -> experimental -> active -> deprecated -> retired

## Rules

- every relevant change must be recorded in CHANGELOG
- state promotion requires observable criteria
- deprecation must indicate a replacement when one exists
- removal from recommended use does not erase history
- the lifecycle does not define implementation
