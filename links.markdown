---
layout: custom
links:
    - link: https://www.stilldrinking.org/programming-sucks
      title: Programming Sucks
    - link: https://users.cs.utah.edu/~elb/folklore/mel.html
      title: The Story of Mel
    - link: https://www.pbm.com/~lindahl/real.programmers.html
      title: Real Programmers Don't Use Pascal
    - link: https://www.teamten.com/lawrence/writings/coding-machines/
      title: Coding Machines
    - link: https://steve-yegge.blogspot.com/2006/03/execution-in-kingdom-of-nouns.html
      title: The Kingdom of Nouns
---
Random things I've enjoyed reading
<ul>
{% for link in page.links %}
      <li><a href="{{ link.link }}">{{ link.title }}</a></li>
{% endfor %}
</ul>

