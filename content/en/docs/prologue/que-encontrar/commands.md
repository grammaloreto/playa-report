---
title: "Que vas a encontrar"
description: "Doks comes with commands for common tasks."
lead: "Paquetes tecnologicos poco convencionales pero que amplian el conocimiento y pueden brindar informacion valiosa de costas-playas y todo lo que pueda girar en torno a ellas."
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "prologue"
weight: 130
toc: true
---

{{< alert icon="💡" text="Nos estamos ahogando en información, mientras estamos hambrientos de sabiduría. El mundo de ahora en adelante estará dirigido por sintetizadores, personas capaces de reunir la información correcta en el momento correcto, piense críticamente al respecto y tome decisiones importantes sabiamente. (E O. Wilson)" />}}

## create

Create new content for your site:

```bash
npm run create [path] [flags]
```

See also the Hugo docs: [hugo new](https://gohugo.io/commands/hugo_new/).

### Docs based tree

Create a docs based tree — with a single command:

```bash
npm run create -- --kind docs [section]
```

For example, create a docs based tree named guides:

```bash
npm run create -- --kind docs guides
```

## lint

Check scripts, styles, and markdown for errors:

```bash
npm run lint
```

### scripts

Check scripts for errors:

```bash
npm run lint:scripts [-- --fix]
```

### styles

Check styles for errors:

```bash
npm run lint:styles [-- --fix]
```

### markdown

Check markdown for errors:

```bash
npm run lint:markdown [-- --fix]
```

## clean

Delete temporary directories:

```bash
npm run clean
```

## start

Start local development server:

```bash
npm run start
```

## build

Build production website:

```bash
npm run build
```

### functions

Build Lambda functions:

```bash
npm run build:functions
```

### preview

Build production website including draft and future content:

```bash
npm run build:preview
```
