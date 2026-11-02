---
# Home page content. This file holds the banner and feature blocks; the other
# home page sections are in their own files (order is set in layouts/home.html):
#   - Organizan: sections/organizan.md
#   - Apoyos:    sections/apoyos.md
#   - Anfitrión: sections/anfitrion.md

# Banner
banner:
  title: "Hackathon RSE 2027"
  # the word in the title that is deleted and re-typed in cursive, on a loop
  title_rewrite:
    word: "Hackathon"
    to: "hackatón"
  content: "Descubre de qué va la **ingeniería de software de investigación** con mini-proyectos en grupo."
  image: "/images/banner.png"
  image_alt: "Ilustración de una persona trabajando con un computador portátil en un escritorio"
  button:
    enable: true
    label: "-> más información"
    # "#..." jumps to the feature with that id below
    link: "#que-es"
  # smaller text above the button, one line per item
  details:
    - "📍 Santiago de Chile, 12 - 14 enero 2027"
    - "Campus San Joaquín (UC Chile)"

# Features
features:
  - title: "¿Qué es el Hackathon RSE?"
    id: "que-es"
    image: "/images/service-1.png"
    image_alt: "Ilustración de tarjetas de interfaz: un reproductor de video, gráficos de barras y controles deslizantes"
    content: ""
    bulletpoints:
      - "Un ***hackathon*** es un encuentro de duración limitada en el que equipos de participantes trabajan de forma intensiva para desarrollar una idea o resolver un reto concreto, normalmente programando. "
      - "En este caso, queremos dar a conocer la profesión de ***ingeniero de software de investigación*** (o RSE por las siglas en inglés de _Research Software Engineer_), que hace referencia a los y las profesionales que desarrollan y mantienen el software usado en la investigación científica"
      - "Esperamos reunir a participantes con perfiles y experiencias variadas. También invitaremos a ponentes de ediciones anteriores del seminario [Charlas RSE en español](https://charlas-rse-espanol.github.io/sessions/) a participar en línea. "
    button:
      enable: false
      label: ""
      link: ""

  - title: "¿Quién puede participar?"
    image: "/images/service-2.png"
    image_alt: "Ilustración de tarjetas con gráficos de barras, un gráfico de anillo y un gráfico de líneas"
    content: "Nos gusta la variedad: buscamos participantes con diversidad de trayectorias y experiencias. Si escribes código en el contexto de proyectos de investigación, ya eres parte de la comunidad RSE, ¡aunque no lo sepas!"
    bulletpoints:
      - "Estudiantes de postgrado"
      - "Investigadores postdoctorales, personal técnico"
      - "Con formación en ciencias, humanidades o tecnológico"
    button:
      enable: true
      label: "Postula"
      # empty = the application form URL (navigation_button.link in config/_default/params.toml)
      link: ""

# Centred button shown below the features
more_info_button:
  enable: true
  label: "-> Sobre el hackathon"
  link: "sobre-el-hackathon/"
---
