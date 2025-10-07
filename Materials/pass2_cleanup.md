# PASS 2: MECHANICAL CLEANUP AND GRAMMAR CORRECTION

You are performing mechanical cleanup of annotated text. Execute ONLY deterministic, non-controversial fixes.

## YOUR TASK

Remove all annotation markers and apply the fixes they indicate. This pass handles:

1. **Remove flagged hedging phrases** - Pure deletion
   - Delete "it should be noted that," "it is important to understand," etc.
   - Convert "It is worth noting that X" → "X"
   - Adjust capitalization and punctuation as needed

2. **Eliminate semantic padding** - Simple substitution
   - "delve deep into the topic" → "examine the topic"
   - "the very fabric of American democracy" → "American democracy"
   - "multifaceted implications" → "implications"
   - "serves to effectively prevent" → "prevents"

3. **Cut redundant transitions** - Selective deletion
   - Remove excessive "Moreover," "Furthermore," "Additionally"
   - Keep only transitions that signal genuine logical shifts
   - Within unified paragraphs, remove most transitions

4. **Fix all grammar and spelling** - Mechanical correction
   - Subject-verb agreement
   - Pronoun-antecedent fixes
   - Spelling corrections
   - Punctuation normalization

5. **Standardize formatting**
   - Consistent capitalization
   - Uniform spacing

## CRITICAL CONSTRAINTS

- **MINIMAL sentence reconstruction**: Delete flagged phrases and adjust punctuation only as needed
- Do NOT rewrite entire sentences unless grammatically necessary
- If flagged phrase is at sentence start: delete it and capitalize next word
- If mid-sentence: delete it and adjust punctuation if needed
- Preserve the core sentence structure

## EXAMPLE TRANSFORMATION

**Before (with annotations):**
[SLOP-HEDGING: "It is important to note that,"] [SLOP-TRANSITION: "furthermore,"] the Court has established that discrimination against interstate commerce is prohibited.

**After:**
The Court has established that discrimination against interstate commerce is prohibited.

## OUTPUT REQUIREMENTS

Return ONLY the cleaned text. All annotations must be removed. Text should be shorter and cleaner but structurally similar to the original.
