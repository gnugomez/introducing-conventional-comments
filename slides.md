---
theme: seriph
themeConfig:
  primary: "#F06C01"
title: Introducing Conventional Comments
info: |
  ## 
  a quick walkthrough of the new [conventional comments](https://conventionalcomments.org/) initiative, should not be confused with [conventional commits](https://www.conventionalcommits.org/).
class: text-center
transition: slide-left
mdc: true
---

# Introducing **conventional comments**

a quick walkthrough of the new [conventional comments](https://conventionalcomments.org/) innitiative, should not be confused with [conventional commits](https://www.conventionalcommits.org/).

---

<div class="grid grid-cols-2 gap-4">

<div class="flex flex-col gap-6">

## You create a PR/MR 

<div v-click>
<Comment username="Alice">
  <template #comment>

This is not worded correctly.

  </template>
</Comment>
</div>
<div v-click>
Comments like this are unhelpful… 
</div>

<div v-click class="flex flex-col gap-4">
By simply prefixing the comment with a label, the intention is clear and the tone dramatically changes. 

<Comment username="Alice">
  <template #comment>

**suggestion:** This is not worded correctly. 

  </template>
</Comment>
<Comment username="Alice">
  <template #comment>

**issue (non-blocking):** This is not worded correctly. 

  </template>
</Comment>
</div>

</div>

<div h-full flex items-center v-click>

<div text-yellow p-8>

The first comment is a **suggestion** and the second one is an **issue**. 

Are meant to be addressed in a completely different way.

</div>

</div>


</div>

---

## It can also help you as a reviewer

Labels also prompt the reviewer to give more actionable comments. 

<Comment username="sharon" name="Sharon">
  <template #comment>

**suggestion:** This is not worded correctly.

Can we change this to match the wording of the marketing page?

  </template>
</Comment>

<div v-click>

Labeling comments encourages collaboration and saves hours of undercommunication and misunderstandings. They are also parseable by machines!

</div>

---

## The format is simple

Here’s the format they propose:

```
<label> [decorations]: <subject>

[discussion]
```

<div class="grid grid-cols-2 gap-8 mt-8">

<div>

**Required:**
- `label` - what kind of comment 
- `subject` - the main message

**Optional:**
- `decorations` - extra context (non-blocking, security, etc.)
- `discussion` - supporting details and reasoning

</div>

<div>

<Comment username="Olivier">
  <template #comment>

**suggestion (security):** This function needs validation.

We should sanitize user input here to prevent XSS attacks. Consider using the framework's built-in validation instead.

  </template>
</Comment>

</div>

</div>

---

## Available labels

<div class="grid grid-cols-2 gap-4 text-sm">

<div>

**Core labels:**
- `praise:` - highlight something positive
- `nitpick:` - trivial preference-based requests  
- `suggestion:` - propose improvements
- `issue:` - highlight specific problems
- `todo:` - small, necessary changes
- `question:` - seek clarification
- `thought:` - ideas from reviewing
- `chore:` - process-related tasks
- `note:` - highlight something to note

</div>

<div>

**Expressive alternatives:**
- `typo:` - misspelling (like todo)
- `polish:` - improve quality (like suggestion)
- `quibble:` - trivial preference (like nitpick)

**Common decorations:**
- `(non-blocking)` - shouldn't prevent acceptance
- `(blocking)` - should prevent acceptance  
- `(if-minor)` - resolve only if changes are minor

</div>

</div>

---

## More examples

<div class="flex flex-col gap-4 mt-8">

<Comment username="madhatter" name="Mad Hatter">
  <template #comment>

**nitpick:** `little star` => `little bat`

Can we update the other references as well?

  </template>
</Comment>

<Comment username="alice" name="Alice">
  <template #comment>

**chore:** Let's run the `jabber-walk` CI job to make sure this doesn't break any known references.

Here are [the docs](https://en.wikipedia.org/wiki/Jabberwocky) for running this job. Feel free to reach out if you need any help!

  </template>
</Comment>

<Comment username="cheshire" name="Cheshire Cat">
  <template #comment>

**praise:** Beautiful test!

  </template>
</Comment>

</div>

---

## Tools to help you adopt it

**Pullpo** (Spanish team) created browser extensions (open source) to make it easy:

<div class="grid grid-cols-2 gap-8 mt-8">

<div>

**Features:**
- 🎨 Intuitive toolbar integrated into GitHub & GitLab
- 🏷️ All standard labels (praise, nitpick, suggestion, issue, etc.)
- 🎯 Decorations (non-blocking, blocking, if-minor)
- 🔄 Toggle functionality and badge-style formatting

</div>

<div>

**Installation:**
- **Chrome:** [Chrome Web Store](https://chromewebstore.google.com/detail/gelgbjildgbbfgfgpibgcnolcipinmlp)
- **Firefox:** [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/conventional-comments-pullpo/)
- **GitHub:** [pullpo-io/conventional-comments](https://github.com/pullpo-io/conventional-comments)

Works automatically on GitHub.com and GitLab.com!

</div>

</div>

---
layout: center
class: text-center
---

# Thank you for your attention!

<PoweredBySlidev mt-10 />