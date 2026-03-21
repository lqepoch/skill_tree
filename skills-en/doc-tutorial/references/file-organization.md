# File Organization Guidelines

## Core Principle
Separate concerns to keep the tutorial maintainable and clear.

## Recommended Structure

```
tutorial-name/
├── index.md              # Main tutorial entry point
├── steps/                # Individual step files (optional for large tutorials)
│   ├── step-01.md
│   ├── step-02.md
│   └── ...
├── diagrams/             # Mermaid diagrams (if extracted from markdown)
│   ├── workflow.mmd
│   ├── sequence.mmd
│   └── ...
├── assets/               # Images, screenshots, icons
│   ├── screenshots/
│   │   ├── step-01.png
│   │   └── ...
│   └── icons/
├── scripts/              # Tutorial-specific scripts
│   ├── setup.sh
│   ├── validate.sh
│   └── ...
└── references/           # Reference materials, cheat sheets, etc.
    ├── glossary.md
    └── faq.md
```

## When to Use This Structure

- **Simple tutorials** (< 5 steps): Keep everything in a single `index.md`
- **Medium tutorials** (5-15 steps): Consider splitting steps into the `steps/` directory
- **Complex tutorials** (> 15 steps or significant assets): Use the full structure above

## Naming Conventions

- Use lowercase letters, numbers, and hyphens
- Be descriptive but concise
- For steps: `step-01.md`, `step-02.md`, etc. (use leading zeros for proper sorting)
- For diagrams: describe the purpose, e.g., `user-workflow.mmd`, `api-sequence.mmd`

## Asset Management

- Store screenshots in `assets/screenshots/` with step numbers in filenames
- Optimize images for web (appropriate size, compression)
- Use consistent image formats (PNG for screenshots, SVG for icons/diagrams)
- Reference assets relatively from the markdown files

## Cross-Project Compatibility

To make tutorials adaptable to different projects:

1. **Use placeholders**: Replace project-specific names with placeholders like `[your-project-name]`
2. **Document assumptions**: Clearly state what the tutorial assumes about the project structure
3. **Provide alternatives**: When possible, show variations for different project types
4. **Use relative paths**: Avoid absolute paths; use paths relative to the project root
5. **Version considerations**: Note which versions of tools/frameworks the tutorial applies to

## Example: Adapting a Tutorial

Original step:
```
1. Navigate to src/components/user-profile/
2. Edit UserProfile.js
```

Adaptable version:
```
1. Navigate to your component directory (typically src/components/ or similar)
2. Locate the user profile component file (may be named UserProfile.js, UserProfile.tsx, etc.)
3. Edit the user profile component file
```

## Maintenance Tips

- Regularly check that file paths still exist
- Update assets when UI changes
- Verify that scripts still work with current tool versions
- Keep diagrams in sync with described processes