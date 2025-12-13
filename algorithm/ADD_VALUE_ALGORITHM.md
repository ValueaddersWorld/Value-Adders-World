# The ADD VALUE Algorithm

## A Complete Technical Reference

---

## Overview

The ADD VALUE Algorithm is an 8-step cognitive protocol that converts insight into measurable action. It is implemented as a state machine where each pillar represents a transformation gate.

```
Input: Raw situation/challenge
Output: Measurable progress + Identity evolution
```

---

## The Algorithm

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        THE ADD VALUE ALGORITHM                              │
│                                                                             │
│  ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐                     │
│  │    A    │ → │    D    │ → │    D    │ → │    V    │    ← PREPARATION    │
│  │AWARENESS│   │ DEFINE  │   │ DEVISE  │   │VALIDATE │      PHASE          │
│  │         │   │         │   │         │   │         │                     │
│  │ input:  │   │ input:  │   │ input:  │   │ input:  │                     │
│  │ reality │   │ truth   │   │ target  │   │ plan    │                     │
│  │         │   │         │   │         │   │         │                     │
│  │ output: │   │ output: │   │ output: │   │ output: │                     │
│  │ truth   │   │ target  │   │ plan    │   │evidence │                     │
│  └────┬────┘   └────┬────┘   └────┬────┘   └────┬────┘                     │
│       │             │             │             │                           │
│       ▼             ▼             ▼             ▼                           │
│  ╔═════════════════════════════════════════════════════╗                   │
│  ║         GATE: ready_to_act = True?                  ║                   │
│  ║         (All 4 preparation pillars complete)        ║                   │
│  ╚═════════════════════════════════════════════════════╝                   │
│                            │                                                │
│                            ▼                                                │
│  ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐                     │
│  │    E    │ ← │    U    │ ← │    L    │ ← │    A    │    ← EXECUTION      │
│  │ EVOLVE  │   │UNDERSTAND│   │  LEARN  │   │ACT UPON │      PHASE         │
│  │         │   │         │   │         │   │         │                     │
│  │ input:  │   │ input:  │   │ input:  │   │ input:  │                     │
│  │ pattern │   │ lessons │   │ result  │   │evidence │                     │
│  │         │   │         │   │         │   │         │                     │
│  │ output: │   │ output: │   │ output: │   │ output: │                     │
│  │identity │   │ pattern │   │ lessons │   │ result  │                     │
│  └─────────┘   └─────────┘   └─────────┘   └─────────┘                     │
│                                                                             │
│  ╔═════════════════════════════════════════════════════╗                   │
│  ║         GATE: cycle_complete = True?                ║                   │
│  ║         (All 8 pillars complete → Loop back)        ║                   │
│  ╚═════════════════════════════════════════════════════╝                   │
│                            │                                                │
│                            ▼                                                │
│                      ↻ NEXT CYCLE                                           │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Pillar Specifications

### Phase 1: Preparation (A-D-D-V)

#### A — AWARENESS

| Property | Value |
|----------|-------|
| **Purpose** | Neutralize emotional blindness |
| **Input** | Raw reality (situation, data, context) |
| **Output** | Truth (unfiltered perception) |
| **Gate** | `truth != comfortable_narrative` |

```python
def awareness(situation: Situation) -> Truth:
    """
    Extract truth from situation without emotional distortion.
    
    Failure mode destroyed: Emotional blindness
    """
    raw_data = observe(situation)
    filtered = remove_bias(raw_data)
    truth = extract_core(filtered)
    
    assert truth.is_uncomfortable or truth.is_validated
    return truth
```

**Key Question:** *What is actually happening — not what I want to be happening?*

---

#### D — DEFINE

| Property | Value |
|----------|-------|
| **Purpose** | Remove ambiguity |
| **Input** | Truth (from Awareness) |
| **Output** | Target (measurable, binary) |
| **Gate** | `target.is_measurable and target.is_binary` |

```python
def define(truth: Truth) -> Target:
    """
    Convert truth into a clear, measurable target.
    
    Failure mode destroyed: Ambiguity
    """
    problem = identify_core_problem(truth)
    success_criteria = create_binary_metric(problem)
    target = Target(
        problem=problem,
        success_criteria=success_criteria,
        is_measurable=True
    )
    
    assert can_answer_yes_or_no(target.success_criteria)
    return target
```

