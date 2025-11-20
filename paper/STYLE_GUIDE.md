# Style Guide: Attention Head Naming Convention Paper

**Author:** Karol Kowalczyk  
**Document Type:** Academic Paper (LaTeX)  
**Last Updated:** November 2025

---

## 1. Author Voice

### 1.1 Singular Author
- **Use:** "I" for all author references
- **Examples:**
  - ✅ "I propose a unified naming framework"
  - ✅ "This work introduces..."
  - ✅ "I believe this taxonomy provides..."
  - ❌ "We propose a unified naming framework"
  - ❌ "Our work introduces..."

### 1.2 When to Use "We"
- Only when referring to the research community collectively
- Example: ✅ "We as a community have identified numerous..."
- Never use "we" to mean "the author" or "the reader and author"

---

## 2. Plurality and Agreement

### 2.1 Head Descriptions
- **Rule:** When describing a head type, use plural unless specifically discussing a single instance
- **Stack overviews:** Plural (describing multiple heads)
- **Individual entries:** Plural (the head type represents many instances)

**Examples:**
- ✅ "These heads detect and process delimiter tokens"
- ✅ "Induction heads operate by attending to tokens"
- ✅ "This head type performs..." (when emphasizing the type itself)
- ❌ "This head detects and processes delimiter tokens"

### 2.2 Function Descriptions
- Use plural verbs with plural subjects
- **Pattern:** "These heads [plural verb] by [gerund]..."
- ✅ "These heads identify boundaries by attending to..."
- ✅ "Name-mover heads copy entity names by..."

### 2.3 Attention Pattern Descriptions
- Maintain subject-verb agreement
- ✅ "These heads attend strongly to..."
- ✅ "They react to punctuation marks"

---

## 3. Voice and Tense

### 3.1 Preferred Voice
- **Active voice** is preferred for clarity and directness
- ✅ "These heads detect harmful content"
- ❌ "Harmful content is detected by these heads"

**Exceptions where passive is acceptable:**
- When the actor is unknown or unimportant
- In results/findings sections: "was observed", "were measured"

### 3.2 Tense Usage

| Section Type | Tense | Example |
|--------------|-------|---------|
| Literature review | Present | "Elhage et al. demonstrate that..." |
| Methodology | Present | "I organize heads into stacks" |
| Head descriptions | Present | "These heads perform pattern matching" |
| Past studies | Past | "Previous work identified several head types" |
| Results/Findings | Past | "Ablation experiments showed..." |

---

## 4. Technical Terminology

### 4.1 Core Terms

| Term | First Use | Subsequent Uses | Notes |
|------|-----------|-----------------|-------|
| Attention head | "attention head" | "head" | Always lowercase unless proper name |
| Transformer | "transformer" | "transformer" | Lowercase (not a proper noun) |
| Stack | "stack" or "functional stack" | "stack" | Lowercase |
| Depth | "depth" or "relative depth" | "depth" | Use "relative depth" for 0.0-1.0 scale |

### 4.2 Compound Terms
- **Hyphenate compound adjectives** before nouns
- ✅ "cross-paper comparison", "multi-layer processing", "task-mode head"
- ✅ "well-documented head type" (before noun)
- ✅ "This head type is well documented" (after verb, no hyphen)

### 4.3 Abbreviations
- **Format:** Always include comma after abbreviation
- ✅ "e.g., pattern matching"
- ✅ "i.e., the model understands"
- ❌ "e.g. pattern matching"

**Common abbreviations:**
- e.g., (exempli gratia - for example)
- i.e., (id est - that is)
- etc., (et cetera - and so forth) [use sparingly in academic writing]

---

## 5. Number and Quantity Formatting

### 5.1 Spelling Out Numbers
- **Spell out:** One through nine (except in data/measurements)
- **Use numerals:** 10 and above

**Examples:**
- ✅ "three head types", "five examples", "seven stacks"
- ✅ "12 layers", "48 heads", "96-layer model"
- ✅ "0.35 relative depth" (always use numerals for decimals)

### 5.2 Percentages
- Always use numerals with % symbol
- ✅ "15% degradation", "3.2% growth"

### 5.3 Ranges
- Use en-dash (--) in LaTeX for ranges
- ✅ `0.05--0.20`, `12--24 layers`
- ❌ `0.05-0.20` (hyphen)

---

