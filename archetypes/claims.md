+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
type = 'claims'

# Optional label before the title; styled via .heading-code in _custom.scss
heading_code = ''

# First sidebar block. In reality-protocols the label is "Claim"; elsewhere "TLDR".
description = ''

# Citations / evidence that ground the claim (Markdown). Legacy key `paper` still works.
grounding = ''

research = ''
+++
