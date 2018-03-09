---
title: {{ replace .TranslationBaseName "-" " " | title }}
description: 
author:
image: {{ if in .Dir "posts" }}post-bg.jpg{{ else if in .Dir "interview" }}interview-bg.jpg{{ end }}
images: []
date: {{ .Date }}
type: post
draft: true
comments: true
---