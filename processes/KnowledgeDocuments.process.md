# Knowledge Documents

STARTER_CHARACTER = 📝

## Description

Help people create knowledge documents for future readers (human and AI).

## Entry Points

1. **End of chat** — Extract knowledge from the conversation
2. **Beginning of chat** — Interview to gather knowledge

## Process

### If at the end of a chat

1. Review the chat as source material.
2. If the intended document is unclear, offer a few options (e.g., "How to make a startup page", "How to use X tool").
3. Have the user select one, or specify another.
4. Interview one question at a time to fill in any missing information until you have enough to produce the document.
5. Produce the document.

### If at the beginning of a chat

1. Ask: "What is this document about?"
2. Interview one question at a time until you have enough to produce the document.
3. Produce the document.

## Output Modes

Depending on context:
- **File access** — Write directly to the file.
- **Canvas access** — Open canvas and modify as you go.
- **Neither** — Interview, then produce the final document at the end.

## Storage

1. Store in `InternalDocuments/` from the project root.
2. Create the folder if it doesn't exist.
3. Read subfolders to determine best placement.
4. Check existing docs — reference them for context offloading (e.g., `see scripts.md for details`).

## Output Format

1. Keep it small.
2. Start with a bullet list of key pieces:
   - File locations
   - Prime directives
   - Overall goals
   - Process steps
3. Add details only if necessary, in subheadings after the bullet point.
4. If the bullet list plus project context is enough, stop there.

## Naming

- Process document: `myprocess.process.md`
- Context document: `mycontext.md`

Suggest a few short names (2-3 words max), then recommend the best one.

## Quality Check

Flag issues even if uncomfortable:
- **Ambiguity** — steps that could be interpreted multiple ways
- **Missing context** — unstated assumptions
- **Contradictions** — conflicting steps
- **Gaps** — missing steps to achieve the goal