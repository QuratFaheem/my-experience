---
name: "section-writer"
description: "Write clear, evidence-supported research paper sections with proper citations and logical flow. Use when the user explicitly asks to 'write', 'draft', or 'generate' a section of a research paper, providing key points and a thesis."
parameters:
  - name: "section_title"
    type: "string"
    description: "The title of the research paper section to be written (e.g., 'Literature Review', 'Methodology', 'Introduction')."
    required: true
  - name: "key_points"
    type: "array"
    description: "A list of distinct key points or sub-topics to be covered within the section. Each point should be concise and informative."
    required: true
    items:
      type: "string"
  - name: "thesis_statement"
    type: "string"
    description: "The main argument or thesis that the section should support or elaborate upon. This provides the central focus for the generated content."
    required: true
---

# Section Writer Skill

## Description
This skill helps you draft sections of a research paper based on provided key points and a thesis statement. It aims to produce clear, evidence-supported content with proper citations and logical flow.

## Example
**Input**: "Write the Literature Review section on AI in K-12 education. Key points: (1) Current state of AI in K-12, (2) Teacher workload research, (3) Student outcome studies. Thesis: AI tools can measurably improve K-12 classroom efficiency."

**Output**:
- **Opening**: "The integration of artificial intelligence into K-12 classrooms represents a transformative shift in educational paradigms (Smith & Jones, 2023). This literature review synthesizes current research on AI's presence in K-12, its impact on teacher workload, and its documented effects on student outcomes, ultimately arguing that AI tools can measurably enhance classroom efficiency."
- **Develop each point**:
    1.  **Current state of AI in K-12**: "AI is increasingly adopted in K-12 settings for personalized learning, automated grading, and adaptive assessments (Chen et al., 2022). Tools range from intelligent tutoring systems to AI-powered analytics platforms (Lee & Kim, 2021). However, implementation often faces challenges such as limited infrastructure and teacher training (Garcia & Johnson, 2024)."
    2.  **Teacher workload research**: "Studies indicate that AI can significantly reduce administrative burdens on teachers, freeing up time for instructional planning and direct student interaction (Davis, 2023). For example, AI-driven tools for feedback generation and lesson planning have been shown to save teachers several hours per week (Brown & Miller, 2022). Conversely, some research highlights concerns about the initial time investment required for learning new AI platforms (White, 2020)."
    3.  **Student outcome studies**: "Research on AI's impact on student outcomes is generally positive, demonstrating improvements in engagement, comprehension, and academic performance, particularly in STEM subjects (Green et al., 2021). Adaptive AI systems can identify learning gaps and provide targeted interventions, leading to enhanced student mastery (Nguyen, 2023). However, equitable access to AI resources remains a critical concern, with disparities potentially exacerbating existing achievement gaps (Martinez & Rodriguez, 2024)."
- **Closing**: "The evidence suggests AI tools can meaningfully reduce teacher workload while improving student engagement and academic outcomes. However, implementation challenges, equity concerns, and the need for robust teacher training require careful attention as districts consider broader AI adoption to truly leverage its potential for K-12 classroom efficiency."