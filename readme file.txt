SLA Governance Virtual Agent
A responsive Service Level Agreement governance dashboard and conversational assistant for monitoring incidents, identifying SLA risk, documenting breaches, and reviewing justifications.

What this app does
Shows an overview of active SLA risk, breached work, compliance, and completed incidents.
Provides a Virtual Agent that explains the project and answers questions from the local incident register.
Tracks incidents with priority, assignment group, assignee, elapsed hours, and state.
Applies a 4-hour SLA target to P1 critical incidents.
Marks P1 incidents as At risk at 75% of the SLA target.
Marks P1 incidents as Breached at 100% or more of the target.
Lets users submit breach justifications and update manager review status.
Provides dashboard summaries for compliance, breach reasons, and breached assignment groups.
Stores demo incidents, justifications, and chat history in the current browser.
Works across desktop, laptop, tablet, and mobile layouts.
Includes installable web-app metadata for supported mobile browsers.
Virtual Agent examples
Open the Virtual Agent page and try:

Check SLA for INC0010001
Explain every step of the project
What is an incident?
What is an SLA breach?
What does at risk mean?
List breached or at-risk work
How do I justify a breach?
Summarize the dashboard
How does manager review work?
How do I create an incident?
The assistant responds with explanations, current data from the register, next steps, and links to the relevant page.

SLA policy used in the demo
Rule	Behavior
P1 target	4 hours
At-risk threshold	75% of the target, or 3 hours
Breach threshold	100% of the target, or 4 hours
Resolved incident	Completed
P2 and P3 incidents	Not applicable to the P1 SLA calculation
Breach justification	Required for breached P1 incidents
Manager review	Pending, Approved, or Needs revision
Run locally
This app is part of a pnpm workspace.

Requirements
Node.js
pnpm
Install dependencies
From the workspace root:

pnpm install
Start the development preview
pnpm --filter @workspace/sla-governance run dev
The managed app workflow supplies the required port and base path.

Type-check the app
pnpm --filter @workspace/sla-governance run typecheck
Build the app
PORT=4177 BASE_PATH=/ pnpm --filter @workspace/sla-governance run build
Project structure
artifacts/sla-governance/
├── public/
│   ├── favicon.svg
│   ├── manifest.webmanifest
│   └── robots.txt
├── src/
│   ├── App.tsx
│   ├── index.css
│   └── main.tsx
├── index.html
├── package.json
├── tsconfig.json
└── vite.config.ts
Data and privacy
This is a zero-backend demo. Data is saved with browser local storage:

slaDemoData stores incidents and justifications.
slaDemoConversation stores the Virtual Agent conversation.
Data is device- and browser-specific. It is not automatically shared between laptops or phones, and it is not connected to ServiceNow or another external system.

Access from other devices
The UI is responsive and can be opened from mobile phones, tablets, laptops, and desktop computers after publishing. Publish the app to get a public URL. To use a non-platform-branded address, connect a custom domain through the publishing settings.

Technology
React
TypeScript
Vite
Wouter
Tailwind CSS
Lucide React
Browser local storage