## 6. Punctuation and Formatting

### 6.1 Quotations
- **LaTeX style:** Use `` `text' `` or `` ``text'' `` for proper quotes
- **For code/technical terms:** Use `\texttt{}`
- ✅ `` ``induction head'' ``
- ✅ `\texttt{claude-sonnet-4}`
- ❌ "induction head" (straight quotes)

### 6.2 Lists and Enumerations

**In-text lists:**
- Use semicolons between items
- Final item gets "and" before it
- ✅ "The model performs three tasks: detection; classification; and filtering."

**Bulleted lists:**
- Complete sentences: end with period
- Fragments: no punctuation
- Maintain parallel structure

### 6.3 Parenthetical Citations
- Place at end of sentence when possible
- ✅ "Transformers use attention mechanisms \cite{vaswani2017attention}."
- ✅ "As shown by Vaswani et al. \cite{vaswani2017attention}, attention is key."
- Avoid mid-clause citations when possible

---

## 7. Section References

### 7.1 Format
- **Preferred:** Use `§` symbol with `\ref{}`
- ✅ `§\ref{sec:introduction}`
- Alternative: `Section~\ref{sec:introduction}` (with non-breaking space)

### 7.2 Consistency
- Choose one format and use throughout
- **Current choice:** `§\ref{}` for compactness

---

## 8. Head Entry Structure

### 8.1 Standard Entry Format

Each head entry must follow this exact structure:

```latex
\subsubsection{(DEPTH) Head-Name Heads}
\label{head:label}

\noindent\depthinfo{0.XX--0.YY} | \litnames{alt name 1, alt name 2}

\begin{functiondesc}
[Plural description of what these heads do...]
\end{functiondesc}

\begin{attentionbox}
\attstrong{Primary attention targets}\\
\attweak{Weak/secondary targets}\\
\attreacts{Trigger conditions}
\end{attentionbox}

\begin{ablationbox}
\textbf{Expected ablation:} [Plural description of effects...]
\end{ablationbox}

\begin{examplebox}
\exinput{"User input example"}\\
\exbehavior{What the heads do}\\
\exeffect{Result of the behavior}
\end{examplebox}

\headfooter{Status}{Related heads}
```

### 8.2 Function Description Guidelines
- **First sentence:** High-level summary (1-2 lines)
- **Body:** Detailed explanation with mechanisms
- **Length:** 4-8 sentences typical
- **Tone:** Technical but accessible
- **Voice:** Active, plural

**Template:**
```
[Plural verb phrase describing primary function]. [Mechanism explanation]. 
[Additional capabilities]. [Distinguishing features]. [Importance/role]. 
[Relationship to other heads].
```

### 8.3 Attention Pattern Guidelines

**Strong attention:**
- Most important targets
- Primary information sources
- 3-6 items typical

**Weak attention:**
- Secondary targets
- Background information
- 2-4 items typical

**Reacts to:**
- Triggering conditions
- Activation contexts
- 2-5 items typical

### 8.4 Ablation Description Guidelines
- Start with: "**Expected ablation:**"
- Use measurable/observable terms
- Include approximate impact magnitude when known
- Mention compensation mechanisms if any
- Format: "[Primary effect]. [Secondary effects]. [Compensation notes]."

**Impact magnitude terms:**
- "Critical/Severe" (>50% degradation)
- "Significant/Major" (25-50% degradation)
- "Moderate" (10-25% degradation)
- "Reduced/Degraded" (<10% degradation)

### 8.5 Example Guidelines
- **Input:** Clear, concise user query or context
- **Behavior:** What the heads specifically do (mechanism)
- **Effect:** Observable result or output change
- Keep examples under 2 lines each when possible

---

## 9. Depth Indicators

### 9.1 Prefix Usage
- **(E)** = Early (0.00--0.25)
- **(M)** = Middle (0.25--0.70)
- **(L)** = Late (0.70--0.88)
- **(F)** = Final (0.88--1.00)

### 9.2 Format
- Always use parentheses: `(E)`, `(M)`, `(L)`, `(F)`
- Place before head name: `(E) Delimiter Heads`
- Use in cross-references: "delimiter heads (E)"

---

## 10. Status Indicators

### 10.1 Categories
- **\statuswell** = Well-documented (strong empirical evidence)
- **\statusobs** = Observed (reported but less rigorous evidence)
- **\statusprop** = Proposed (theoretical, needs validation)

### 10.2 Usage in Footer
```latex
\headfooter{\statuswell}{related-head-1 (D), related-head-2 (D)}
```

---

## 11. Cross-References and Related Heads

### 11.1 Format
- List related heads with depth indicators
- Separate with commas
- Format: `head-name (DEPTH)`
- Example: `induction (M), name-mover (L), duplicate-token (M)`

### 11.2 Selection Criteria
- **Include:** Direct functional relationships, circuit partners, similar mechanisms
- **Limit:** 3-5 most relevant heads
- **Order:** Typically by processing flow or depth

---

## 12. Common Patterns to Avoid

### 12.1 Wordiness
- ❌ "In order to detect patterns"
- ✅ "To detect patterns"

- ❌ "These heads are able to perform"
- ✅ "These heads perform"

### 12.2 Hedge Words (minimize)
- Minimize: "somewhat", "rather", "quite", "fairly"
- Use sparingly: "may", "might", "could", "possibly"
- Use when accurate: "typically", "generally", "often"

### 12.3 Redundancy
- ❌ "These heads detect and identify patterns"
- ✅ "These heads detect patterns"

- ❌ "completely and entirely"
- ✅ "completely"

---

## 13. LaTeX-Specific Conventions

### 13.1 Spacing
- Use `~` (non-breaking space) before citations: `work~\cite{}`
- Use `~` before references: `Section~\ref{}`
- No space before citations at end: `work\cite{}.`

### 13.2 Special Characters
- En-dash for ranges: `--` → –
- Em-dash for breaks: `---` → —
- Proper quotes: `` ` `` and `'` or `` `` and `''`

