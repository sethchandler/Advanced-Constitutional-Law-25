# PASS 1: COMPREHENSIVE DETECTION AND ANNOTATION

You are an expert editor performing diagnostic analysis. Your task is to identify and annotate ALL issues in the provided text WITHOUT modifying it.

## ANNOTATION FORMAT

Use this exact format for all annotations:
[CATEGORY-TYPE: "exact quoted phrase"]

Place annotations immediately before or after the problematic phrase in the text.

## CATEGORIES TO DETECT

### 1. SLOP CATEGORIES (10 types)

**SLOP-HEDGING**: Unnecessary qualifying phrases that weaken claims
Examples to flag:
- "it should be noted that"
- "it is important to understand that"
- "one must consider that"
- "it is worth noting that"
- "it could be argued that"
- "some would say that"
- "arguably"
- "in some sense"

**SLOP-TRANSITION**: Excessive or mechanical transition words, especially chains
Examples to flag:
- "Moreover," "Furthermore," "Additionally," "In addition," appearing in consecutive sentences
- Transitions used within a single unified argument where they add no logical connection
- "That being said," "Having said that," when no real contrast exists

**SLOP-PADDING**: Inflated language that adds no meaning
Examples to flag:
- "delve deep into"
- "the very fabric of"
- "multifaceted implications"
- "complex and nuanced"
- "deeply intertwined"
- "intricately connected"
- "serves to effectively"
- "works to essentially"
- "fundamentally important"
- "increasingly relevant"

**SLOP-OPENING**: Generic, empty opening statements
Examples to flag:
- "In today's world,"
- "In today's rapidly evolving world,"
- "has never been more important/relevant"
- "Throughout history,"
- "Since the dawn of time,"
- "In modern society,"
- "In recent years," (when not followed by specific years/data)

**SLOP-LISTICLE**: Mechanical parallel structure with formulaic transitions
Flag when you see:
- "First," ... "Second," ... "Third," with minimal substantive content
- "On one hand," ... "On the other hand," ... "Additionally,"
- Numbered points that are just restatements rather than distinct ideas

**SLOP-CIRCULAR**: Circular definitions or tautologies
Examples to flag:
- "X is important because it is significant"
- "This demonstrates Y because it shows Y"
- Definitions that just restate the term in different words

**SLOP-EXAMPLE**: Weak, abstract, or circular examples
Flag when:
- Example is just a category, not an illustration ("For example, taxation" not "For example, in Maryland v. Wynne...")
- Example doesn't actually illustrate the principle claimed
- "Such as X, Y, and Z" where X, Y, Z are abstract categories

**SLOP-CONTRAST**: Meaningless contrast structures
Flag when:
- "On one hand... on the other hand..." presents no real tension or alternative
- False balance where one side is strawmanned or trivial
- Contrast structure used purely for rhythm with no substantive disagreement

**SLOP-HEADER**: Obvious, generic, or uninformative headers
Examples to flag:
- "Introduction"
- "Conclusion"
- "Background"
- "What is [X]?"
- "Why [X] Matters"
- Any header that just restates the document title

**SLOP-PASSIVE**: Passive voice that creates false complexity or obscures agency
Flag when:
- Active voice would be clearer and agency matters
- Passive creates unnecessary wordiness
- Example: "Discrimination is practiced against" vs "discriminates against"
Note: Do NOT flag all passive voice - only flag when it's problematic

**SLOP-ENTHUSIASM**: Vapid motivational language or forced excitement
Examples to flag:
- "exciting opportunities"
- "truly remarkable"
- "absolutely essential"
- "game-changing"
- "revolutionary impact"
- "transformative potential"
(Flag only when these are empty intensifiers, not when genuinely warranted)

### 2. GRAMMAR AND SYNTAX

**GRAMMAR-SUBJECT-VERB**: Subject-verb agreement errors
Example: "The list of items are" (should be "is")

**GRAMMAR-PRONOUN**: Pronoun-antecedent errors
Example: "Each student must submit their" (number disagreement)

**GRAMMAR-FRAGMENT**: Sentence fragments (incomplete sentences)

**GRAMMAR-RUNON**: Run-on sentences or comma splices

**GRAMMAR-SPELLING**: Spelling errors

**GRAMMAR-PUNCTUATION**: Punctuation mistakes

**GRAMMAR-OTHER**: Other grammatical issues

### 3. STRUCTURAL PROBLEMS

**STRUCTURAL-REPETITION**: Same concept stated multiple times
Flag when: A point made in one paragraph/section is restated later without adding new information

**STRUCTURAL-EXAMPLE-WEAK**: Abstract or inadequate examples (overlap with SLOP-EXAMPLE but use when it's more about structural inadequacy than slop)

**STRUCTURAL-FOCUS**: Paragraph lacks clear focus or topic sentence

**STRUCTURAL-ORDERING**: Sentences or ideas in illogical order

**STRUCTURAL-TRANSITION**: Missing necessary transitions (different from SLOP-TRANSITION which is about excessive transitions)

### 4. VOICE INCONSISTENCIES

**VOICE-TONE-SHIFT**: Unjustified shift from formal to casual or vice versa

**VOICE-REGISTER**: Register mismatch (e.g., colloquial language in formal context, or overly formal in casual context)

**VOICE-STYLE-CONFLICT**: Competing stylistic approaches (e.g., mixing academic prose with journalistic style without clear reason)

## OUTPUT REQUIREMENTS

1. Return the COMPLETE original text with annotations inserted
2. Place each annotation immediately before or after the problematic phrase
3. Use the EXACT format: [CATEGORY-TYPE: "quoted phrase"]
4. Quote the EXACT problematic phrase in the annotation
5. Do NOT modify the text itself - only add annotations
6. Be thorough - flag EVERY instance of the issues above

## EXAMPLE OUTPUT

Here's how your output should look:

[SLOP-OPENING: "In today's rapidly evolving world,"] [SLOP-HEDGING: "it should be noted that"] the dormant commerce clause [SLOP-ENTHUSIASM: "has never been more relevant"]. [SLOP-TRANSITION: "Moreover,"] [SLOP-HEDGING: "one must consider that"] this constitutional doctrine [SLOP-PADDING: "serves to effectively"] prevent states from engaging in protectionist measures. [SLOP-TRANSITION: "Furthermore,"] [SLOP-HEDGING: "it should be understood that"] [SLOP-PADDING: "the very fabric of"] American federalism depends upon this principle.

## NOW ANALYZE THIS TEXT

Carefully read the following text and annotate ALL issues according to the categories above. Return the complete text with inline annotations.
