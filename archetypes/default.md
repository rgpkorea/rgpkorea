---
title: {{ replace .TranslationBaseName "-" " " | title }}
description: 
author:
image: {{ if in .Dir "posts" }}post-bg.jpg{{ else if in .Dir "interview" }}interview-bg.jpg{{ end }}
images: []
tags: ["rgp", "tech", "blog", "요기요", "배달통"]
date: {{ .Date }}
type: post
draft: true
comments: true
---