# AI Ethics Quest: System Architecture

## Overview

**AI Ethics Quest** is a narrative-driven, interactive browser game built using **HTML**, **CSS**, and **JavaScript**. Players step into the role of **Jamie**, a high school intern at Edubot Inc., tasked with guiding the ethical development of an AI tutor.

The game integrates **real-world AI dilemmas** (data privacy, bias, misinformation) and centers around **stakeholder trust management**. Trust levels dynamically influence the story's progression, stakeholder responses, and determine the success or failure of Edubot.

---

## Core Components

### 1. Frontend Stack
- **HTML5**: Structures the game interface and elements.
- **CSS3**: Styles the game, including dark-themed UI, trust bars, and responsive layouts.
- **JavaScript (Vanilla)**: Handles game logic, decision-making mechanics, stakeholder trust updates, and narrative feedback.

No external libraries or frameworks are used, ensuring a lightweight, portable design.

---

## Game Architecture Diagram

[User Interface] | |---> [Game Logic Engine (JavaScript)] | | | |---> Stakeholder Trust Manager | |---> Decision Engine | |---> Narrative Consequence Handler | |---> [Stakeholder Trust Visualization (CSS Trust Bars)] | |---> [Narrative Feedback System] | |---> Headlines, Social Media Posts, Event Logs

markdown
Copy
Edit

---

## Key Systems

### 1. Stakeholder Trust Manager
- **Stakeholders**: Students, Parents, Teachers, Regulators, Trolls.
- **Trust Levels**: Represented as floating-point values (0–1), displayed through **CSS-based trust bars**.
- **Thresholds**: If trust falls below a set threshold, specific **narrative consequences** trigger.
- **Dependencies**:
  - **Students → Parents**: If students disengage, parents follow.
  - **Teachers → Regulators**: Teachers raising concerns prompts regulatory scrutiny.
  - **Trolls → Students/Teachers**: Trolls degrade trust passively.

### 2. Decision Engine
- **Player Decisions**: Presented as buttons for each chapter scenario.
- **Immediate Trust Changes**: Trust deltas are applied to stakeholders based on decision impacts.
- **Agent Influence Application**: After each decision, **secondary influences** cascade (e.g., students affect parents).
- **Critical Threshold Check**: If any trust level drops below its threshold, **game-over conditions** initiate.

### 3. Narrative Consequence Handler
- **Event Log**: Tracks outcomes (e.g., viral posts, public protests).
- **Headlines & Social Media Posts**: Surface narrative shifts after decisions.
- **Game Over Conditions**: Specific messages explain why Edubot failed (e.g., privacy scandals, regulatory shutdowns).

---

## Gameplay Flow

1. **Player makes a decision** (via buttons).
2. **Immediate trust changes** apply to stakeholders.
3. **Agent influences** cascade:
   - Students impact Parents.
   - Trolls degrade Students/Teachers.
   - Regulators pressure Teachers.
4. **Narrative feedback** appears (e.g., social posts, headlines).
5. **Critical thresholds** are checked:
   - If any stakeholder trust drops too low → **Game Over**.
   - Otherwise → Proceed to the next chapter.
6. **Victory Conditions**:
   - Maintain stakeholder trust above thresholds across all five chapters.

---

## Data Structures

### Stakeholders

```javascript
const stakeholders = {
  students: { trust: 0.75, threshold: 0.3 },
  parents: { trust: 0.8, threshold: 0.4 },
  teachers: { trust: 0.7, threshold: 0.4 },
  regulators: { trust: 0.65, threshold: 0.4 },
  trolls: { trust: 0.15 }
};
```
## Trust System Overview

- **Trust** is dynamically updated based on player decisions.
- Each stakeholder’s trust level is visualized through **animated CSS trust bars**.
- **Thresholds** define critical failure points where consequences trigger.

---

## Stakeholders as Agents and Their Interactions

In **AI Ethics Quest**, stakeholders act as **agents** within a dynamic system. They not only respond to player decisions but also **influence one another**, mimicking social dynamics and regulatory pressures seen in real-world AI ethics debates.

### Stakeholder Roles and Influences

