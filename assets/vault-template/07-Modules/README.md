# 07-Modules: Module Knowledge Map

One card per module of the product: what it is for, where its code starts, which data it owns, the rules that
must stay true, the traps that already cost time, its ADRs, bugs and tests, and when someone last compared the
card with the code. An agent starts from this settled knowledge instead of rediscovering the module.

*   **Template:** `templates/module-card.md` of the skill. The file name is the id: `MOD-<module>.md`, for
    example `MOD-payments.md`; task notes link the cards in scope from §5 Code Locations (`[[MOD-payments]]`).
*   **Read before you touch.** Every role reads the card of a module before its first edit there, together with
    the rest of the ticket (`workflows/session-protocol.md` §1.1).
*   **Update in the same change.** When a change alters the module's behaviour, data or entry points, its author
    updates the card in the same branch, so the card is reviewed with the code. `date_verified` and
    `verified_commit` move only when someone actually compared the card with the code.
*   **The code wins.** A card that disagrees with the code is fixed, not followed; a reviewer asks for a missing
    card update the way it asks for a missing test.
*   **Lint:** `scripts/vault_lint.py` checks the card frontmatter (`id`, `title`, `entry_points`,
    `date_verified`) and warns when an `entry_points` path does not exist in the project (VL015; paths are
    relative to the project root).

This README is not a module card and is not linted as one.
