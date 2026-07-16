# Contributing to OpenSatia

Last edited: 2026-07-16 13:15:15 GMT+8

OpenSatia welcomes focused contributions from humans and their agents. The
project is early, so evidence, restraint, and a clear user problem matter more
than the size of a change.

## Current Focus

The active target is a runnable first-roll experience that produces three
safe, honest, visually compelling cart options. Contributions should improve
that experience, its provider boundaries, or the evidence needed to trust it.

The broader OpenSatia vision is intentionally not all in this public
repository. Do not import private ideation archives, personal histories, or
unaccepted future concepts into an issue or pull request.

## Route The Work

- Small bug or documentation fix: open a focused pull request.
- Product feature, new provider, or architecture change: open an issue first
  and explain the user problem, proposed result, alternatives, and risks.
- Security vulnerability or unsafe provider action: follow `SECURITY.md`; do
  not disclose it in a public issue.
- General support or speculative ideation: wait for a documented community
  channel rather than turning it into implementation by default.

During the current sprint, broad refactors and unrelated infrastructure work
may be closed or deferred even when technically sound.

## Public Boundary

Never commit or attach:

- credentials, cookies, tokens, headers, `.env` values, or payment data
- addresses, personal ordering histories, or health-sensitive user data
- provider dumps or authenticated browser captures
- restricted menu content or images without clear reuse rights
- raw agent sessions that contain private context

Use synthetic, rights-cleared, or explicitly sanitized fixtures. Provider
behavior may be described without publishing a user's account state.

## Contribution Flow

1. Fork the repository or create a focused branch.
2. Keep one user-visible problem or coherent technical change per pull request.
3. Add or update proportional tests and evaluation traces.
4. Run the documented checks for the touched surface.
5. Review the diff for secrets, private data, provider captures, and unrelated
   files.
6. Open a pull request with enough evidence for another person or agent to
   reproduce the result.

Setup and test commands will be added with the executable app shell. Until
then, do not invent commands or claim checks that do not exist.

## Pull Request Evidence

Every pull request should explain:

- **Summary:** what changed
- **Why:** which user, safety, or reliability problem it solves
- **Verification:** exact checks that were actually run
- **Manual checks:** screenshots or recordings for visual changes
- **Risks / limitations:** what remains uncertain or intentionally unsupported
- **Follow-ups:** useful work that does not belong in this pull request

AI-assisted contributions are welcome. Say which agent or model materially
helped, confirm that you understand the change, and include useful validation.
Do not publish private prompts or session logs merely to prove AI assistance.

## License

By contributing, you agree that your contribution may be distributed under
the repository's MIT License. You must have the right to contribute any code,
text, data, fixtures, or media you submit.