**Key Question:** *What exactly does success look like — in measurable terms?*

---

#### D — DEVISE

| Property | Value |
|----------|-------|
| **Purpose** | Reduce cognitive load |
| **Input** | Target (from Define) |
| **Output** | Plan (minimum viable action) |
| **Gate** | `plan.steps <= 3 and plan.first_step.duration < 15min` |

```python
def devise(target: Target) -> Plan:
    """
    Create minimum viable action plan.
    
    Failure mode destroyed: Cognitive overload
    """
    all_paths = generate_paths(target)
    simplest = select_minimum_viable(all_paths)
    plan = Plan(
        steps=simplest.steps[:3],  # Max 3 steps
        first_step=create_15min_action(simplest)
    )
    
    assert len(plan.steps) <= 3
    assert plan.first_step.can_complete_in_15min
    return plan
```

**Key Question:** *What is the smallest action that creates irreversible forward momentum?*

---

#### V — VALIDATE

| Property | Value |
|----------|-------|
| **Purpose** | Dissolve fear-based hesitation |
| **Input** | Plan (from Devise) |
| **Output** | Evidence (confirmation data) |
| **Gate** | `evidence.confidence >= threshold` |

```python
def validate(plan: Plan) -> Evidence:
    """
    Replace anxiety with evidence.
    
    Failure mode destroyed: Fear-based hesitation
    """
    assumptions = extract_assumptions(plan)
    tests = design_quick_tests(assumptions)
    results = run_tests(tests)
    evidence = Evidence(
        assumptions=assumptions,
        test_results=results,
        confidence=calculate_confidence(results)
    )
    
    assert evidence.confidence >= MINIMUM_CONFIDENCE
    return evidence
```

**Key Question:** *What evidence exists that this will work — before I commit fully?*

---

### Decision Gate: Ready to Act

```python
def ready_to_act(decision: Decision) -> bool:
    """
    Check if preparation phase is complete.
    All 4 pillars must be satisfied before action.
    """
    return all([
        decision.awareness.completed,
        decision.define.completed,
        decision.devise.completed,
        decision.validate.completed,
    ])
```

---

### Phase 2: Execution (A-L-U-E)

#### A — ACT UPON

| Property | Value |
|----------|-------|
| **Purpose** | Force micro-commitment |
| **Input** | Evidence (from Validate) |
| **Output** | Result (observable outcome) |
| **Gate** | `result.is_observable` |

```python
def act_upon(evidence: Evidence, plan: Plan) -> Result:
    """
    Execute the first step. Create visible evidence.
    
    Failure mode destroyed: Infinite delay
    """
    first_step = plan.first_step
    
    # Force action within 15 minutes
    with timeout(minutes=15):
        outcome = execute(first_step)
    
    result = Result(
        action_taken=first_step,
        outcome=outcome,
        timestamp=now(),
        is_observable=True
    )
    
    assert result.is_observable
    return result
```

**Key Question:** *What action in the next 15 minutes creates visible evidence of movement?*

---

#### L — LEARN

| Property | Value |
|----------|-------|
| **Purpose** | Remove shame from feedback |
| **Input** | Result (from Act Upon) |
| **Output** | Lessons (ego-free insights) |
| **Gate** | `lessons.blame_score == 0` |

```python
def learn(result: Result) -> Lessons:
    """
    Extract lessons without ego or shame.
    
    Failure mode destroyed: Shame spiral
    """
    facts = extract_facts(result)
    
    # Separate identity from outcome
    lessons = Lessons(
        what_happened=facts,
        what_worked=identify_successes(facts),
        what_didnt=identify_failures(facts),
        surprises=identify_unexpected(facts),
        blame_score=0  # Never assign blame
    )
    
    assert "I am bad" not in lessons.conclusions
    assert "I failed" not in lessons.conclusions
    return lessons
```

**Key Question:** *What did this attempt reveal — without making it mean something about me?*

---

#### U — UNDERSTAND

| Property | Value |
|----------|-------|
| **Purpose** | Upgrade pattern recognition |
| **Input** | Lessons (from Learn) |
| **Output** | Pattern (reusable mental model) |
| **Gate** | `pattern.applies_to_count >= 3` |

