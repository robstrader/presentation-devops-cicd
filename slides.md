---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /images/mountain-background.jpg
# some information about your slides (markdown enabled)
title: "Build, Test, and Deploy Again: A DevOps Tale"
info: |
  ## Rundown of the principles of DevOps
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: fade
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# CI/CD: Build, Test, and Deploy Again... A DevOps Tale

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  One does not simply skip to the next slide. <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/robstrader/presentation-devops-cicd" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: slide-up
layout: image-right
image: /images/ui-component-developer.jpg
---

# Who am I?

Senior Software Developer at SAS

- 👴 **Experience** - 13+ years of experience in Software Development at SAS concentrating mostly on frontend development.
  - <div><carbon:logo-react /> 6+ years in React</div>
  - <div><carbon:workflow-automation /> 4+ years on Enterprise UI Ops Team</div>
  - 🖥️ Frontend Application Development
  - 🖌️ UI Component Development
  - 🏗️ Application Builds
  - 🧪 Testing
  - 🔒 Security Scans
  - 🏛️ Architecture of a UI component Library/Framework

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg,hsl(228, 85.80%, 69.60%) 5%,rgb(213, 229, 247) 50%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
- Describe SAS some.
- Discuss my background a bit, how I became a developer.
- Transition to what we are going to build.
-->

---
transition: slide-left
layout: image-right
image: /images/cicd-end.png
backgroundSize: contain
---

# What are we building?

A simple Vite Single Page Application (SPA) with a few components, a test suite and a deployment pipeline.

- **Vite** - A modern build tool for frontend projects.
- **Vitest** - A test runner for Vite.
- **GitHub Actions** - A CI/CD tool for GitHub repositories.
- **GitHub Pages** - A free static site hosting service.

<!--
- Briefly discus each of these tools and what they do.
- Mention that these are just tools, and that they could easily be replaced with others, but the principles would remain the same.
- These are examples of how to implement CI/CD, so let's discuss what CI/CD is.
-->

---
transition: slide-down
layout: image-right
image: /images/ci.png
---

## Continuous Integration (CI)

<br />

- Combines code frequently to prevent "integration hell".
- Catches bugs early with automated tests.
- Saves time by automating builds and testing.
- Keeps the team aligned with the latest code.
- Ensures software is stable and ready to use.

<br />

<v-click>

### Practices

</v-click>

<v-clicks>

- Commit code frequently to a shared repository.
- Run automated tests on each change.
- Fix bugs as soon as they are detected.
- Keep builds fast and reliable.

</v-clicks>

<!--
- There is only one interesting version of the code.
- Changes are always visible.
- Makes code reviewing so much easier.
- Keep unfinished features unreachable or behind a feature flag.
-->

---
transition: slide-down
layout: image-right
image: /images/delivery.jpg
---

## Continuous Delivery (CD)

<br />

- Ensures code is ready for deployment.
- Verifies changes through automated tests.
- Reduces risk by deploying smaller, tested updates.
- Rapid delivery with high quality.
- Allows teams to release manually or automatically.

<br />

<v-click>

### Practices

</v-click>
<v-clicks>

- Code passes all tests before deployment.
- Use automation to deploy updates efficiently.
- Deploy smaller, incremental changes.
- Monitor deployments for issues.

</v-clicks>

<!--
- Shortens the lengths of plans. Keep plans small.
- Recover quickly from failures.
- Comes from the Agile Manifesto.
- Logical extension of CI.
- Try to disprove that the software is in a good state.
- Releasibility is the target, which makes releasing a business decision, not a technical one.
-->

---
layout: default
transition: slide-left
---

# What is DevOps?

<v-switch>
  <template v-slot:1>
    <div class="text-2xl"><em>DevOps is the integration and automation of the software development and information technology operations. -Wikipedia</em></div>
    <br />
    <div class="text-2xl"><em>Culture, Automation, Measurement, Sharing(CAMS) -John Willis</em></div>
    <br />
    <div class="text-2xl"><em>A set of practices intended to reduce the time between committing a change to a system and the change being placed into normal production, while ensuring high-quality. -Len Bass, Ingo Weber & Liming Zhu</em></div>
    <br />
    <div class="text-2xl"><em>Optimizing the human experience and performance of software... with software... and with humans. -Andrew Clay Shafer</em></div>
    
  </template>

  <template v-slot:2>
  <img
    src="/images/devops.png"
    class="w-full"
  />
  </template>
  <template v-slot:3>
  <div style="display: flex; justify-content: center; align-items: center; height: 100%;">
  <img
    src="/images/mess.png"
    class="h-auto w-1/2"
  />
  </div>
  </template>
