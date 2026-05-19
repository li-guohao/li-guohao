# Profile README Design

## Goal

Refresh the public GitHub profile README for `li-guohao/li-guohao` so it feels intentional, credible, and easy to maintain.

## Direction

Use a documentation-first profile with a small terminal accent. The README should read like a concise engineering profile, not a decorative template collection.

## Source Context

- Authenticated GitHub account: `li-guohao`.
- Public profile name: `Guohao Li`.
- Profile README repository already exists at `https://github.com/li-guohao/li-guohao`.
- Current public work includes original repositories around applied AI, agent systems, efficient ML, developer tools, research scaffolds, and AI skills.
- Existing README contained useful contact information but also template-heavy widgets, trophy walls, stats cards, placeholder social links, and noisy visual elements.
- Previous refresh incorrectly included forked repositories in the main showcase. The corrected design treats `fork=false` as a hard requirement for the main work section.

## Structure

- Static SVG banner with the profile name, terminal-style identity block, and three focus tags.
- Centered badge row with only a few consistent badges.
- Short terminal-style positioning line.
- Sections for `Now`, `Selected Work`, `Operating Notes`, `Stack Signals`, and `Contact`.
- Collapsible note explaining the restraint behind the README design.

## Constraints

- GitHub Markdown only: no custom CSS, JavaScript, hover effects, external layout scripts, or custom fonts that are required for comprehension.
- Avoid template-heavy elements such as trophy walls, quote cards, snake animations, excessive stats cards, and large random badge grids.
- Avoid placeholder social links and unverifiable claims.
- Main showcase entries must be public repositories where GitHub API reports `fork=false`; this is an internal maintenance rule, not public README copy.
- Keep future updates simple: new original projects should fit into the `Selected Work` table without redesigning the page.

## Self-Review

- No placeholders remain.
- The design matches the approved `Documentation-first + terminal accent` direction.
- The README does not depend on unsupported GitHub rendering features.
- Claims are tied to current public repositories or contact details already visible in the existing public README.
- The main showcase excludes `worldmonitor`, `agentguard`, and any other repository where `fork=true`.
