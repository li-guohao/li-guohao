# Profile README Design

## Goal

Refresh the public GitHub profile README for `li-guohao/li-guohao` so it feels intentional, credible, and easy to maintain.

## Direction

Use a dashboard-like profile structure with a dark terminal banner. The README should read like a concise engineering profile, not a decorative template collection.

## Source Context

- Authenticated GitHub account: `li-guohao`.
- Public profile name: `Guohao Li`.
- Profile README repository already exists at `https://github.com/li-guohao/li-guohao`.
- Current public work includes original repositories around applied AI, agent systems, efficient ML, developer tools, research scaffolds, and AI skills.
- Existing README contained useful contact information but also template-heavy widgets, trophy walls, stats cards, placeholder social links, and noisy visual elements.
- Previous refresh incorrectly included forked repositories in the main showcase. The corrected design treats `fork=false` as an internal hard requirement for the main work section, while keeping that rule out of public README copy.

## Structure

- Static SVG banner with a dark terminal panel on the left and compact signal panels on the right.
- Centered badge row with only a few consistent badges.
- Short terminal-style positioning line.
- Sections for `Signal Snapshot`, `Current Loop`, `Selected Work`, `Stack Surface`, and `Contact`.

## Constraints

- GitHub Markdown only: no custom CSS, JavaScript, hover effects, external layout scripts, or custom fonts that are required for comprehension.
- Avoid template-heavy elements such as trophy walls, quote cards, snake animations, excessive stats cards, and large random badge grids.
- Avoid placeholder social links and unverifiable claims.
- Keep future updates simple: new projects should fit into the `Selected Work` table without redesigning the page.

## Self-Review

- No placeholders remain.
- The design matches the approved hybrid direction: Signal Dashboard structure with AI Lab Console banner.
- The README does not depend on unsupported GitHub rendering features.
- Claims are tied to current public repositories or contact details already visible in the existing public README.
