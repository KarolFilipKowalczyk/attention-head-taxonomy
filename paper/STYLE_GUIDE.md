# Style Guide: Attention Head Naming Convention Paper

**Author:** Karol Kowalczyk  
**Document Type:** Academic Paper (LaTeX)  
**Last Updated:** November 2025 (Revised Edition)

---

## CRITICAL: CONCISENESS REQUIREMENTS

### Priority 1: Eliminate Verbosity
- **Target:** Reduce document by 25-30% without losing information
- **Maximum function description:** 3-5 sentences (was 4-8)
- **Remove all redundant explanations**
- **One concept per sentence**

### Priority 2: Avoid Repetition
- **Never repeat the same concept in different words**
- **Don't explain what's already clear from context**
- **Merge similar ideas into single statements**

---

## 1. Author Voice

### 1.1 Singular Author
- **Use:** "I" for author references
- âœ… "I propose..." / âŒ "We propose..."
- Alternative: "This work introduces..." (avoid overuse)

### 1.2 Community Reference
- Use "we" ONLY for: "We as a community..."

---

## 2. Plurality and Agreement

### 2.1 Head Descriptions
- **Always plural** for head types: "These heads detect..."
- **Exception:** "This head type" when discussing category

### 2.2 Consistency Rule
- Plural verbs with plural subjects throughout
- âœ… "These heads perform" / âŒ "This head performs"

---

## 3. Voice and Tense

### 3.1 Active Voice Mandatory
- âœ… "These heads detect" / âŒ "Detection is performed by"
- Passive ONLY for: "was observed", "were measured" (results)

### 3.2 Present Tense Default
- Head descriptions: Present
- Literature: Present ("Elhage et al. demonstrate")
- Past studies: Past ("Previous work identified")

---

## 4. Technical Terminology

### 4.1 First-Use Rules
| Term | First Use | Later |
|------|-----------|-------|
| Attention head | "attention head" | "head" |
| Stack | "stack" | "stack" |
| Depth | "relative depth" | "depth" |

### 4.2 Hyphenation
- Compound adjectives before nouns: "well-documented head"
- No hyphen after verbs: "is well documented"

### 4.3 Abbreviations
- Always with comma: "e.g.," "i.e.,"
- Minimize use of "etc." in academic writing

---

## 5. Numbers and Ranges

### 5.1 Numbers
- Spell: one through nine
- Numerals: 10+, all decimals, all percentages

### 5.2 Ranges
- LaTeX en-dash: `0.05--0.20`
- CRITICAL: Check all depth ranges for consistency

---

## 6. Punctuation

### 6.1 LaTeX Quotes
- Use `` ``text'' `` not "text"
- Technical terms: `\texttt{JSON}`

### 6.2 Citations
- End of sentence preferred
- Non-breaking space: `work~\cite{}`

---

## 7. REVISED HEAD ENTRY STRUCTURE

### 7.1 Mandatory Compact Format

```latex
\subsubsection{(DEPTH) Head-Name Heads}
\label{head:label}

\noindent\depthinfo{0.XX--0.YY} | \litnames{alt1, alt2}

\begin{functiondesc}
[PRIMARY FUNCTION - 1 sentence]. [MECHANISM - 1-2 sentences]. 
[KEY DISTINCTION or IMPORTANCE - 1 sentence]. [MAX 3-5 sentences total]
\end{functiondesc}

\begin{attentionbox}
\attstrong{Primary targets (3-4 items max)}\\
\attweak{Secondary (2-3 items max)}\\
\attreacts{Triggers (2-3 items max)}
\end{attentionbox}

\begin{ablationbox}
\textbf{Expected ablation:} [ONE primary effect]. [ONE secondary if critical]. [MAX 2 sentences]
\end{ablationbox}

\begin{examplebox}
\exinput{Brief input}\\
\exbehavior{Concise action}\\
\exeffect{Direct result}
\end{examplebox}

\headfooter{\statusXXX}{related1 (D), related2 (D), related3 (D)}
```

---

## 8. CONCISENESS PATTERNS

### 8.1 Function Descriptions - STRICT RULES

**FORBIDDEN Patterns:**
- âŒ "These heads are particularly important for..."
- âŒ "It's important to note that these heads..."
- âŒ "These heads work by [verb]ing... They also [verb]..."
- âŒ "Acting as... these heads..."
- âŒ "Essential for... they..."
- âŒ Explaining the same concept twice

**REQUIRED Patterns:**
- âœ… Subject-Verb-Object, period.
- âœ… Combine related functions in one sentence
- âœ… Remove "particularly", "especially", "notably" (usually redundant)

**Before (verbose):**
```
Detect and process delimiter tokens that mark boundaries between 
structural elements. These heads recognize punctuation marks, brackets, 
delimiters, and special characters that indicate separation or grouping. 
They also process whitespace characters as structural elements rather 
than mere separators. Particularly important for languages where 
whitespace is syntactically significant, these heads distinguish between 
semantically meaningful whitespace and irrelevant spacing.
```

**After (concise):**
```
Detect delimiter tokens (punctuation, brackets, whitespace) that mark 
structural boundaries. Process whitespace as semantic in languages like 
Python and YAML. Distinguish meaningful spacing from formatting.
```

### 8.2 Attention Patterns - MINIMIZE

**FORBIDDEN:**
- Long lists of similar items
- Redundant descriptions
- Overlapping categories

**REQUIRED:**
- Group similar items: "punctuation and brackets" not "commas, periods, semicolons, brackets"
- Maximum 3-4 items per category

### 8.3 Ablation Descriptions - BE PRECISE

