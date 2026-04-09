+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
type = 'sayings'

# Umbrella + Street Wisdom project hub. Remove Venezuelan-Street-Wisdom if this post is not that series.
categories = ['Cognitive-Memetics', 'Venezuelan-Street-Wisdom']

# Optional label before the title (e.g. week id); styled via .heading-code in _custom.scss
heading_code = ''

# Series line on the detail hero (e.g. Arepa-Contigo for the Venezuelan hub). `title` = unique episode name (lists, prev/next). Leave empty for one-line titles.
project = ''

# Used by layouts/sayings/single.html (section list shows TLDR + Context)
tldr = ''
fluff = ''
+++

