+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
type = 'papers'

# Optional label before the title; styled via .heading-code in _custom.scss
heading_code = ''

# Blurb for the first sidebar block. In section reality-protocols the label is "Claim"; elsewhere "TLDR".
description = ''

# Optional blocks (Markdown). Use one or both.
paper = ''
research = ''
+++