```python
def understand(lessons: Lessons) -> Pattern:
    """
    Extract reusable patterns from specific lessons.
    
    Failure mode destroyed: Pattern blindness
    """
    specific_lesson = lessons.core_insight
    
    # Generalize to pattern
    pattern = Pattern(
        trigger=identify_trigger(specific_lesson),
        mechanism=identify_mechanism(specific_lesson),
        applies_to=find_similar_situations(specific_lesson),
        mental_model=create_mental_model(specific_lesson)
    )
    
    assert len(pattern.applies_to) >= 3  # Must be reusable
    return pattern
```

**Key Question:** *What pattern does this reveal that I'll see again in different forms?*

---

#### E — EVOLVE

| Property | Value |
|----------|-------|
| **Purpose** | Lock identity change |
| **Input** | Pattern (from Understand) |
| **Output** | Identity (permanent upgrade) |
| **Gate** | `identity.requires_motivation == False` |

```python
def evolve(pattern: Pattern, current_identity: Identity) -> Identity:
    """
    Lock the learning into identity.
    
    Failure mode destroyed: Regression
    """
    behavior_change = pattern.to_behavior()
    
    # Integrate into identity (not just behavior)
    new_identity = Identity(
        base=current_identity,
        new_trait=f"I am someone who {behavior_change}",
        requires_motivation=False,  # Identity doesn't need willpower
        is_permanent=True
    )
    
    record_visible_evidence(new_identity)
    
    assert new_identity.requires_motivation == False
    return new_identity
```

**Key Question:** *How has this changed who I am — not just what I do?*

---

## Complete Cycle

```python
def add_value_cycle(situation: Situation) -> CycleResult:
    """
    Complete ADD VALUE cycle.
    
    Promise: Visible evidence within 7-30 days,
             even if motivation disappears.
    """
    # Phase 1: Preparation
    truth = awareness(situation)
    target = define(truth)
    plan = devise(target)
    evidence = validate(plan)
    
    # Gate check
    decision = Decision(truth, target, plan, evidence)
    if not ready_to_act(decision):
        return CycleResult(status="blocked", blocker=find_incomplete_pillar(decision))
    
    # Phase 2: Execution
    result = act_upon(evidence, plan)
    lessons = learn(result)
    pattern = understand(lessons)
    identity = evolve(pattern, current_identity())
    
    return CycleResult(
        status="complete",
        visible_evidence=result.outcome,
        identity_shift=identity.new_trait,
        pattern_learned=pattern.mental_model,
        ready_for_next_cycle=True
    )
```

---

## Data Structures

### Pillar Enum

```python
from enum import Enum

class Pillar(Enum):
    """The 8 pillars of the ADD VALUE Algorithm."""
    
    # Phase 1: Preparation
    AWARENESS = "A"       # Neutralize emotional blindness
    DEFINE = "D1"         # Remove ambiguity
    DEVISE = "D2"         # Reduce cognitive load
    VALIDATE = "V"        # Dissolve fear-based hesitation
    
    # Phase 2: Execution
    ACT_UPON = "A2"       # Force micro-commitment
    LEARN = "L"           # Remove shame from feedback
    UNDERSTAND = "U"      # Upgrade pattern recognition
    EVOLVE = "E"          # Lock identity change
```

### Pillar State

```python
@dataclass
class PillarState:
    """Track completion state of a pillar."""
    
    pillar: Pillar
    completed: bool = False
    input_data: Any = None
    output_data: Any = None
    timestamp: datetime = None
    
    def complete(self, output: Any) -> None:
        self.completed = True
        self.output_data = output
        self.timestamp = datetime.now()
```

### Decision Tracker

```python
@dataclass
class Decision:
    """Track progress through the ADD VALUE cycle."""
    
    situation: str
    agent: str
    pillars: Dict[Pillar, PillarState]
    visible_evidence: List[str] = field(default_factory=list)
    identity_shifts: List[str] = field(default_factory=list)
    
    @property
    def ready_to_act(self) -> bool:
        """First 4 pillars complete = ready to execute."""
        return all([
            self.pillars[Pillar.AWARENESS].completed,
            self.pillars[Pillar.DEFINE].completed,
            self.pillars[Pillar.DEVISE].completed,
            self.pillars[Pillar.VALIDATE].completed,
        ])
    
    @property
    def cycle_complete(self) -> bool:
        """All 8 pillars complete = full evolution."""
        return all(p.completed for p in self.pillars.values())
    
    def document_evidence(self, evidence: str) -> None:
        """Record visible proof of progress."""
        self.visible_evidence.append(evidence)
    
    def document_identity_shift(self, shift: str) -> None:
        """Record identity change."""
        self.identity_shifts.append(shift)
```

