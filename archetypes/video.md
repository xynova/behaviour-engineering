+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
type = 'video'

# Short pitch for list cards and the lead on the page (Markdown ok).
description = ''

# From the watch URL: …youtube.com/watch?v=THIS_PART
youtube_id = ''

subtitle = ''

# Use umbrella hubs such as Mind-Infrastructure or Human-Condition (see other posts in those sections).
categories = ['Mind-Infrastructure']

tags = []
+++

Why this video is worth your time (body). Alternatively, leave `youtube_id` empty and add the built-in YouTube shortcode in Markdown.
