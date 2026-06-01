# raptor-comply-docs

Public customer API documentation for [Raptor Comply](https://raptorcomply.com),
published at [docs.raptorcomply.com](https://docs.raptorcomply.com) via Mintlify.
Live preview: [raptorcomply.mintlify.app](https://raptorcomply.mintlify.app).

## Structure

| Path | Authored by | Notes |
|---|---|---|
| `introduction.mdx`, `authentication.mdx`, `quickstart.mdx` | Hand-written | Get Started section |
| `concepts/*.mdx` | Hand-written | Data model, organizations, permissions |
| `guides/*.mdx` | Hand-written | Integration guides (CMDB sync, cyber asset lifecycle, error handling) |
| `api-reference/*.mdx` | Hand-written today, **auto-generated post Stage 2** | Per-resource reference pages. The Stage 2 generator in `raptor-comply` will regenerate these from the ts-rest contract + OpenFGA model. |
| `mint.json` | Hand-edited | Navigation, branding, top-level config |
| `images/`, `favicon.svg` | Hand-managed | Brand assets |

## Editing

- All pages: edit on a `feat/` branch, open a PR, merge after CODEOWNERS approval.
- The Mintlify dashboard's Web Editor pushes changes to GitHub via PR; review there.
- Branch protection: PR + CODEOWNERS + stale-approval dismissal. No direct pushes,
  no force pushes. SOC2-style independent-review is intentionally NOT required
  because Peter is the sole CODEOWNER and the HITL reviewer for auto-PRs.

## Auto-sync (post Stage 2)

The forthcoming `sync-customer-api-docs.yml` workflow in
[`raptor-comply`](https://github.com/RaptorMaps/raptor-comply) will regenerate
the `api-reference/*` pages on every change to the customer-facing contract or
the OpenFGA model. Updates land here via a force-updated `auto/api-sync` PR.

See the [Mintlify API Docs Automation design](https://github.com/RaptorMaps/raptor-comply-os/blob/main/docs/superpowers/specs/2026-05-28-mintlify-api-docs-automation-design.md)
and [rollout plan](https://github.com/RaptorMaps/raptor-comply-os/blob/main/docs/superpowers/plans/2026-05-31-mintlify-api-docs-rollout-plan.md)
for the full architecture.
