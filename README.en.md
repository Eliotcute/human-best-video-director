# Human Best Video Director

[简体中文](README.md) | English | [繁體中文](README.zh-TW.md)

[![Version](https://img.shields.io/badge/version-1.1.0-2563eb)](#)
[![skills.sh](https://skills.sh/b/Eliotcute/human-best-video-director)](https://skills.sh/Eliotcute/human-best-video-director)
[![License](https://img.shields.io/badge/license-CC_BY--NC_4.0-16a34a)](LICENSE)
[![X](https://img.shields.io/badge/X-%40shizhieliot-000000?logo=x&logoColor=white)](https://x.com/shizhieliot)

Created by [Eliot](https://x.com/shizhieliot).

A Chinese-first set of director Skills for content creators, social media operators, personal brands, founders, and small teams.

It covers the full path from “who should this account serve?” to “how should this post be produced?” and “what should change after publication?” Use it for account positioning, personal IP, topic decisions, titles and openings, spoken scripts, production plans, and post-publication reviews.

This is not a writing template that turns every topic into instant copy. When a request is vague, it first checks the audience, purpose, real source material, and production constraints. If a missing fact would change the result, it asks no more than three useful questions and then continues the task.

Current version: `v1.1.0` · 9 Skills · [CC BY-NC 4.0](LICENSE)

## Who is it for?

- **Content creators and bloggers** who want to turn loose ideas into publishable topics, openings, scripts, and production plans.
- **Social media operators** who need to position a new account, plan the first posts, and decide what to change from real performance data.
- **Personal brands and knowledge creators** who want a sustainable content direction grounded in real experience, ability, and point of view.
- **Founders and brand leads** who need to turn products, business decisions, and founder stories into content people can understand and trust.
- **Faceless or low-budget creators** who need workable plans built around screen recordings, real footage, documents, voice-over, and limited crew.
- **People training as directors** who want to improve audience judgment, topic choice, visual thinking, pacing, and use of source material through real tasks.

If you only need a sentence polished, a general writing tool is enough. This project is for work that requires a sound direction before the content is made.

## Project architecture

The project contains one main entry point and eight specialist Skills. The main Skill understands the request, selects the Skills required for the task, keeps confirmed context, and combines the results into one final delivery. Each specialist handles one clearly defined problem.

```mermaid
%%{init: {"theme":"base","themeVariables":{"background":"#ffffff","primaryColor":"#eef5ff","primaryTextColor":"#172033","primaryBorderColor":"#7aa7e8","lineColor":"#8290a3","secondaryColor":"#f7f9fc","tertiaryColor":"#ffffff","fontFamily":"-apple-system, BlinkMacSystemFont, Segoe UI, sans-serif"},"flowchart":{"curve":"basis"}}}%%
flowchart TB
    U(["User content request"]) --> M["human-best-video-director<br/>Main entry<br/>Understand · Select · Integrate · Validate"]

    M -- "Missing context" --> I["hbvd-intake<br/>Clarify the request<br/>Up to 3 key questions"]
    I -- "Return key facts" --> M

    M -- "Account and identity" --> A["hbvd-account<br/>Account positioning and launch<br/>Audience · Follow reason · Content pillars"]
    M --> P["hbvd-ip<br/>Personal IP and founder story<br/>Real credentials · Trust · Character expression"]
    M -- "Content decisions" --> T["hbvd-topic<br/>Topic decision<br/>Best topic · Evidence · Validation conditions"]
    M --> H["hbvd-hook<br/>Title and opening<br/>Title · Cover · First line · First visual"]
    M -- "Production" --> S["hbvd-script<br/>Script and production<br/>Copy · Timeline · Shots · Production list"]
    M -- "Feedback and growth" --> V["hbvd-review<br/>Draft and performance review<br/>Facts · Main issue · Next change"]
    M --> C["hbvd-training<br/>Director training<br/>Real task · Before/after · Acceptance criteria"]

    A --> P
    A --> T
    P --> T
    P --> S
    T --> H
    T --> S
    H --> S
    V -. "Return the issue to its stage" .-> T
    V -.-> H
    V -.-> S
    C -. "Train a weak capability" .-> A
    C -.-> T
    C -.-> H
    C -.-> S

    A --> O["Unified delivery<br/>Usable · Factual · Producible"]
    P --> O
    T --> O
    H --> O
    S --> O
    V --> O
    C --> O
    O --> Z(["Task complete"])

    classDef main fill:#eef5ff,stroke:#7aa7e8,color:#172033,stroke-width:1.5px;
    classDef plain fill:#ffffff,stroke:#aab4c3,color:#172033,stroke-width:1.2px;
    classDef branch fill:#f7f9fc,stroke:#aab4c3,color:#172033,stroke-width:1.2px;
    class U,M,O,Z main;
    class I,A,P,T,H,S,V,C branch;
```

Solid arrows show common production dependencies. Dashed arrows show review or training returning to a specific stage. Most users only need the main entry point and do not need to arrange the eight Skills themselves.

## Start with an example

You can say:

```text
Use $human-best-video-director.

I want to start a faceless Xiaohongshu account about practical AIGC workflows.
My audience is office workers and social media operators. I am good at
commercial execution and content creation. I can record my screen and add voice-over.

Help me position the account, choose the best first topic, and turn it into a 60-second script.
```

You should receive:

1. A clear answer to who the account is for and why someone would follow it.
2. One topic worth publishing first, instead of a long list of loose ideas.
3. A 60-second script you can record and shoot.
4. A list of shots that must be captured and claims that must not be invented.

If your request is only:

```text
I want to start a Xiaohongshu account. Help me get it off the ground.
```

The Skill will not invent your identity or direction. It asks up to three questions that would actually change the plan. Once you answer, it continues from there without restarting the interview or making you type “continue” at every step.

## What can it help with?

| Your situation | What it does |
|---|---|
| You want to start an account but the direction is still vague | Clarifies the three most important unknowns, then proposes one workable direction |
| You know what you are good at but not who the account is for | Defines the audience, the reason to follow, and the first assumption worth testing |
| You want a personal IP without performing a fake persona | Finds the part of your real experience and ability that is worth building around |
| You have too many topic ideas and do not know what to shoot first | Recommends one topic for the current stage and explains why |
| The title is strong but the body does not deliver | Aligns the title, cover, opening, evidence, and payoff |
| You have an idea but cannot turn it into a shootable video | Writes the spoken script, shot order, and missing-footage checklist |
| You are faceless, low-budget, or working alone | Adapts the plan to screen recordings, voice-over, real footage, hands, or source material |
| A post underperformed and you do not know why | Separates what the data proves from what is still a guess, then picks one thing to change |
| You want to improve as a director | Reworks the same real task twice so you can see whether your judgment improved |

## The nine Skills

Most people only need to remember `$human-best-video-director`. If you already know exactly what you need, call a specialist directly.

| Skill | Use it when | What you get |
|---|---|---|
| `$human-best-video-director` | You do not know where to start, or the request spans several stages | It chooses the order and returns one coherent result |
| `$hbvd-intake` | The request is still broad and you are not sure whether the information is sufficient | Up to three useful questions, followed by a handoff to the next step |
| `$hbvd-account` | You need account positioning, a launch plan, or recurring content directions | One account promise, a reason to follow, and a first test to run |
| `$hbvd-ip` | You are building a personal IP, founder presence, or character-led story | What to emphasize, why people should trust it, and how the first story should work |
| `$hbvd-topic` | Several directions seem possible, or you need to decide whether a topic is worth making | One recommended topic, the evidence it needs, and reasons to reject weaker options |
| `$hbvd-hook` | The topic and body exist, but the title, cover, or opening needs work | One title, cover line, opening sentence, and first visual |
| `$hbvd-script` | The topic is confirmed and you are ready to produce | A speakable script, timeline, shot plan, and production checklist |
| `$hbvd-review` | You have a draft, video, or performance data and want to know what failed | The most likely bottleneck, conclusions you cannot yet make, and one change for the next test |
| `$hbvd-training` | You want to train topic judgment, empathy, visual thinking, pacing, or material selection | One real exercise, a rewrite method, and a way to judge improvement |

## How it works

```mermaid
%%{init: {"theme":"base","themeVariables":{"background":"#ffffff","primaryColor":"#eef5ff","primaryTextColor":"#172033","primaryBorderColor":"#7aa7e8","lineColor":"#8290a3","secondaryColor":"#f7f9fc","tertiaryColor":"#ffffff","fontFamily":"-apple-system, BlinkMacSystemFont, Segoe UI, sans-serif"},"flowchart":{"curve":"basis"}}}%%
flowchart LR
    U(["You describe the task"]) --> G{"Enough information?"}
    G -- "No" --> Q["Ask up to 3<br/>useful questions"]
    Q --> G
    G -- "Yes" --> B["Organize this task"]
    B --> R{"What needs to be done?"}
    R --> A["Account<br/>Personal IP<br/>Topic"]
    R --> C["Title and opening<br/>Script and production"]
    R --> D["Draft review<br/>Data review"]
    R --> T["Director training"]
    A --> O["Turn the work into<br/>one usable result"]
    C --> O
    D --> O
    T --> O
    O --> V{"Does it answer the original need?"}
    V -- "Not yet" --> R
    V -- "Yes" --> Z(["Done"])

    classDef main fill:#eef5ff,stroke:#7aa7e8,color:#172033,stroke-width:1.5px;
    classDef plain fill:#ffffff,stroke:#aab4c3,color:#172033,stroke-width:1.2px;
    classDef branch fill:#f7f9fc,stroke:#aab4c3,color:#172033,stroke-width:1.2px;
    class U,B,O,Z main;
    class G,R,V plain;
    class Q,A,C,D,T branch;
```

The Skills keep the facts, materials, and constraints already provided, so later stages should not ask the same questions again.

## Common ways to use it

### Start an account from scratch

```text
Use $human-best-video-director.

I want to create a real-estate content account, but the direction is not clear yet.
I do not want to appear on camera. I can visit properties and record maps and commute data.
Ask only for information that would change the plan, then help me design the launch.
```

### Pick one topic for a new account

```text
Use $hbvd-topic.

This is a new Xiaohongshu account for office workers buying their first home.
I can produce property field tests, but I will not appear on camera.
Recommend only one topic to publish first and tell me what footage I need.
```

### Turn a confirmed topic into a script

```text
Use $hbvd-script.

The topic is: “The sales office says the metro is 800 meters away,
so I walked it at 6:30 p.m. on a Monday.”
The audience is office workers buying their first home. I have maps and real walking footage.
Write a 60-second voice-over, timeline, and shot list.
Leave unknown measurements blank instead of inventing them.
```

### Create a founder story

```text
Use $human-best-video-director.

I run a neighborhood bakery and want local families to understand why we bake everything daily.
I can appear on camera. I have early photos, footage of morning preparation, and the real process.
Find the trust this story should build, then turn it into a shootable video plan.
```

### Improve a title and opening

```text
Use $hbvd-hook.

Here is the finished body and the material I can show: ...
Give me one title, one cover line, the first sentence, and the first visual.
If the body cannot support the promise, tell me directly.
```

### Review an underperforming post

```text
Use $hbvd-review.

The purpose of this post was to earn follows.
Here are the averages from the previous 10 posts, the 72-hour results for this post,
and the title, cover, and full content: ...

Tell me what the evidence supports, what remains unknown, and the one thing to change next.
```

## What the answer may look like

The following excerpts are shortened examples. Real answers are rebuilt from your business, materials, and production limits.

### When important information is missing

You say:

```text
I want to build a personal IP in real estate. Help me plan it.
```

Instead of inventing a persona, it should answer like this:

```text
I cannot choose a reliable character direction yet. Your actual business, the people who need to trust you, and whether you will appear on camera would all change the plan. Please tell me:

1. Do you mainly sell property, provide consulting, or run a real-estate business?
2. Who do you want to attract, and what makes them distrust this industry or your offer?
3. Will you appear on camera, and what real experience, cases, or on-site material do you have?
```

### When choosing a launch topic

If you have explained that you create AIGC content, understand commercial execution, have a real workflow, and prefer faceless production, it may propose:

```text
Publish this first: I used AI to generate 30 Xiaohongshu drafts, but only 4 were worth publishing.

Why this one:
It shows both AI execution and editorial judgment. The audience does not need to know you beforehand.

Prepare before shooting:
- A real list or thumbnail view of the 30 drafts
- The criteria used to reject drafts
- Before-and-after comparisons for the 4 retained drafts

If you cannot show this process, do not put “30” and “4” in the title.
```

### When writing a script

For “The sales office says the metro is 800 meters away, so I walked it during rush hour,” an excerpt may look like:

```text
0–5 seconds
Visual: “800 meters” on the sales material, then the final phone timer.
Voice-over: The sales office says the metro is only 800 meters away. At 6:30 p.m. on Monday, I walked the route at a real commuting time. It took 【measured minutes】 minutes.

5–12 seconds
Visual: Actual property exit, map route, and metro entrance number.
Voice-over: I started at 【actual starting point】. The destination is not the metro icon on the map; it is 【entrance name】, where you can actually enter the station.

Must capture: start time, actual exit, full route, crossings or detours, entrance number, and stopped timer.
```

Unknown distance, time, and route results remain as placeholders until you measure them.

### When reviewing performance

If you provide the averages from the previous 10 posts, this post's data, and the full content, the answer should separate the evidence:

```text
What we know: three-second retention is below the account's recent average, so the first problem appears before the body begins.

Priority hypothesis: the cover promises a real commute time, but the first visual introduces the property instead of showing the measurement.

What we cannot conclude: one post does not prove platform throttling or that the entire field-test direction has failed.

Change one thing next: show the final timer in the first visual and keep the rest of the script unchanged.
```

### What the other specialists return

Account positioning should produce something operational, not a vague “warm personal brand”:

```text
Account direction: test the commuting and living costs that first-time home buyers cannot see in property advertising.
Reason to follow: every post walks, measures, or verifies one claim for the viewer.
First test: publish 3 commute field tests and watch whether viewers ask about specific properties and routes.
```

Personal IP connects real behavior to the trust the audience needs:

```text
Character focus: not a “successful founder,” but the bakery owner who personally checks ingredients and bake times every morning.
Source of trust: real preparation, how failed batches are handled, and why same-day production matters.
First story: how one product that should have been discarded became today's quality rule.
```

The hook specialist returns one set of elements that can all be fulfilled by the body:

```text
Title: The sales office says the metro is 800 meters away. I walked it during Monday rush hour.
Cover: How long does 800 meters really take?
First sentence: Ignore the map distance for a moment. This is the time from the actual property exit to the station gate.
First visual: the final phone timer.
```

Training uses a real task instead of prescribing “watch 100 videos every day”:

```text
Train one thing: turn an abstract audience into a concrete situation.
Original task: explain metro distance to home buyers.
Rewrite: list the route concerns of a rush-hour commuter, a family with children, and a night-shift worker.
Pass condition: each person can state what problem this post solves for them.
```

## Frequently asked questions

### Which Skill should I use first?

Use `$human-best-video-director`. It decides where to start from the result you want now.

### Can I start with one vague sentence?

Yes. It asks no more than three questions that would change the plan. If you do not want to answer, ask it to proceed with the current information; it should state its assumptions and give one provisional version.

### Why does it sometimes ask questions instead of writing immediately?

Audience, evidence, and production limits can completely change the direction. The questions prevent invented context; they are not a fixed questionnaire.

### Can I request positioning, a topic, and a script at once?

Yes. When the information is sufficient, it continues through the required stages in one response. It pauses only when a missing fact would make the later work unreliable.

### If I already have a topic, will it restart account positioning?

No. A clear script request should use the existing topic and context without expanding the task.

### Can it review content without analytics?

It can review the draft, but it should not pretend to perform data attribution. It can inspect the title, opening, structure, evidence, and reason to follow, while naming what still requires publication data.

### How do I revise an answer that does not match my style?

Give a specific change: “make it more conversational,” “remove industry jargon,” “cut it to 45 seconds,” or “keep the structure and rewrite only the opening.” You do not need to repeat the entire background.

### Does it fetch live trends or publish for me?

Not by default. It does not connect to your platform backend, scrape live data, or publish on your behalf. Provide trend material, account data, or platform rules when you want them included in the judgment.

## What information helps?

You do not need to fill out a questionnaire. Share what you know. These details are usually the most useful:

- Platform and whether the account is new or established.
- The person you want to reach and the situation they are in.
- Your real identity, business, experience, or strongest ability.
- What this piece needs to accomplish: reach, follows, trust, sales, or clear expression.
- Real examples, data, locations, recordings, screenshots, or archive material you have.
- Whether you can appear on camera, target length, budget, and available people.
- The result you want: direction, topic, title, full script, or review plan.

For example:

```text
This is a new Xiaohongshu account.
The audience is office workers buying their first home and commuting by metro.
I make faceless field-test content and have a phone, maps, and real footage.
This video should explain what “800 meters from the metro” means during rush hour.
Give me a 60-second voice-over, timeline, and shot list.
```

If you only have one sentence, that is fine. The main Skill will ask about the few things that matter most.

## A few rules that matter

### One recommendation by default

Unless you explicitly ask for a topic bank or several options, it makes a decision first. One idea you can shoot today is often more useful than ten ideas that all look possible.

### No invented experience or results

Unknown numbers stay blank or are marked clearly. Unconfirmed judgments are treated as assumptions. The Skills should not fabricate client feedback, revenue, views, or historical footage.

### The content must deliver the title's promise

The title, cover, first sentence, first visual, and body should all point to the same value. A louder hook should not hide a weak body.

### A script has to be producible

Crew size, camera preference, available footage, budget, and time all change the plan. For faceless content, the Skills prefer real footage, screen recordings, hands, documents, voice-over, and captions.

### A review should admit uncertainty

Poor numbers do not automatically mean throttling or a bad topic. The review separates observed facts from possible explanations, then chooses one major change for the next test.

## Installation

### skills.sh

Once the repository is public, install it directly with the official Skills CLI. The command lets you choose the Skills and target agent:

```bash
npx -y skills add Eliotcute/human-best-video-director
```

To inspect the Skills without installing them:

```bash
npx -y skills add Eliotcute/human-best-video-director --list
```

### Codex

The repository is public and can be cloned directly:

```bash
gh auth login
git clone https://github.com/Eliotcute/human-best-video-director.git
cd human-best-video-director

mkdir -p ~/.codex/skills
cp -R human-best-video-director hbvd-* ~/.codex/skills/
```

Open a new Codex task and enter:

```text
Use $human-best-video-director to help me complete this content task.
```

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -R human-best-video-director hbvd-* ~/.claude/skills/
```

Claude Code natively uses `SKILL.md`. Install all nine folders so it can choose the right capability for each request. Skill locations can differ by client version or team configuration, so follow the documentation for your current environment.

### Doubao

Doubao Desktop has its own `.skills` workspace mechanism and also uses `SKILL.md` as the core file format. Do not import only Human Best Video Director. All nine Skills must appear in Doubao's Skills directory or its Rules and Skills list; otherwise account planning, topic selection, and script writing may not work correctly.

Doubao versions and workspace layouts change quickly, so this repository does not hard-code a local path. After installing through SkillHub, confirm that `human-best-video-director` and all eight `hbvd-*` Skills are listed. If only one appears, import the nine folders separately.

### TRAE

TRAE supports project-level `.trae/skills`. Copy all nine Skill folders into the current project:

```bash
mkdir -p .trae/skills
cp -R human-best-video-director hbvd-* .trae/skills/
```

Then check TRAE's Rules and Skills view to make sure all nine Skills appear. TRAE may use a different invocation style from Codex's `$skill-name` syntax, so follow the controls shown by your current version. If only one Skill appears, account planning, topic selection, and script writing may not connect automatically.

### Compatibility at a glance

| Environment | Current assessment | Check before use |
|---|---|---|
| Codex | Full support; primary test environment | All nine Skills appear in the available list |
| Claude Code | Full support for `SKILL.md` and multi-Skill installation | Copy all nine folders into the Skills directory |
| Doubao Desktop | Supports the same kind of files; installation varies by version | All nine Skills appear in the list |
| TRAE | Supports `.trae/skills`; usage varies by version | All nine Skills appear, then run one account or script task |
| General chat models | The files can only be used as prompts or knowledge | They will not choose and connect the nine Skills automatically |

### Other agents that support `SKILL.md`

Copy the nine Skill folders into that agent's Skills directory. Confirm that all nine appear, then run one complete request to check whether it can move from clarification to a topic or script. If the client does not support `$skill-name`, use its own invocation syntax.

### Updating

```bash
cd human-best-video-director
git pull --ff-only
cp -R human-best-video-director hbvd-* ~/.codex/skills/
```

Back up the installed copy first if you have edited it directly.

## Boundaries

- No promises of virality, follower growth, revenue, sales, or platform recommendation.
- No invented identities, experience, cases, data, or testimonials.
- New footage must not be presented as historical footage.
- A guess must not be presented as a conclusion when the evidence is incomplete.
- Explicit constraints such as faceless production, budget, length, and crew size must be respected.
- The Skills do not replace legal, medical, or investment advice.

## Repository layout

```text
human-best-video-director/
├── README.md
├── README.en.md
├── README.zh-TW.md
├── LICENSE
├── human-best-video-director/   # Main router
├── hbvd-intake/                 # Clarify the request
├── hbvd-account/                # Account positioning and launch
├── hbvd-ip/                     # Personal IP and founder stories
├── hbvd-topic/                  # Topic decisions
├── hbvd-hook/                   # Title, cover, and opening
├── hbvd-script/                 # Script and production plan
├── hbvd-review/                 # Draft and data review
└── hbvd-training/               # Director training
```

Each Skill folder contains:

```text
SKILL.md
agents/openai.yaml
```

## License

This project is licensed under [Creative Commons Attribution-NonCommercial 4.0 International](LICENSE).

You may copy, share, and adapt the project with appropriate attribution, but not for commercial purposes. See the [official Creative Commons legal code](https://creativecommons.org/licenses/by-nc/4.0/legalcode) for the full terms.