### 13.3 Emphasis
- **Bold** for structure: `\textbf{Status:}`
- *Italic* for emphasis: `\textit{particularly}`
- `\texttt{}` for code/technical: `\texttt{JSON}`

---

## 14. Consistency Checklist

Before finalizing any section, verify:

- [ ] Author voice: "I" not "we"
- [ ] Plurality: "These heads" for types
- [ ] Active voice preferred
- [ ] Numbers: spelled out 1-9, numerals 10+
- [ ] Abbreviations: comma after "e.g.," and "i.e.,"
- [ ] Hyphens: compound adjectives before nouns
- [ ] Quotes: LaTeX style backticks
- [ ] Citations: end of sentence when possible
- [ ] Ranges: en-dash (--)
- [ ] Cross-refs: consistent format (§\ref{})

---

## 15. Example Transformations

### Before (Original):
```latex
\begin{functiondesc}
Detects and processes delimiter tokens that mark boundaries. This head 
attends to punctuation marks, brackets, and special characters. We see 
that it is particularly important for structured formats.
\end{functiondesc}
```

### After (Style Guide Applied):
```latex
\begin{functiondesc}
Detect and process delimiter tokens that mark boundaries between 
structural elements. These heads attend to punctuation marks, brackets, 
and special characters. Particularly important for understanding 
structured formats like JSON, CSV, and code blocks.
\end{functiondesc}
```

**Changes applied:**
- Plural verb: "Detects" → "Detect"
- Removed "This head" → "These heads"
- Removed "We see that"
- Active voice maintained
- Added specificity: "like JSON, CSV, and code blocks"

---

## 16. Review Process

### 16.1 First Pass
- Check author voice (I vs we)
- Check plurality (head vs heads)
- Check verb agreement

### 16.2 Second Pass
- Active voice conversion
- Number formatting
- Abbreviation formatting

### 16.3 Final Pass
- Citation placement
- Cross-reference consistency
- LaTeX formatting (quotes, dashes, spacing)

---

## Appendix: Quick Reference

### Common Replacements

| Find | Replace | Context |
|------|---------|---------|
| We propose | I propose | Author voice |
| We introduce | This work introduces | Author voice |
| Our taxonomy | This taxonomy | Possessive |
| This head performs | These heads perform | Plurality |
| The head attends | These heads attend | Plurality |
| This head is able | These heads can | Wordiness |
| in order to | to | Wordiness |
| "text" | \`\`text'' | Quotes |
| e.g. | e.g., | Abbreviation |
| Section \ref{} | §\ref{} | Reference style |

---

**End of Style Guide**

*For questions or clarifications, refer to specific section numbers above.*
