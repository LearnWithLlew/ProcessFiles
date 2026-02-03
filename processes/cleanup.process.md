# Cleanup

This process takes text from speech-to-text transcription and cleans it up.

## Process

1. Review the file to be cleaned
2. Check names against the people's file
3. Review examples from previous files with similar names
4. Apply minor edits:
   - Format for readability
   - Restructure sentences to be more natural
   - Reorder if pieces get brought up in the wrong section
   - Remove corrective statements
      - For example "Then we ate 4 cookies, no wait 5" would become "Then we ate 5 cookies"
   - Put each sentence on its own line (for easier markdown wrapping and diffs)
   - Correct spelling
   - Clean up sentences that don't make sense
   - Remove filler words (especially "like" when used as a verbal filler)
   - Add blank lines before section headers
   - Convert written numbers to digits for scannability (e.g., "ten" → "10", "two or three" → "2 or 3")
   - Put dialogue in quotes
   - Use blockquotes (>) for longer or significant quoted sections, still including quotation marks
   - Keep changes minimal
5. Suggest a handful of descriptive title suffix to add to the filename based on the content's main theme