# Style Guide: Attention Head Naming Convention Paper

**Author:** Karol Kowalczyk  
**Document Type:** Academic Paper (LaTeX)  
**Last Updated:** November 2025 (Revised Edition)

---

## CRITICAL: WRITING PHILOSOPHY

### Core Principle: Maximum Information, Minimum Words
Every word must justify its presence. If information can be conveyed in fewer words without loss of precision, use fewer words. Prefer direct statements over elaborate constructions.

### Priority: Clarity Through Brevity
- Write one concept per sentence
- Never repeat the same concept in different words
- Don't explain what's already clear from context
- Merge related ideas into single statements

---

## 1. Author Voice

### 1.1 Singular Author
- **Use:** "I" for author references
- ✓ "I propose..." / ✗ "We propose..."
- Alternative: "This work introduces..." (use sparingly)

### 1.2 Community Reference
- Use "we" ONLY for: "We as a community..."

---

## 2. Plurality and Agreement

### 2.1 Head Descriptions
- **Always plural** for head types: "These heads detect..."
- **Exception:** "This head type" when discussing category

### 2.2 Consistency Rule
- Plural verbs with plural subjects throughout
- ✓ "These heads perform" / ✗ "This head performs"

---

## 3. Voice and Tense

### 3.1 Active Voice Mandatory
- ✓ "These heads detect" / ✗ "Detection is performed by"
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
- Verify all depth ranges for consistency

---

## 6. Punctuation

### 6.1 LaTeX Quotes
- Use `` ``text'' `` not "text"
- Technical terms: `\texttt{JSON}`

### 6.2 Citations
- End of sentence preferred
- Non-breaking space: `work~\cite{}`

---

## 7. HEAD ENTRY STRUCTURE

### 7.1 Mandatory Format

```latex
\subsubsection{(DEPTH) Head-Name Heads}
\label{head:label}

\noindent\depthinfo{0.XX--0.YY} | \litnames{alt1, alt2, alt3}

\begin{functiondesc}
[PRIMARY FUNCTION - 1 sentence]. [MECHANISM - 1-2 sentences]. 
[KEY DISTINCTION or IMPORTANCE - 1 sentence]. [3-5 sentences total]
\end{functiondesc}

\begin{attentionbox}
\attstrong{Primary targets (3-4 items max)}\\
\attweak{Secondary (2-3 items max)}\\
\attreacts{Triggers (2-3 items max)}
\end{attentionbox}

\begin{ablationbox}
\textbf{Expected ablation:} [ONE primary effect with percentage]. [ONE secondary if critical]. [1-2 sentences max]
\end{ablationbox}

\begin{examplebox}
\exinput{Brief input (<15 words)}\\
\exbehavior{Concise action (<10 words)}\\
\exeffect{Direct result (<10 words)}
\end{examplebox}

\headfooter{\statusXXX}{related1 (D), related2 (D), related3 (D)}
```

---

## 8. WRITING FUNCTION DESCRIPTIONS

### 8.1 Required Structure
1. **Sentence 1:** What the heads do (core function)
2. **Sentences 2-3:** How they work (mechanism)
3. **Sentence 4-5:** Key distinction or relationship to other heads (optional)

### 8.2 Forbidden Patterns
Never write:
- "These heads are particularly important for..."
- "It's important to note that these heads..."
- "These heads work by [verb]ing... They also [verb]..."
- "Acting as... these heads..."
- "Essential for... they..."
- Explaining the same concept twice
- "Serves to", "Functions to", "In order to"

### 8.3 Required Patterns
Always write:
- Subject-Verb-Object, period
- Combine related functions in one sentence
- Remove "particularly", "especially", "notably" (usually redundant)

### 8.4 Example (Good)
```latex
Detect delimiter tokens (punctuation, brackets, whitespace) that mark 
structural boundaries. Process whitespace as semantic in languages like 
Python and YAML. Distinguish meaningful spacing from formatting.
```

### 8.5 Example (Bad - Too Verbose)
```latex
Detect and process delimiter tokens that mark boundaries between 
structural elements. These heads recognize punctuation marks, brackets, 
delimiters, and special characters that indicate separation or grouping. 
They also process whitespace characters as structural elements rather 
than mere separators. Particularly important for languages where 
whitespace is syntactically significant, these heads distinguish between 
semantically meaningful whitespace and irrelevant spacing.
```

---

## 9. WRITING ATTENTION PATTERNS

### 9.1 Rules
- **Maximum 4 items** in `\attstrong`
- **Maximum 3 items** in `\attweak`
- **Maximum 3 items** in `\attreacts`
- Group similar items: "punctuation and brackets" not "commas, periods, semicolons, brackets"