---

## Usage Example

### For Humans

```python
# Situation: I want to start exercising but keep procrastinating

cycle = AddValueCycle("Start exercising consistently")

# A - Awareness
cycle.awareness("""
    Truth: I haven't exercised in 3 months. 
    I feel physically weak. I avoid mirrors.
    I tell myself I'll start Monday, but I never do.
""")

# D - Define  
cycle.define("""
    Target: Do 10 push-ups tomorrow morning.
    Success criteria: Did I do 10 push-ups? Yes or No.
""")

# D - Devise
cycle.devise("""
    Plan: 
    1. Put workout clothes by bed tonight
    2. When alarm goes, put on clothes immediately
    3. Do 10 push-ups before anything else
""")

# V - Validate
cycle.validate("""
    Evidence: 
    - I can physically do 10 push-ups (tested just now)
    - This takes less than 2 minutes
    - No equipment needed
    Confidence: 95%
""")

# Ready to act? YES

# A - Act Upon
cycle.act_upon("""
    Result: Did 10 push-ups at 6:47 AM.
    Evidence: Recorded video on phone.
""")

# L - Learn
cycle.learn("""
    Lessons:
    - Putting clothes out made it automatic
    - Morning is actually easier than evening
    - 10 push-ups felt too easy (good starting point)
""")

# U - Understand
cycle.understand("""
    Pattern: The hardest part is the transition, not the activity.
    Applies to: Starting work, making calls, writing, all "dreaded" tasks.
    Mental model: "Reduce friction before the moment of truth"
""")

# E - Evolve
cycle.evolve("""
    Identity: I am someone who exercises in the morning.
    No motivation required - it's just who I am now.
""")
```

### For AI Agents

```python
class ValueAdderAgent:
    """AI agent using the ADD VALUE Algorithm."""
    
    def __init__(self, name: str):
        self.name = name
        self.framework = AddValueFramework(agent_name=name)
    
    def process(self, task: str) -> Result:
        decision = self.framework.new_decision(task)
        
        # Phase 1: Preparation
        self.framework.awareness(decision, self.perceive_context())
        self.framework.define(decision, self.extract_objective())
        self.framework.devise(decision, self.create_plan())
        self.framework.validate(decision, self.run_validation())
        
        if decision.ready_to_act:
            # Phase 2: Execution
            result = self.execute()
            self.framework.act(decision, result)
            self.framework.learn(decision, self.analyze_outcome(result))
            self.framework.understand(decision, self.extract_pattern())
            self.framework.evolve(decision, self.update_self())
            
            return result
        
        return self.request_more_info(decision)
```

---

## Key Properties

### Invariants

1. **No action without validation** — `act_upon()` requires `validate().confidence >= threshold`
2. **No learning with shame** — `learn().blame_score == 0` always
3. **No evolution without pattern** — `evolve()` requires `understand().applies_to >= 3`
4. **Identity over willpower** — `evolve().requires_motivation == False`

### Complexity

| Operation | Time Complexity |
|-----------|-----------------|
| Single pillar | O(1) |
| Full cycle | O(n) where n = complexity of situation |
| Cycle stacking | O(cycles × n) |

### Guarantees

| Promise | Mechanism |
|---------|-----------|
| Progress within 7-30 days | Forced micro-commitment in Act Upon |
| Works without motivation | Identity locking in Evolve |
| Compounds over time | Pattern library accumulation in Understand |

---

## Integration

See the [Technical Documentation](../whitepaper/ADD_VALUE_FRAMEWORK.md) for integration with:

- LangChain agents
- AutoGen multi-agent systems
- Custom AI implementations
- Human coaching applications

---

<div align="center">

**The ADD VALUE Algorithm**

*Converts insight into behavior — reliably.*

💜 *Add Value. We Flourish & Prosper.* 💜

</div>
