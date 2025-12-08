# Contributing to Snapmaker U1 Extended Firmware

Thanks for helping make the U1 more awesome. 🎉  
This project is community-driven and depends on your feedback and patches.

Before you open a pull request, please read and agree to the terms below.

---

## Project license

This project is licensed under **GPL-3.0-only**.  
All accepted contributions will be distributed under the same license.
By contributing, you agree that your Contribution will be licensed under
**GPL-3.0-only**.

By contributing, you agree that your changes may be included in future
GPL-licensed releases as source code and/or as part of firmware images
built from this repository.

If that is not acceptable to you, please do not submit a contribution.

---

## Contributor license terms

By submitting a pull request, patch, or other contribution ("Contribution"),
you confirm that:

1. **You have the rights to contribute**

   You are the author of the Contribution, or you otherwise have sufficient
   rights to submit it under the terms of the GPL-3.0-only license.

2. **You license your Contribution under GPL-3.0-only**

   You hereby license your Contribution under the same license used by the
   project: the GNU General Public License, version 3.0 only.

   This means:
   - The project may copy, modify, and redistribute your Contribution
     under GPL-3.0-only.
   - Downstream users may do the same, under the terms of GPL-3.0-only.

3. **No additional restrictions**

   You will not assert any patent or other rights that would prevent the
   project or its users from exercising the rights granted by GPL-3.0-only
   with respect to your Contribution.

4. **No hidden third-party code**

   If your Contribution includes or is based on third-party code, you:
   - Clearly identify that code and its license in your pull request, and
   - Confirm that the license is compatible with GPL-3.0-only and with the
     way the project uses it.

If you are contributing on behalf of a company or organization, you confirm
that you have authority to submit the Contribution on its behalf under these
terms.

---

## Code and review style

Some quick guidelines to keep things pleasant:

- Keep changes focused; avoid huge "do everything" PRs.
- Document user-visible changes in the docs or `RELEASE.md`.
- For risky changes (boot, updates, safety logic), please open an issue/thread
  to discuss the approach before sending a big patch.
- When in doubt, assume your change can brick a printer or reduce safety and
  treat it accordingly.

---

## Safety reminder

Contributions that touch boot, update, toolchanging, or safety-critical paths
may have real-world consequences if something goes wrong.

By contributing such changes, you acknowledge that:

- The maintainers may ask for extra review, tests, or changes.
- The maintainers may decline changes that look too risky for typical users.

Thanks again for helping improve the U1 ecosystem. 💙