### 9.2 Example
```latex
\begin{attentionbox}
\attstrong{Punctuation, brackets, whitespace patterns, indentation}\\
\attweak{Alphanumeric content, regular words}\\
\attreacts{Structural punctuation, formatting characters, indentation changes}
\end{attentionbox}
```

---

## 10. WRITING ABLATION DESCRIPTIONS

### 10.1 Rules
- **Always include specific percentages** when possible
- **1-2 sentences maximum**
- **One primary effect**, one secondary effect if critical
- If compensation exists, mention in 3 words max

### 10.2 Format
```
[Impact statement with percentage]. [Secondary effect or clarification]. [Optional: brief compensation note]
```

### 10.3 Examples (Good)
```latex
\textbf{Expected ablation:} Significant structure parsing impairment. 
30--50\% degradation on structured data, code blocks. Boundary detection errors.
```

```latex
\textbf{Expected ablation:} Reduced instruction-following capability. 
Model generates relevant content but fails to follow specific directives. 
25--35\% degradation on instruction-following tasks.
```

### 10.4 Example (Bad - Too Vague)
```latex
\textbf{Expected ablation:} Moderate reduction in boundary awareness and 
degraded segmentation. Model may blur distinctions between sections, miss 
paragraph boundaries, or fail to recognize document structure. Reduced 
performance on multi-section documents.
```

---

## 11. WRITING EXAMPLES

### 11.1 Length Targets
- **Input:** <15 words
- **Behavior:** <10 words
- **Effect:** <10 words

### 11.2 Format
```latex
\begin{examplebox}
\exinput{Brief, realistic input}\\
\exbehavior{Clear mechanism}\\
\exeffect{Observable result}
\end{examplebox}
```

### 11.3 Use "vs." for Contrast
```latex
\exeffect{Summary format vs. continuation}
\exeffect{``Paris'' vs. hallucination}
\exeffect{Calculation vs. literary devices}
```

---

## 12. STACK OVERVIEW REQUIREMENTS

### 12.1 Maximum Length
- **2 sentences maximum**
- Sentence 1: What the stack does
- Sentence 2: Key components or mechanism (if needed)

### 12.2 Forbidden
- Lists of all heads in the stack
- Detailed mechanisms (save for individual entries)
- Importance statements (implied by inclusion)

### 12.3 Example (Good)
```latex
\textbf{Stack overview:} Implement content filtering, policy enforcement, 
and refusal mechanisms. Early layers detect harmful content; final layers 
enforce refusal and redirect to safe responses.
```

---

## 13. DEPTH RANGES

### 13.1 Consistency Requirements
**Depth Boundaries (MUST be consistent):**
- Early (E): 0.00--0.25
- Middle (M): 0.25--0.70  
- Late (L): 0.70--0.88
- Final (F): 0.88--1.00

### 13.2 Verification Rules
- Every head's depthinfo range MUST fall within its category
- Overlaps between categories should be minimal (<0.05)
- Use realistic precision (0.05 increments typical)

### 13.3 Cross-Reference Format
- Always include depth: "induction (M)"
- Maximum 3 related heads

---

## 14. FORBIDDEN PHRASES

### 14.1 Delete on Sight
Never use these phrases:
- "It is important to note that"
- "These heads work by"
- "Particularly important for"
- "Acts as a" / "Serves as"
- "Serves to" / "Functions to"
- "In order to" (use "To")
- "Is able to" (use "Can")
- "Essential for"
- "Critical for"
- "Important for understanding"

### 14.2 Replacement Table
| Verbose | Concise |
|---------|---------|
| These heads work by detecting | Detect |
| Particularly important for | [delete or "Essential for"] |
| Acts as a mechanism to | [delete] |
| In order to facilitate | To enable |
| Has the ability to | Can |
| Makes it possible to | Enables |
| Is responsible for | Handles |
| Functions to provide | Provides |

---

## 15. SENTENCE PATTERNS

### 15.1 Preferred Opening Verbs (Function Descriptions)
Use strong, direct verbs:
- Detect, Identify, Process, Manage
- Enforce, Maintain, Generate, Perform
- Determine, Track, Route, Filter
- Modulate, Adjust, Structure, Implement

### 15.2 Combining Sentences
When you have two mechanisms:
- ✓ Merge: "Detect boundaries and maintain organization"
- ✗ Separate: "Detect boundaries. Maintain organization."

When listing examples:
- ✓ Inline: "patterns like `ing', `tion', or punctuation clusters"
- ✗ Separate: "patterns. For example: `ing', `tion'. Also punctuation clusters."

---

## 16. LaTeX FORMATTING

