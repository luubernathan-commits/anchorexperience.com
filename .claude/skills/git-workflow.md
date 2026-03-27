# Git Workflow

Enforces consistent git practices across all Nathan Luu's repositories. This skill applies to every commit, branch, and PR that Claude Code generates.

---

## Commit Messages

### Format

```
<type>: <short description>

[optional body — explain WHY, not what]
```

### Types

| Type | When to Use |
|------|-------------|
| `feat` | New feature or capability |
| `fix` | Bug fix |
| `style` | Design/UI changes (no logic change) |
| `refactor` | Code restructure (no feature/fix) |
| `docs` | Documentation only |
| `chore` | Build, deps, config changes |
| `test` | Adding or updating tests |
| `perf` | Performance improvement |

### Rules

- Imperative mood: "Add calendar view" NOT "Added calendar view"
- Under 72 characters for the first line
- No period at the end of the subject line
- Body explains WHY the change was made, not WHAT changed (the diff shows that)
- Reference issue numbers when applicable: `feat: add decision log (#12)`

### Examples

```
feat: add facilitator scheduling view to AnchorOS

Enables retreat coordinators to assign facilitators to
time slots with drag-and-drop. Uses localStorage for
offline persistence with optional Supabase sync.
```

```
fix: resolve dark mode contrast on status badges
```

```
chore: update Supabase client to v2.47.0
```

---

## Branch Naming

### Format

```
<type>/<short-description>
```

### Examples

```
feat/calendar-view
fix/dark-mode-badges
refactor/localStorage-pattern
docs/update-readme
chore/deps-update
```

### Rules

- Lowercase with hyphens
- Keep under 50 characters
- Match the commit type prefix
- Branch from `main` unless working on a long-running feature

---

## Workflow

### Standard Flow

1. Create branch: `git checkout -b feat/new-feature`
2. Make changes in small, logical commits
3. Push: `git push origin feat/new-feature`
4. Create PR (if collaborating) or merge to main directly

### Solo Development (Default for Nathan's Projects)

For solo work, commit directly to `main` with clear messages:

```bash
git add .
git commit -m "feat: add retreat calendar component"
git push origin main
```

This triggers auto-deploy on Cloudflare Pages for Anchor repos.

---

## Pre-Commit Checks

Before every commit, verify:

- [ ] Code compiles without errors (`npm run build` or `pnpm run typecheck`)
- [ ] No `console.log` debug statements left behind (except `console.warn` for non-critical errors)
- [ ] No API keys, tokens, or secrets in the commit
- [ ] No `any` types in TypeScript files
- [ ] Commit message follows the convention above

---

## .gitignore Standards

Every repo should ignore:

```
node_modules/
dist/
.env
.env.local
.env.*.local
*.log
.DS_Store
.vscode/
.idea/
```

---

## Repo-Specific Notes

### Floject 2.0 (`floject-app`)
- Uses pnpm — lockfile is `pnpm-lock.yaml`
- Monorepo — commits may span multiple packages
- Build: `pnpm run build` (typechecks all packages)
- Deploy: Cloudflare Workers via `wrangler`

### Anchor Experience (`anchor-experience`)
- Uses npm — lockfile is `package-lock.json`
- Build: `npm run build` (copies static + built assets to `dist/`)
- Deploy: Auto-deploys to Cloudflare Pages on push to `main`
- Contains constitution at `.specify/memory/constitution.md` — never modify without approval

### anchorexperience.com
- Static site — no build step
- Deploy: Auto-deploys to Cloudflare Pages on push to `main`
- Any push immediately goes live
