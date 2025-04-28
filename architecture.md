
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
