# Review notes — not yet validated

These notes flag issues for a later scientific review; they are not presented as resolved in this portfolio upload.

1. **Date anonymization:** The original class task used a personally significant date. The shared version substitutes 2025-06-15 12:00 in source cells and removes saved outputs. The `figures/` images were archived from the **original** run and may not correspond to the new notebook inputs. All numerical results must be regenerated.
2. **Dataset reuse:** Later notebook cells overwrite the variable `ds` while making global maps, but subsequent fitting cells reuse it. Confirm that the correct location/time and target altitude range are actually selected for the fitted Cairo profile.
3. **Fixed molecular mass:** Using $M_{air}=28.97$ g/mol across 0–100 km is an approximation; composition varies substantially with height. Check the pressure calculation at high altitudes.
4. **Tropopause definition:** The simple `dT/dz` threshold may differ from meteorological lapse-rate definitions and can be sensitive to resolution.
5. **Fitting objective and notation:** The routine uses only two fitted parameters (surface temperature and temperature gradient); $h_0$ is derived, not independently minimized. The loss function labelled chi-squared is a sum of squared relative deviations, not a statistical chi-squared weighted by measurement errors. The markdown and code use `gamma` for more than one physical meaning; clarify later.
6. **Map methods:** Global parameter maps use a linear fit to temperature, rather than the same full minimization as the Cairo section. Do not describe them as identical methods.
7. **Attribution:** The source retains its statement about AI-assisted code sections. Course collaborators, if any, should also be acknowledged before publication.

This version was extracted and packaged from a supplied notebook. **It has not been executed or independently reproduced as part of this upload.**
