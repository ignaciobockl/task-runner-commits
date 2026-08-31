# task-runner-commits

A collection of **Opencode** / **Claude Code** skills that can be installed on any development machine via the `skills.sh` CLI. Each skill lives in its own folder under `skills/` and follows the standard `SKILL.md` structure.

## Repository Structure

```
skills/
└── task-runner-commits/
    └── SKILL.md      # The task planning + commit skill
├── README.md          # This file
└── .gitignore
```

- **`skills/<skill-name>/SKILL.md`**: The core definition of a skill — front-matter block with `name` and `description`, followed by detailed step-by-step English instructions an agent can follow.
- **`README.md`** (root): Overview of the repo, installation guidance, and contribution notes.

## Installing a Skill

### Via the `skills.sh` CLI (recommended)

```bash
npx skills add <your-github-owner>/<your-repo>
```

Replace `<your-github-owner>/<your-repo>` with the GitHub repository that hosts the skill collection. The CLI downloads the skill and registers it for your agent.

### Manual installation

1. Clone the repository to a local directory.
2. Add the absolute path of the `skills/` folder to your global `opencode.json` configuration:

```json
{
  "skills": {
    "paths": ["C:/path/to/your/skills"]
  }
}
```

Adjust the path for your environment (use forward slashes or escaped backslashes).

## Interoperability

All skills use the standard `SKILL.md` format shared across Opencode, Claude Code, and generic Agent Skills. Any agent that can parse the markdown front-matter can execute the skill regardless of platform.

## Contributing New Skills

1. Create a new folder under `skills/` with a concise kebab-case name (e.g., `my-new-skill`).
2. Add `SKILL.md` following the template used in existing skills:
   - Front-matter with `name` and a one-sentence `description`.
   - Clear, numbered English instructions.
   - Any required templates or ASCII diagrams.
3. Open a pull request.

---

*This repository does not contain any runtime code; it only provides specifications for skills that agents will execute.*