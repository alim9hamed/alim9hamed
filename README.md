<!--     Header -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=Hello%20World!😁&fontSize=70&animation=blink&fontAlign=33&fontAlignY=30" />
<!--     Paragragh -->
<p>I'm <b>Ali</b>, an ML Engineer, Data Scientist, Data Analyst, and Senior Student at the Faculty of Computer Science and Artificial Intelligence, at Fayoum University. If you need any help, please feel free to contact me.</p>
<!--     Links -->
<h1>Contact Us</h1>
<a href="https://www.linkedin.com/in/ِali-mohamed-4218391b1">
  <img height="50" src="linkedin.png"/>
</a>
<a href="https://www.facebook.com/profile.php?id=100078176362609&mibextid=b06tZ0">
  <img height="50" src="facebook.png"/>
</a>
<a href="https://www.kaggle.com/alimohamed01">
  <img height="50" src="kaggle.png"/>
</a>
<a href="mailto:alim9hamem1000@gmail.com">
  <img height="50" src="email.png"/>
</a>
<!--     Footer -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=100&section=footer&fontSize=70&animation=blink&fontAlign=33&fontAlignY=30" />

name: "generate-snake-game-from-github-contribution-grid"
description: "Generates a snake game from a github user contributions grid. Output the animation as gif or svg"
author: "platane"

runs:
  using: docker
  image: docker://platane/snk@sha256:753878055e52fbbaf3148fdac4590e396f97581f1dc4c1f861701add7a1dc1b5

inputs:
  github_user_name:
    description: "github user name"
    required: true
  outputs:
    required: false
    default: null
    description: |
      list of files to generate.
      one file per line. Each output can be customized with options as query string.
       supported query string options:
      - palette:      A preset of color, one of [github, github-dark, github-light]
      - color_snake:  Color of the snake
      - color_dots:   Coma separated list of dots color. 
                      The first one is 0 contribution, then it goes from the low contribution to the highest.
                      Exactly 5 colors are expected.
      example:
        outputs: |
          dark.svg?palette=github-dark&color_snake=blue
          light.svg?color_snake=#7845ab
          ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
