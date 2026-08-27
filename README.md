# my-skills

## Guide to Using Skills in Opencode

### What are Skills?
Skills in Opencode are reusable agents that can be invoked to perform specific tasks. They are defined by a SKILL.md file and can be loaded using the `skill` tool.

### Skill Structure
Each skill is stored in a directory under `~/.opencode/skills/` (global) or potentially in a project-specific location (like `.opencode/skills/` in the project root). The skill directory must contain a `SKILL.md` file with the following format:

```markdown
---
name: skill-name
description: >
  Description of the skill.
  It can be multiple lines.
  Activated by phrases like "...".
---

## Skill Content
... (instructions for the skill)
```

### Configuring Skills
Skills are automatically loaded from the global skills directory (`~/.opencode/skills/`). To add a new skill:
1. Create a directory under `~/.opencode/skills/` with the skill name.
2. Inside that directory, create a `SKILL.md` file with the skill definition.

### Using a Skill in Opencode
Once a skill is installed, you can use it by invoking the `skill` tool in your conversation with Opencode. For example:
- To use the commit-message-writer skill, you would say: "Use the commit-message-writer skill to generate a commit message."
- Opencode will then load the skill and follow its instructions.

### Using a Skill in Antigravity
In Antigravity, there is no need for a specific `/skill` command. You can simply ask the AI in natural language to use a skill, and it will dynamically find and read the corresponding `SKILL.md` file. 

- **By Name**: "Usa la skill `commit-message-writer` para generar mi mensaje de commit."
- **By Description**: "Usa la skill que sirve para hacer commits."
- **Listing Skills**: "¿Qué skills tengo instaladas?" o "Muéstrame mis skills."

Antigravity will automatically navigate to your `~/.opencode/skills/` (or project-specific skills folder), read the instructions, and apply them directly in the chat.

### Example: Creating a New Skill
Let's create a simple skill for greeting:

1. Create the directory: `mkdir -p ~/.opencode/skills/greeting-skill`
2. Create the SKILL.md file:
```markdown
---
name: greeting-skill
description: >
  Generates a friendly greeting.
  Use when you want to say hello.
  Activated by phrases like "say hello" or "greet someone".
---

## Output
Return a friendly greeting message. For example:
"Hello! How can I assist you today?"
```

Now you can use the skill by asking Opencode to use the greeting-skill.

### Managing Project-Specific Skills
To manage skills specific to this project, place them in the `.agents/skill/` directory. Each skill should have its own directory containing a `SKILL.md` file.

- **Add a skill:** Create `.agents/skill/<skill-name>/SKILL.md` and define its behavior.
- **Update a skill:** Edit the existing `SKILL.md` to refine its instructions or behavior.
- **Share skills:** Commit the `.agents` directory to the repository so the team can use the same project-specific skills.
