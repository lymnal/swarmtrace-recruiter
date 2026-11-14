# SwarmTrace

**Trace a correction from the first message to the artifact someone actually changed.**

[Open the interactive demo →](https://lymnal.github.io/swarmtrace-recruiter/)

I built the investigator workbench for a three-person team at the [AI Swarm Dynamics Hackathon](https://swarmchasing.com/logistics/). The workbench brings chat, tool output, and resulting artifacts into one timeline so a reviewer can see which parts of an agent's account are supported by evidence.

## Walk through a fictional case

An agent repeats the wrong pickup time for a book donation. A second agent checks the calendar and posts a correction. One agent acknowledges the correction, and another artifact remains stale. Open the evidence in order and decide what you can actually confirm.

<details>
<summary><strong>09:02 · The wrong time spreads</strong></summary>

**Synthetic chat · E01**

> Schedule agent: Book pickup is at 4:00 p.m.
>
> Board agent: I’ll put 4:00 p.m. on the volunteer board.

This records a claim and an intent to update the board. To establish the board’s state, check the board itself.

</details>

<details>
<summary><strong>09:05 · A tool check turns up the correct time</strong></summary>

**Synthetic calendar response · E02**

```text
Event: Book donation pickup
Confirmed time: 3:00 p.m.
```

**Synthetic chat · E03**

> Calendar agent: The calendar says 3:00 p.m. Please update the volunteer board and the print handout.
>
> Board agent: Got it. I’ll update both.

The calendar response supports the correction. The reply establishes acknowledgment and a plan.

</details>

<details>
<summary><strong>09:09 · Only one artifact confirms the correction</strong></summary>

**Synthetic artifact snapshots · E04 and E05**

| Artifact | Before | At 09:09 | Review status |
| --- | --- | --- | --- |
| Volunteer board | 4:00 p.m. | 3:00 p.m. | Correction observed |
| Print handout | 4:00 p.m. | 4:00 p.m. | Still stale at last check |

The snapshots support a partial correction. They leave open whether anyone saw either version of the handout.

</details>

All records, messages, timestamps, and artifacts in this repository were created for this demonstration. The example demonstrates my workbench design. The research project used the [AI Village dataset from AI Digest](https://huggingface.co/datasets/aidigestorg/ai-village).

[Ethan Sam](https://ethansam.io/) · [LinkedIn](https://www.linkedin.com/in/ethansam)
