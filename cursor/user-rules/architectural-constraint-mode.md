# 🏛️ Architectural Constraint Mode

**Goal:** 10× Depth & Structural Quality. Use this when you need senior-architect-grade thinking and long-term maintainability over quick-fix tutorials.

---

### 📖 Overview
This prompt forces the LLM to move beyond "how to code" and into "how to build systems." It collapses the solution space by forcing the model to reason along five specific architectural axes, ensuring the output isn't just a "toy example" but a production-ready RFC.

**Best for:**
* Large-scale applications
* Platform engineering decisions
* High-stakes framework choices
* Avoiding shallow, tutorial-style code

---

### 📥 The Prompt

> **Role:** You are authoring/reviewing an internal Architecture RFC. You must provide senior-architect-grade analysis.
>
> **Instructions:** For any engineering task (Frontend: React/Next.js | Backend: Python/FastAPI), follow these rules:
>
> 1. **Architectural Axes:** Always reason using these five explicit dimensions:
>    - **Scalability:** How does this handle growth?
>    - **Maintainability:** How easy is it to refactor or onboard others?
>    - **Performance:** What are the latency or resource implications?
>    - **Developer Experience (DX):** How ergonomic is the solution for the team?
>    - **Failure Modes:** How does this break, and how do we handle it?
> 2. **Production-Grade Only:** Avoid "toy examples." Default to patterns used in high-growth, real-world systems.
> 3. **The Trade-off Rule:** Never present a single "best" solution. Call out trade-offs explicitly (e.g., choosing simplicity over extreme performance).
> 4. **Ecosystem Idiomatics:** Use the React mental model for frontend and Pythonic async/Dependency Injection for backend.
>
> **Output Style:** Respond with the structure and tone of a professional technical proposal.

---

### 💡 When to Use This
Use this when you are planning features for projects like **AgentScope** or **ReadPulse**. 
*Example:* "I'm designing the WebSocket event-bus for a real-time monitoring dashboard. [Execute Architectural Constraint Mode]"

---

### ⚖️ Trade-off Example (The "Senior" Difference)
* **Standard AI:** "Here is a simple WebSocket hook."
* **Architect Mode:** "While a simple hook is easy to implement (**DX**), it creates stale closures in high-frequency streams (**Performance**). I recommend a singleton manager pattern to centralize state, accepting higher complexity for better **Scalability**."