| Stakeholder | Role                      | Trust Sensitivities                     | Influence on Others                   | Narrative Impact                                                        |
|-------------|----------------------------|------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|
| **Students**   | Primary users              | Bias, misinformation, privacy breaches   | Impact Parents' trust                  | Low trust = Student boycotts, disengagement, social backlash            |
| **Parents**    | Guardians of student well-being | Privacy, student well-being           | Amplify public sentiment               | Low trust = Parent protests, withdrawal of consent                      |
| **Teachers**   | Advocates for fairness     | Bias, misinformation                    | Amplify regulatory scrutiny            | Low trust = Public criticism, opinion pieces, forums                    |
| **Regulators** | Oversight bodies           | Scandals (privacy, data misuse)          | Pressure Teachers for compliance       | Low trust = Sanctions, shutdowns, investigations                        |
| **Trolls**     | External disruptors        | N/A (disruptive agent)                   | Degrade trust of Students and Teachers | Viral misinformation campaigns, exploit system weaknesses               |

---

### Agent Influence Mechanics

- **Students → Parents**: When Students lose trust (e.g., due to bias or misinformation), **Parents' trust also declines**. This reflects how student dissatisfaction drives parental concern.

- **Teachers → Regulators**: Teachers act as **watchdogs**. If Teachers lose trust, they amplify concerns, prompting **Regulatory scrutiny** or intervention.

- **Trolls → Students/Teachers**: Trolls act as **passive disruptors**, degrading trust for Students and Teachers over time. Their influence represents **external threats**, such as misinformation or viral controversies.

- **Regulators → Teachers**: When Regulatory trust drops, **pressure mounts on Teachers** to suspend Edubot usage, pushing for reforms or compliance.

---

## Chapters and Agent Dynamics

Each chapter presents an **ethical dilemma** with distinct agent interactions:

- **Chapter 1 (The Data Dilemma)**: Students and Regulators lose trust → Parents follow.
- **Chapter 2 (The Bias Crisis)**: Teachers raise concerns → Regulatory scrutiny increases.
- **Chapter 3 (Hallucination Hazards)**: Trolls amplify misinformation → Students and Teachers' trust erodes.
- **Chapter 4 (Privacy Predicament)**: Regulatory action leads Teachers to suspend Edubot.
- **Chapter 5 (Learning from Users)**: Trolls corrupt Edubot in real-time → trust collapses among Students and Teachers.

These **multi-agent interactions** ensure that player decisions reverberate throughout the system, creating **emergent consequences**.

---

## UI & Visualization

- **Trust Bars**: CSS-based horizontal bars for each stakeholder, animated for real-time trust updates.
- **Chapter Images**: Background visuals dynamically reflect the chapter’s ethical dilemma.
- **Narrative Feedback**:
  - **Headlines** (e.g., _"Edubot Faces Bias Allegations"_)
  - **Social Media Posts** (e.g., viral tweets, leaked screenshots)
  - **Event Logs** (chronological record of key events)

---

## Narrative & Mechanics Integration

| Stakeholder | Trigger Threshold | Narrative Outcome                                      |
|-------------|-------------------|--------------------------------------------------------|
| **Students**   | Below 0.3          | Boycott, disengagement, peer-led backlash               |
| **Parents**    | Below 0.4          | Parents withdraw consent, public protests               |
| **Teachers**   | Below 0.4          | Teachers publicly criticize Edubot                      |
| **Regulators** | Below 0.4          | Regulatory shutdown or investigation                    |
| **Trolls**     | N/A                | Spread misinformation, escalate trust erosion           |

---

## Future Expansion (Scalable Design)

- **Modular JavaScript**: Easily extendable to add new chapters, stakeholders, or scenarios.

### Potential Additions

- **Persistent storage**: Local storage or backend integration for saving progress.
- **Enhanced visuals**: Animations, sound effects for deeper immersion.
- **Adaptive difficulty**: Trust thresholds or troll influence could vary based on player performance.

---

This architecture balances **game mechanics**, **ethical narratives**, and **agent-based dynamics** to create an engaging, educational experience on the complexities of AI development.
