# BV-BRC Copilot: User Guide

> **Status:** Documentation template — verify against deployed BV-BRC 3.60.21. **Audience:** BV-BRC researchers. **Placement:** `docroot/tutorial/` or service documentation (confirm navigation).

## Overview
BV-BRC Copilot is a conversational assistant for finding data and planning analyses. It can be opened from **Tools & Services → AI → Chat** or as a floating window on a BV-BRC page. Availability requires the corresponding Copilot API gateway and orchestrator.

**Screenshot:** Copilot entry point and floating chat window.

## Start a conversation
1. Open **Tools & Services → AI → Chat**, or open the floating Copilot window.
2. Describe the data or analysis you want to work with.
3. Review the assistant's response and any proposed actions.

**Example prompt placeholder:** [Insert a tested, realistic BV-BRC query and expected output.]

## Plan mode and approvals
In **Plan mode**, Copilot can prepare a job or genome group. **Nothing is submitted or written without user approval.** Review the proposed action and choose to approve, decline, or request changes. Approval decisions persist across page reloads.

For multi-step plans, review each step individually. Steps can be approved, skipped, or retried, and the interface shows progress while a step runs.

**Screenshot:** Proposed job, approval controls, and multi-step progress.

## Floating window
The window can be resized and remembers its size. On narrower screens, the sidebar collapses and the input bar adapts.

## Limitations and safeguards
- Copilot availability depends on backend deployment.
- Confirm generated parameters, inputs, and output location before approving a job.
- Do not describe Copilot as automatically running analyses without approval.

## Troubleshooting
**Copilot does not appear or cannot connect:** Confirm the corresponding API is deployed and available; contact BV-BRC support if necessary.

## Before publication
- [ ] Confirm navigation labels and deployment availability
- [ ] Test a data-discovery query
- [ ] Test approval, decline, revision, skip, retry, and reload behavior
- [ ] Capture real screenshots and example output
- [ ] Add service-specific links and support contact