### 16.1 Consistency Requirements
- All depth ranges use en-dash: `--`
- All quotes use LaTeX style: `` ``text'' ``
- All cross-refs use: `§\ref{}`
- All box environments must close with `}` not `>`

### 16.2 Special Characters
- Arrows in examples: `$\rightarrow$`
- Non-breaking spaces before citations: `~\cite{}`

### 16.3 Common Errors to Avoid
- ✗ `\end{ablationbox>` 
- ✓ `\end{ablationbox}`
- ✗ `\end{examplebox>`
- ✓ `\end{examplebox}`

---

## 17. QUALITY METRICS

### 17.1 Length Targets (Per Head Entry)
- Function description: 3-5 sentences (50-100 words)
- Ablation: 1-2 sentences (15-30 words)  
- Stack overview: 2 sentences (20-40 words)
- Attention patterns: ≤4 items per category
- Examples: Input <15w, Behavior <10w, Effect <10w

### 17.2 Document Targets
- Total document: 30-35 pages (not 45+)
- Each stack file: 6-11K

---

## 18. SELF-AUDIT CHECKLIST

Before finalizing ANY head entry, verify:

- [ ] Function description is ≤5 sentences
- [ ] No sentence repeats previous information
- [ ] No redundant adjectives ("particularly", "especially")
- [ ] Ablation description is ≤2 sentences
- [ ] Ablation includes specific percentage when possible
- [ ] Attention patterns have ≤4 items per category
- [ ] Example input is <15 words
- [ ] Example behavior is <10 words
- [ ] Example effect is <10 words
- [ ] No forbidden phrases present
- [ ] All LaTeX boxes close with `}` not `>`

---

## 19. WRITING WORKFLOW

### 19.1 For New Head Entries

1. **Draft function description (3-5 sentences):**
   - Sentence 1: Core function (what)
   - Sentences 2-3: Mechanism (how)
   - Sentence 4-5: Context/distinction (optional)

2. **List attention patterns (≤4 per category):**
   - Group similar items
   - Keep concise

3. **Write ablation (1-2 sentences with %):**
   - Primary effect with percentage
   - Secondary effect if critical

4. **Create example (brief):**
   - Input: <15 words
   - Behavior: <10 words  
   - Effect: <10 words

5. **Run self-audit checklist**

6. **Read aloud - if it sounds verbose, it is**

### 19.2 Editing Existing Entries

1. Count sentences in function description (should be ≤5)
2. Remove any forbidden phrases
3. Merge redundant sentences
4. Add percentages to ablations if missing
5. Trim attention patterns to ≤4 items
6. Shorten examples if needed
7. Run self-audit checklist

---

## 20. EXAMPLES OF COMPLETE ENTRIES

### 20.1 Excellent Entry (Concise)
```latex
\subsubsection{(M) Induction Heads}
\label{head:induction}

\noindent\depthinfo{0.30--0.65} | \litnames{induction head, pattern head, copy head, ICL head}

\begin{functiondesc}
Detect [A][B]...[A] patterns and predict [B] follows the second [A]. 
Attend to tokens after previous instances of current token. Work with 
previous-token heads to enable pattern completion, name recall, and 
few-shot learning. Fundamental to in-context learning.
\end{functiondesc}

\begin{attentionbox}
\attstrong{Tokens following previous occurrences}\\
\attweak{Immediate neighbors, first occurrence}\\
\attreacts{Token repetition, [A][B]...[A] patterns}
\end{attentionbox}

\begin{ablationbox}
\textbf{Expected ablation:} Significant degradation in in-context learning 
and pattern completion. 30--50\% accuracy loss on few-shot tasks. 
Partial compensation through other heads.
\end{ablationbox}

\begin{examplebox}
\exinput{``Mary and John went to the store, Mary bought...''}\\
\exbehavior{Second ``Mary'' attends to tokens after first ``Mary''}\\
\exeffect{Increased probability of appropriate continuation}
\end{examplebox}

\headfooter{\statuswell}{previous-token (E), duplicate-token (M), name-mover (L)}
```

### 20.2 What Makes This Excellent
- ✓ Function: 4 sentences, clear and direct
- ✓ Attention: 2-3 items per category
- ✓ Ablation: 2 sentences with specific 30-50% figure
- ✓ Example: All fields concise
- ✓ No forbidden phrases
- ✓ Active voice throughout
- ✓ Every word earns its place

---

## FINAL REMINDER

**"When in doubt, cut it out."**

If you're unsure whether information is necessary, it probably isn't. Academic writing should be precise, not verbose. Every additional word must add value. Clarity comes from simplicity, not elaboration.

**END OF STYLE GUIDE**
