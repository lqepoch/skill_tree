# Doc Tutorial Skill

This skill helps create detailed documentation tutorials with step-by-step instructions, Mermaid diagrams, and organized file structures.

## Purpose

Create comprehensive documentation tutorials that guide users through specific processes with:
- Clear step-by-step instructions
- Visual Mermaid diagrams for complex workflows
- Organized file structure with proper separation of concerns
- Compatibility with various project types
- Scalable formatting for large documentation sets

## Usage

When you need to create a detailed tutorial/documentation, this skill will:
1. Help you break down the process into clear steps
2. Generate Mermaid diagrams for workflow visualization
3. Organize content appropriately across SKILL.md, scripts/, references/, and assets/ directories
4. Provide templates for consistent documentation formatting

## File Structure

```
doc-tutorial/
├── SKILL.md          # Main skill documentation
├── scripts/          # Utility scripts for tutorial generation
├── references/       # Reference materials and templates
└── assets/           # Images, diagrams, and other media
```

## Core Principles

1. **Atomic Steps**: Each tutorial step should focus on a single action
2. **Visual Aids**: Use Mermaid diagrams to illustrate complex processes
3. **Separation of Concerns**: Keep instructional content separate from code/assets
4. **Scalability**: Design templates that work for both small and large documentation sets
5. **Portability**: Ensure tutorials can be adapted to different project contexts

## Creating a Tutorial

To create a new tutorial using this skill:

1. Identify the process/document to document
2. Break it down into discrete, actionable steps
3. For each step, specify:
   - What the user should do
   - Where they should click/navigate
   - What they should create/modify
   - Expected outcome
4. Create Mermaid diagrams for workflow visualization
5. Organize supporting files in appropriate directories
6. Ensure compatibility with target project types

## Mermaid Diagram Guidelines

When creating Mermaid diagrams:
- Use flowchart diagrams for sequential processes
- Use sequence diagrams for interactions between components
- Use state diagrams for complex state transitions
- Keep diagrams simple and focused
- Label all elements clearly
- Use consistent styling

## Template Files

This skill includes template files in the references/ directory to help standardize tutorial creation:
- Step-by-step instruction templates
- Mermaid diagram templates
- File organization guidelines
- Cross-project compatibility notes

## Maintenance

To maintain tutorials created with this skill:
- Regularly review steps for accuracy
- Update diagrams when processes change
- Verify all file paths and references
- Ensure compatibility with evolving project structures
- Keep language clear and concise