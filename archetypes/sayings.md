+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
type = 'sayings'

# Optional label before the title (e.g. week id); styled via .heading-code in _custom.scss
heading_code = ''

# Used by layouts/sayings/single.html (section list shows TLDR + Context)
tldr = ''
fluff = ''
+++

