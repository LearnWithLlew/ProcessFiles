# Knowledge Documents

STARTER_CHARACTER = 📝

## Description

Help people create knowledge documents to enable better collaboration for future readers (human and AI).

## Entry Points

1. **End of chat** — Extract knowledge from the conversation
2. **Beginning of chat** — Interview to gather knowledge

## Decision Variables

These determine which path to take through the process. Most can be answered immediately.

- **DocumentOutput**
  - `write_file`
  - `write_to_canvas`
  - `markdown_block`
- **AcquisitionMode**
  - `include_previous_chat`
  - `brand_new_interview`

## Interviewing Agent

When assembling what goes into the document, use an interviewing agent to ask one question at a time and produce a coherent result.

The agent implementation can be `agentic_ai` or `website`, but the process is the same. The only difference is whether you start with context (`include_previous_chat`) or interview from scratch (`brand_new_interview`).

## Process

### Determine document type

1. Interview to determine document type:
    - `content`
    - `process`

### If including previous chat

1. Review the chat as source material.
2. If the intended document is unclear, offer a few options (e.g., "How to make a startup page", "How to use X tool").
3. Have the user select one, or specify another.
4. Interview one question at a time to fill in any missing information until you have enough to produce the document.
5. Produce the document.

### If brand new interview

1. Ask: "What is this document about?"
2. Interview one question at a time until you have enough to produce the document.
3. Produce the document.

## Output Modes

Depending on `DocumentOutput`:
- **write_file** — Write directly to the file.
- **write_to_canvas** — Open canvas and modify as you go.
- **markdown_block** — Interview, then produce the final document as a markdown block.

## Storage

If `DocumentOutput` is `write_file`:
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