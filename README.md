# yes-i-said-yes-i-will-Yes

> *A computational approach to centering female interiority in language model training through Joyce's Molly Bloom*

## Overview

Fine-tuning Llama-3.2-1B on Molly Bloom's voice from *Ulysses* to explore what happens when models learn language where female-coded vocabulary, embodied thought, and associative consciousness are foundational rather than peripheral.

A linguistic intervention in what models treat as "standard" versus "marginal" language.

## Research Questions

- What happens when body words (menstruation, pregnancy, flesh) are reweighted to be more frequent than abstract philosophical vocabulary?
- Can models learn that associative leaps (knight's moves) are legitimate coherence, not noise?
- How can bathos be preserved?
- Can stream-of-consciousness, unpunctuated flow become the default rather than deviation?

## Theoretical Grounding

**On Joyce & Computation:**

**On Corpus Politics:**

**On Feminist Linguistics & AI:**

## All hail Molly Bloom

Molly's famous unpunctuated stream-of-consciousness monologue represents:
- 24,000+ words of uninterrupted female interiority
- Refusal of patriarchal punctuation and sentence structure
- Embodied, sensual, domestic language elevated to literary importance
- Multiple registers: interior consciousness, public performance, theatrical self

She's computationally perfect because:
- Large enough corpus for training
- Stylistically distinct and consistent
- Represents underrepresented linguistic patterns in training data
- Challenges "neutral" frequency distributions (Zipf in whose world?)

## Three-Stage Training Pipeline

### Stage 1: Vocabulary Foundation

**Source:** All Molly text across *Ulysses*  
**Method:** Frequency-based vocabulary extraction with feminist reweighting

Reorganize token frequencies to center (not add-on):
- Body/embodiment vocabulary
- Domestic/interior spaces  
- Female desire (not male gaze)
- "Vulgar" or "improper" women's language
- Relational/emotional vocabulary
- Material concerns (money, household, clothing)

**aim:** teaches model her vocabulary with female language as primary register

### Stage 2: Public Voice (Lighter Weight)

**Source:** Molly's dialogue throughout *Ulysses*, including *Circe* episode  
**Method:** Standard fine-tuning with preserved punctuation

**aim:** teaches model conversational register, performance mode, code-switching between public/private self

### Stage 3: Interior Consciousness (Heavy Weight)

**Source:** Stream-of-consciousness sections (*Penelope* + interior monologue)  
**Method:** **Overlap-cluster melting**

- Identify thematic clusters (loose topic groupings)
- Create overlapping windows between adjacent clusters
- Strip punctuation in overlap zones
- Preserve run-on quality and associative chains
- Split only at genuine lateral leaps (knight's moves)

**aim:** teaches model pure consciousness flow, bathos, embodied thought

## Dataset Construction: Overlap-Cluster Melting

Traditional segmentation imposes artificial boundaries on stream-of-consciousness text. Approach:
```
Cluster A: [...topics about Gibraltar...]
                    ↓ OVERLAP ZONE (50-200 tokens)
                    ↓ Punctuation stripped
                    ↓ Boundaries melted
Cluster B: [...topics about Bloom's shirt...]
```

Preservation of:
- Momentum across thematic transitions
- Bathetic crashes (high → low register)
- Associative logic that appears non-sequitur but has dream coherence
- Temporal fluidity (past/present bleeding)

## Technical Implementation

**Base Model:** Llama-3.2-1B  
**Method:** QLoRA (4-bit quantization + Low-Rank Adaptation)  
**Infrastructure:** Google Colab (T4 GPU)

**Memory Optimizations:**
- 4-bit quantization with nested quantization
- Gradient checkpointing
- 8-bit paged optimizer (AdamW)
- Batch size 1 with gradient accumulation (16-32 steps)

**Training Progression:**  
Stage 1 → Stage 2 → Stage 3 (sequential fine-tuning, each stage loads previous adapters)

## Dual-Mode Generation

The trained model supports two prompting modes:

**Interior Consciousness:**
```
[Instruction: Stream of consciousness, Molly's thoughts]
```
→ Unpunctuated, associative, embodied, bathetic, run-on

**Public Speech:**
```
[Instruction: Molly speaking]
```
→ Conversational register, more structured, performance mode

## Political Intervention

Stylistics and an attempt to:

1. Challenge default corpus statistics 
2. Center marginalized linguistic patterns
3. Assert alternative coherence structures
4. Retrain attention

If language models learn from text, and text overwhelmingly centers male experience, male vocabulary, and patriarchal structure as "neutral" or "standard," then every model is already politically encoded.

Molly brings the quesiton: what happens if we intentionally train otherwise?

## Project Status

- [x] Theoretical framework
- [x] Three-stage pipeline design  
- [ ] Corpus extraction from *Ulysses*
- [ ] Overlap-cluster melting implementation
- [ ] Stage 1: Vocabulary training
- [ ] Stage 2: Public voice training
- [ ] Stage 3: Interior consciousness training
- [ ] Dual-mode inference testing
- [ ] Evaluation & analysis

## Reproducibility

[Coming: detailed setup instructions, corpus preprocessing scripts, training configs]




