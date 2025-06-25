# Markdown Creation Instruction

## Purpose:
To white-label documentation content by replacing brand-specific terms with custom branding across all `.md` files in the repository or documentation directory, while ensuring compatibility with MDX rendering in Docusaurus.

## Instructions:
When processing markdown files for documentation:

### 1. Branding Replacement
Replace all occurrences (case-sensitive) as follows:
• Hystax → Invincible Ocean  
• Optscale → CloudTuner

### 2. Preserve Context and Formatting
• Maintain Markdown styling — e.g., `**Hystax**` becomes `**Invincible Ocean**`  
• Retain hyperlinks and code blocks unless they explicitly contain brand-specific URLs (see step 4)

### 3. Do NOT Change:
• Variable names, code identifiers, CLI arguments (e.g., `hystax_config.yaml`, `--optscale-mode`)  
• Anything inside fenced code blocks or inline code backticks unless it's plain text branding  
• MDX/JSX component tags or HTML structure

### 4. Link Handling
• Leave all image or external URLs **unchanged**, especially if they start with `http://hystax`  
• If a **hyperlink label** includes "Optscale", update the label only, not the URL  
  ⮕ Example: `[Explore Optscale Docs](https://docs.hystax.com/optscale/)`  
  → `[Explore CloudTuner Docs](https://docs.hystax.com/optscale/)`

### 5. MDX Compatibility Fix
To prevent MDX parsing errors (e.g., "Unexpected character `\` (U+005C) in name"):
• Any inline usage of angle brackets such as `<bucket_name>` or `<AWS account ID>` must be:
  - Replaced with backtick-wrapped code like `` `<bucket_name>` ``
• Avoid placing raw angle brackets inside Markdown unless in fenced code blocks or JSX
• Do not escape these using backslashes (`\`) — instead, wrap them as inline code

### 6. Output Format
• Final output must be in **valid Markdown format**  
• No additional commentary or metadata — pure `.md`-compatible content only  
• Ensure all transformed files can be compiled by Docusaurus without MDX errors

### 7. Add Title Frontmatter
• Each markdown file **must begin** with a valid frontmatter block specifying a `title` based on the main heading or contextual topic of the document.  
• If the file contains a top-level heading (e.g., `# AWS Setup`), extract and set that as the title:
  ```markdown
  ---
  title: AWS Setup
  ---
  ```