</v-switch>

---
layout: two-cols-header
---

# Principles of DevOps

::left::

- **Flow:**

  - Prioritize the flow to customers.
  - Minimize bottlenecks.

- **Feedback:**

  - Amplify feedback.
  - Shorten feedback loops.
  - Encourage collaboration.

- **Continuous Improvement:**
  - Create a culture of experimentation.
  - Learn from failures.
  - Share knowledge.

::right::

<div class="flex h-full items-center justify-center">

```mermaid {alt: 'Flow, Feedback and Continuous Improvement', scale: 1}
flowchart LR
    %% Define Nodes
    CI[Continuous Improvement]:::ciStyle e3@--> loop
    subgraph loop[Flow Feedback Loop]
        Flow:::flowStyle e1@--> Feedback:::feedbackStyle
        Feedback:::feedbackStyle e2@--> Flow:::flowStyle
    end

    %% Define Animations
    e1@{ animate: true }
    e2@{ animate: true }
    e3@{ animate: true }

    %% Node Styles
    classDef ciStyle fill:#FCE4EC,stroke:#EC407A,stroke-width:2px,color:#880E4F;
    classDef flowStyle fill:#E3F2FD,stroke:#42A5F5,stroke-width:2px,color:#0D47A1;
    classDef feedbackStyle fill:#E8F5E9,stroke:#66BB6A,stroke-width:2px,color:#1B5E20;

    %% Subgraph Style
    style loop fill:#000000,stroke:#FFD54F,stroke-width:2px,color:#FF8F00;

```

</div>

---
layout: default
---

# The History of DevOps

<div class="flex h-full items-center justify-center">

```mermaid {alt: 'A brief history of DevOps', scale: 0.8}
timeline
    2001 : Agile Manifesto
    2006 : Amazon adopts "You build it, you run it" model
    2009 : John Allspaw and Paul Hammond present "10+ Deploys Per Day"
         : First DevOpsDays conference in Ghent, Belgium
    2011 : The Phoenix Project <br>by Gene Kim, Kevin Behr, and George Spafford
    2014 : The DevOps Handbook <br>by Gene Kim, Jez Humble, Patrick Debois, and John Willis
```

</div>

<!--
One gets a good rating fighting a fire. The result is visible; can be quantified. If you do it right the first time, you are invisible. You satisfied the requirements. That is your job. Mess it up, and correct it later, you become a here. - W. Edward Demin
-->

---
layout: default
---

# The History of the History of DevOps

<div class="flex justify-center">

```mermaid {alt: 'A brief history the history of DevOps', scale: 0.8}
timeline
    1908 : First Ford Model T
    1911 : The Principles of Scientific Management by Frederick Winslow Taylor
    1930s - 1940s : Shewart and Deming develop Statistical Quality Control
    1940s - 1950s : Toyota and Mitsubishi on Lean Manufacturing
    1950s - 1960s : Lean Manufacturing implemented by Toyota Production System
```

</div>

<!--
Maybe talk about when Deming's 14 points were developed?
Plan Do Check Act
-->

---
transition: slide-down
layout: two-cols
---

## Continuous Integration (CI)

<br />

- Combines code frequently to prevent "integration hell."
- Catches bugs early with automated tests.
- Saves time by automating builds and testing.
- Keeps the team aligned with the latest code.
- Ensures software is stable and ready to use.

<br />

### Practices

- Commit code frequently to a shared repository.
- Run automated tests on each change.
- Fix bugs as soon as they are detected.
- Keep builds fast and reliable.

::right::

## Continuous Delivery (CD)

<br />

- Ensures code is always ready for deployment.
- Verifies every change through automated tests.
- Reduces risk by deploying smaller, tested updates.
- Speeds up delivery while keeping quality intact.
- Allows teams to release manually or automatically, as needed.

<br />

### Practices

- Ensure code passes all tests before deployment.
- Use automation to deploy updates efficiently.
- Deploy smaller, incremental changes.
- Monitor deployments for issues and feedback.

<!--
Context matters!

 "In theory, there is no difference between theory and practice. But, in practice, there is." - Yogi Berra
-->
