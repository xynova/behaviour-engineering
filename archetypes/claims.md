+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
type = 'claims'

# Optional label before the title; styled via .heading-code in _custom.scss
heading_code = ''

# First sidebar block on section lists is "Claim" (type: claims).
description = ''

# Citations / evidence that ground the claim (Markdown). Legacy key `paper` still works.
grounding = ''

research = ''

# Optional Markdown attribution: detail meta above hero; section list under thumbnail. Omit if not needed.
image_credit = ''
+++