**FORBIDDEN:**
- âŒ Vague terms: "degradation", "issues", "problems"
- âŒ Redundant impact descriptions
- âŒ Long explanations of compensation

**REQUIRED:**
- âœ… Specific impact: "15% accuracy loss on task X"
- âœ… One primary, one secondary effect max
- âœ… If compensation exists, mention in 3 words max

**Before:**
```
Moderate reduction in boundary awareness and degraded segmentation. 
Model may blur distinctions between sections, miss paragraph boundaries, 
or fail to recognize document structure. Reduced performance on 
multi-section documents.
```

**After:**
```
Loses section boundaries in multi-part documents. 20% degradation on 
document segmentation tasks.
```

---

## 9. Depth Ranges

### 9.1 STRICT CONSISTENCY REQUIREMENTS

**Depth Boundaries (MUST be consistent):**
- Early (E): 0.00--0.25
- Middle (M): 0.25--0.70  
- Late (L): 0.70--0.88
- Final (F): 0.88--1.00

**Verification Rules:**
- Every head's depthinfo range MUST fall within its category
- Overlaps between categories should be minimal (<0.05)
- Use realistic precision (0.05 increments typical)

### 9.2 Cross-Reference Format
- Always include depth: "induction (M)"
- Maximum 3 related heads (not 3-5)

---

## 10. Common Redundancies to Remove

### 10.1 Redundant Phrases (DELETE ON SIGHT)
- "It is important to note that" → [delete]
- "These heads work by" → "These heads"
- "Particularly important for" → "Important for" or [delete]
- "Acts as a" → [delete]
- "Serves to" → [delete]
- "Functions to" → [delete]
- "In order to" → "To"
- "Is able to" → "Can"

### 10.2 Redundant Explanations
- Don't explain what attention means
- Don't explain what ablation means after first use
- Don't explain obvious mechanisms

### 10.3 Merge Similar Concepts
- "Detect and identify" → "Detect"
- "Process and handle" → "Process"
- "Maintain and preserve" → "Maintain"

---

## 11. Stack Overview Requirements

### 11.1 Maximum Length
- **2 sentences maximum** for stack overview
- Sentence 1: What the stack does
- Sentence 2: Key components or mechanism (if needed)

### 11.2 Forbidden in Overviews
- Lists of all heads in the stack
- Detailed mechanisms (save for individual entries)
- Importance statements (implied by inclusion)

---

## 12. Example Guidelines

### 12.1 Strict Brevity
- Input: <15 words
- Behavior: <10 words
- Effect: <10 words

### 12.2 Realistic Examples
- Use actual tokens/patterns
- Avoid placeholder text like "[restricted topic]"
- Show mechanism clearly

---

## 13. LaTeX Formatting

### 13.1 Consistency Requirements
- All depth ranges use en-dash: `--`
- All quotes use LaTeX style: `` ``text'' ``
- All cross-refs use: `§\ref{}`

### 13.2 Special Characters
- Arrows in examples: `$\rightarrow$`
- Non-breaking spaces before citations: `~\cite{}`

---

## 14. Quality Metrics

### 14.1 Length Targets
- Function description: 3-5 sentences (50-100 words)
- Ablation: 1-2 sentences (15-30 words)  
- Stack overview: 2 sentences (20-40 words)
- Total document: 30-35 pages (was 45+)

### 14.2 Conciseness Checklist
Before submitting any section:
- [ ] Remove all "particularly", "especially", "notably"
- [ ] Merge redundant verbs ("detect and identify")
- [ ] Delete "It is important", "Acts as", "Serves to"
- [ ] Reduce function descriptions to 3-5 sentences
- [ ] Reduce ablations to 1-2 sentences
- [ ] Verify depth ranges are consistent
- [ ] Remove redundant explanations
- [ ] Check attention patterns have ≤4 items per category

---

## 15. Review Process

### 15.1 Conciseness Pass (FIRST)
1. Count sentences in each function description
2. Delete redundant phrases
3. Merge similar concepts
4. Remove unnecessary examples

### 15.2 Technical Pass
1. Verify depth ranges
2. Check cross-references
3. Confirm LaTeX formatting

### 15.3 Final Pass
1. Read aloud - does it flow?
2. Can anything be cut without losing meaning?
3. Are examples clear and brief?

---

## 16. Enforcement

### MANDATORY: Self-Audit Questions

For EVERY head entry, ask:
1. **Is the function description ≤5 sentences?** If no, CUT.
2. **Does any sentence repeat previous information?** If yes, DELETE.
3. **Are there any redundant adjectives?** If yes, REMOVE.
4. **Is the ablation description ≤2 sentences?** If no, CONDENSE.
5. **Could a reader understand this in half the words?** If yes, REWRITE.

### Red Flags Requiring Immediate Revision:
- Function description >100 words
- Ablation description >30 words  
- Any paragraph >5 sentences
- Use of "particularly" more than once per page
- Attention patterns with >4 items per category

---

## Appendix: Quick Fixes

### Instant Replacements
| Verbose | Concise |
|---------|---------|
| These heads work by detecting | Detect |
| It is important to note that | [delete] |
| Particularly important for | Essential for / [delete] |
| Acts as a mechanism to | [delete] |
| In order to facilitate | To enable |
| Serves the purpose of | [delete] |
| Has the ability to | Can |
| Makes it possible to | Enables |
| Is responsible for | Handles |
| Functions to provide | Provides |

### Sentence Combining Patterns
- Two mechanisms → One compound sentence
- List + explanation → Integrated single sentence  
- Example + importance → Choose one, delete other

---

**END OF STYLE GUIDE**

*Remember: Every word must earn its place. When in doubt, cut it out.*