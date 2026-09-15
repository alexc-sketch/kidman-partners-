# Service Finder QA Notes

**Verified:** 15 September 2026

## Outcome Simulator

The published Business outcome simulator was tested at the Start-up pathway. Changing the Step 2 value from **Getting Set Up Correctly** to **Minimising Tax** immediately refreshed the selected answer in the breadcrumb, answer summary and answer chips. Changing Step 3 also refreshed the preview. The Start Over control returned the user to Business Service Finder Step 1.

The Personal outcome simulator was tested at the Wealth Accumulator and Sudden Change pathways. Selecting Sudden Change refreshed the conditional Step 2 and Step 3 options and rendered the Financial Reset Plan with the selected answers.

## Editorial Standards

All published Service Finder HTML and Markdown files were checked for em dashes. No em dashes remain. User-facing copy uses UK English. Browser API property names retain their required technical spelling.

## Publication

The corrected package was published in commit `580f8cb`.

## Pathway Explorer QA

The Pathway Explorer presents all three Business pathways and all four Personal pathways with the corresponding Step 2 and Step 3 questions, answer options, field keys, route and final outcome title. The direct Established Business reference was tested with `view=business-outcomes&path=established`; it opened the Business outcome simulator and selected the correct Established Business default outcome.

The Developer Dashboard Pathway Explorer link was also checked in the repository-relative preview structure. It resolves to `pathways.html`. The standalone explorer layout displays correctly and is suitable for desktop and small screens through its responsive one- and two-column layouts.
