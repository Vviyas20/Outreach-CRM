# Outreach CRM

Version 1. Repository: https://github.com/Vviyas20/Outreach-CRM

Code for the outreach CRM: the live app, its sandbox, and the design work for its new look.

| Folder | What it is |
| --- | --- |
| `crm/` | The live Outreach CRM (single `index.html`), kept identical to the published artifact. It runs as a claude.ai artifact: records live in the artifact's database and contacts load from `data/sheet.json`. |
| `sandbox/` | The Outreach CRM sandbox in the Ospra look: the same app with an in-memory store, invented people and companies, a movable clock and view-only mode. Open `index.html` directly in a browser. |
| `sandbox/previous-look/` | The sandbox before the Ospra restyle (identical logic, original coral and ink styling). |
| `design-styles/` | Four Ospra-based UI/UX directions for the CRM (focus queue, pipeline board, line monitor, account passport). Standalone HTML, see its README. |
| `design-options/` | The four "new look options" boards from the Design canvas (Midnight Pulse, Crisp SaaS, Ink and Coral, Command Center) and the shared `CRMScreen` component they theme. These `.dc.html` files render inside the claude.ai Design tool, which supplies `support.js`. |

## Data is not in this repo

`crm/data/sheet.json` (the BI-sheet export of real contacts with emails and phone numbers) is excluded on purpose and listed in `.gitignore`. Keep it in the artifact, not in git. The sandbox needs no data file.

## Keeping the two in step

`crm/index.html` and `sandbox/index.html` share the same app code. The sandbox adds dummy data, a movable clock and test hooks, and sets `QSINCE=''` so every conducted meeting goes through qualification; the live CRM sets `QSINCE` to the go-live date of deal qualification so meetings conducted before it keep their stage. Change both files together and republish both artifacts.

Meetings live inside the Deals tab in both builds: upcoming meetings, held meetings to qualify (the form opens inline under the row), the pipeline, recently qualified meetings and cancelled check-ins on one page.
