# 🖥️ GPU: size the job first, and the hardware sizes itself

You commented **GPU**. Here are the three prompts from the video, ready to copy into your AI (Claude, ChatGPT, or any assistant), plus the memory cheat sheet.

Fill in the parts in **[brackets]** before you send each prompt.

---

## Prompt 1: let the job pick the model

```
I want to run an AI model locally for this job: [describe the job, e.g. "summarise
support tickets and draft replies"].

Here are 5 real examples of the task, with what a good answer looks like:
[paste 5 real examples]

1. Suggest three open-weight models of different sizes (small, medium, large)
   that are good candidates for this job.
2. Write me a simple test plan to run all 5 examples through each model,
   3 times each, so I can check they get it right consistently.
3. Give me a scoring sheet (pass / fail per example, per run).
4. Tell me how to decide: I want the SMALLEST model that passes every example,
   every time.
```

---

## Prompt 2: work out the memory, at both sizes

```
My chosen model is [model name] with [N] billion parameters.

Calculate how much video memory (VRAM) it needs at:
  a) 16-bit (about 2 bytes per parameter)
  b) 4-bit quantized

For each size, add room for:
  - a full context window of [N] tokens (my longest real conversations)
  - [N] users at the same time

Show your working step by step, list your assumptions, and give me a final
"minimum VRAM" number for each size. Then tell me which common GPU memory
sizes (8, 12, 16, 24, 48 GB …) would fit each one, with some headroom.
```

---

## Prompt 3: rent before you buy

```
Design a one-week test on a rented cloud GPU before I buy hardware.

The model: [model name, 16-bit or 4-bit]
The GPU class I'm considering: [e.g. "24 GB card"]
My real workload: [describe it: how many tasks per day, typical length]

Give me:
1. A day-by-day plan for the week (setup, normal load, peak load, review).
2. What to track for every task: speed (tokens/second, time per task) and
   cost per task.
3. A simple spreadsheet layout to log it.
4. The questions to answer at the end of the week to decide: buy this GPU,
   buy a bigger or smaller one, or keep renting.
```

---

## Memory cheat sheet

| | Rule of thumb | A 7-billion-parameter model |
|---|---|---|
| **16-bit** | about 2 bytes per parameter | about **14 GB** for the weights |
| **4-bit** | about half a byte per parameter, plus some overhead | about **4 to 5 GB** for the weights |
| **Then add** | room for long conversations (context) and more than one user | depends on your use: that's what Prompt 2 works out |

These are starting estimates for the model's weights only. Always test on your real workload; that's what Prompt 3 is for.

---

*Found this useful? Follow for more short, fact-checked AI dev tips.*
