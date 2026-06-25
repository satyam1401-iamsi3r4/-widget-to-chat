# Design Note — Widget-to-Chat Interaction

## Key Design Decisions

**1. The selection moment is a full-panel flash.**
When a manager clicks a widget, the right panel fires a brief acid-yellow flash before the chat view slides in. This is a deliberate directional signal — something *activated* — rather than a soft fade. The selected widget inverts to black with a yellow left-rail accent, so the active state is unambiguous at a glance.

**2. Context transfers as a pinned header bar, not just a prompt.**
The right panel opens with a dark "context bar" showing the widget's name, current value, and delta. This stays visible throughout the conversation so the manager never loses track of which widget they're discussing — even after several messages.

**3. AI responses render as structured cards, not plain text.**
Each pre-seeded AI reply includes a 3-stat summary row plus inline bar chart. This matches how managers actually think about data — they want comparisons, not paragraphs. Plain text follows only for recommendation copy.

**4. Thread state is preserved per widget.**
Switching widgets and back restores the conversation history. Managers can ping-pong between widgets without losing context, which reflects real analytical workflows.

**5. Assumption: no real LLM.**
The task specifies hardcoded mock data. Follow-up questions return varied but plausible simulated responses. In production, this would call a real API; the structure is already wired for it.

---

## Running the App

```bash
npm install
npm start
```

Open http://localhost:3000 — target layout is 1280px wide desktop.
