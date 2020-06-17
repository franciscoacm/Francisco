---
layout: post
title: Productive Laziness - Optimize your Shell Workflow
head_title: Productive Laziness - Optimize your Shell Workflow [Ruby Gem]
date: 2018-01-08T16:26:52+01:00
summary: I would like to share a simple productivity tip that probably helped me save thousands of keystrokes so far. I’ve been using this technique for a while now to maximize my laziness (productivity) during work and so, recently I wrapped it up in an easy to use Ruby Gem.
last_modified_at: 2018-02-01T22:10:10+01:00
preview_image: lazy-cat.jpg
thumb_image: lazy-cat-thumb.jpg
main_image_description: Cat represents productive shell bash workflow
---

I would like to share a simple productivity tip that probably helped me save thousands of keystrokes so far.

I’ve been using this technique for a while now to maximize my laziness (_productivity_) during work and so, recently I wrapped it up in an easy to use [Ruby Gem](https://github.com/pawurb/lazyme){: .link target='_blank'}. It simply counts your shell commands and displays them sorted by usage frequency. Using it is as simple as typing:

{% highlight bash %}
gem install lazyme
lazyme
{% endhighlight %}

This is how my most used commands look now. Top hits are usually a good candidate for new aliases:


{% highlight text %}
+---------------------------------------------+-------+
|                     Lazyme                          |
+---------------------------------------------+-------+
|...                                          | ...   |
| ei                                          | 21    |
| gpstg                                       | 22    |
| gstp                                        | 23    |
| zs                                          | 28    |
| s .                                         | 30    |
| zrr                                         | 32    |
| gpshh                                       | 60    |
| rss                                         | 70    |
| c                                           | 75    |
| gd                                          | 107   |
| o .                                         | 123   |
| gst                                         | 130   |
| ls                                          | 179   |
| gl                                          | 310   |
| gp                                          | 445   |
| gds                                         | 540   |
| gaa                                         | 817   |
| g                                           | 3365  |
+---------------------------------------------+-------+
| Command                                     | Count |
+---------------------------------------------+-------+
{% endhighlight %}

With almost all top commands being aliases, I am now sure I work as lazily as possible.

I know that some developers don’t like using aliases because they worry that they might keep forgetting them. To fix this problem, I have a special alias `aliases` which displays a list of all my aliases (btw `gr` is an alias for `grep`).

{% highlight bash %}
aliases | gr aliases
=> alias 'aliases'='cat ~/.dotfiles/settings/shell/aliases.sh'
{% endhighlight %}

Some say that if you get used to using aliases too much you might have a problem with working efficiently on remote servers which lack your custom config settings. I solved this problem with a couple of aliases which upload a list of my most essential aliases to remote servers (`ubash`, `uvim` and `ugit`). Just be careful not to overwrite some important settings if you don’t own the server. Whether you want to sacrifice your productivity when working locally, to avoid some possible problems when working on remote server is entirely up to you.

You can set aliases and helper functions by adding following lines into your `.bashrc` or `.zshrc` files:

{% highlight bash %}
alias gr='grep — color'
alias g='git status'
alias gaa='git add . -A'

function gm() {
  git commit -m "$*"
}
{% endhighlight %}

I, therefore, encourage you to show your fingers some love and treat them to a couple of nice aliases.
