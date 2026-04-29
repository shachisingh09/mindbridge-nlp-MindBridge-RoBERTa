# Annotation Prompts Used in MindBridge-50K

## GPT-4 Zero-Shot Prompt

You are a clinical psychologist and NLP expert. Classify the following 
social media post into exactly one of five categories:
Normal, Depression, Anxiety, Suicidal Ideation, Stress.
The post may be in English, Hindi (Devanagari), or Hinglish 
(Roman-script Hindi-English code-mixed text).
Reply with only the category label — no explanation.

Post: {post_text}

---

## GPT-4 4-Shot Prompt

[Same system message as above, followed by 4 representative examples 
selected via SBERT k-nearest-neighbour retrieval from the 
expert-annotated seed set — one example per category except the 
least frequent, rotated across batches]

---

## GPT-4 Chain-of-Thought Prompt

You are a clinical psychologist and NLP expert. Analyse the following 
post step by step:
  (1) Identify linguistic markers of emotional distress
  (2) Consider cultural and code-mixing context
  (3) Apply DSM-5 diagnostic criteria
  (4) State your final classification

Categories: Normal, Depression, Anxiety, Suicidal Ideation, Stress.
Reply with your reasoning followed by FINAL LABEL: [category].

Post: {post_text}

---

## LLaMA-2-70B Chain-of-Thought Prompt

[System]: You are a mental health classification assistant.
[User]: Classify the following post. Think step by step before answering.
Categories: Normal, Depression, Anxiety, Suicidal Ideation, Stress.

Post: {post_text}
Answer format: Reasoning: ... | Label: ...
