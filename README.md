# Suraj Thalange

**Moodle developer and technical project manager.** I build plugins and themes for Moodle, put them
through the Marketplace review, and keep them working on every version they claim to support.

[Portfolio](https://surajthalange.github.io) ·
[One Life on the Moodle Marketplace](https://marketplace.moodle.com/plugins/4140) ·
surajthalange18@gmail.com

---

## Published work

| Plugin | What it does | Moodle | Tests | Status |
|---|---|---|---|---|
| **[mod_onelife](https://github.com/surajthalange/moodle-mod_onelife)** | Self-directed revision built from a course question bank. One wrong answer ends the run; the score is the streak. | 4.5 – 5.2 | 176 unit, 5 Behat | **Live on the Marketplace** |
| **[report_transcript](https://github.com/surajthalange/moodle-report_transcript)** | Every learner's courses, dates, grades and outcomes: a page, a branded PDF, and a public verification page the code on it resolves to. | 4.5 – 5.2 | 61 unit, 5 Behat | **Review passed**, awaiting publication |
| **[theme_atrium](https://github.com/surajthalange/moodle-theme_atrium)** | A Boost child theme: collapsible sidebar, Ctrl+K command palette, accessibility toolbar, real print stylesheet. | 5.1 – 5.2 | 73 unit, 20 Behat | In review |

Each one runs the full `moodle-plugin-ci` matrix on every supported Moodle branch, on each PHP
version that branch allows, against PostgreSQL and MariaDB. A support range I have not tested is a
guess, so I do not claim one.

## How that has gone

> "I didn't find any blockers and recommend this plugin for approval."
>
> — Moodle Marketplace reviewer, on my first submission

The second submission did not go like that. The reviewer found a real grade-visibility leak in
`report_transcript`: it resolved a course total and printed it on the page, in the PDF and on a
public verification page, without ever asking whether the course showed grades to learners at all.
A teacher who had switched the gradebook off still had that total published. The finding was
correct, it was an approval blocker, and it shipped fixed the same day with tests for each case
the reviewer named.

I wrote up [what the Marketplace review actually checks](https://surajthalange.github.io/notes/what-the-moodle-review-checks/),
including that finding and the real timelines, because almost nothing about it is written down
anywhere and I wanted it to exist before I needed it again.

## How I build

Moodle-native rather than bolted on: capabilities and roles, the privacy API, language strings,
backup and restore, upgrade steps, events, scheduled tasks, MUC caching. PSR-4 classes and the
Moodle coding standard. Accessibility checked against WCAG 2.1 AA rather than assumed.

**Working with:** PHP · Moodle API · MySQL, MariaDB, PostgreSQL · JavaScript (AMD) · SCSS ·
Mustache · PHPUnit · Behat · GitHub Actions · Linux and Nginx

## Elsewhere

- **[surajthalange.github.io](https://surajthalange.github.io)** — case studies, and notes on what
  a Moodle theme costs in page weight and what the plugin review actually looks for
- Available for Moodle work: plugin and theme development, LMS implementation, upgrades and audits
