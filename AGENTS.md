# Repository guidance

This repository contains reusable instructions for operating iPhone apps through macOS iPhone Mirroring. It is not an automation driver.

- Keep the shared skill independent of any particular iPhone app. Put tool-specific procedures and app-specific navigation in references.
- Label evidence as directly observed, documented by the vendor, or unverified. Include relevant versions and dates. Do not turn one successful attempt into a universal guarantee.
- Validate changes with a realistic, bounded task and check the visible result. A successful tool call is not evidence that the phone changed.
- Use synthetic text and reversible operations for experiments. Keep private screenshots, account details, personal conversations, and raw device logs out of Git. Store temporary evidence under the ignored `.runtime/` directory.
- Do not add fixed screen coordinates to reusable instructions. Derive targets from fresh observations.
- Preserve the user's original app state and settings when practical, and report any intentional test artifacts left behind.
- Public text is English. Keep the skill entrypoint short and link to conditional reference material.
