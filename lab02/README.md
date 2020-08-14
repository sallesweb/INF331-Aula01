# Modelo para Apresentação do Lab02 - Data Flow & Mensagens

## Tarefa sobre catálogo de componentes

> [Catálogo de componentes](notebook/components-01-catalog.ipynb)

## Tarefa Web Components 1
> Escreva aqui o código da sua composição de componentes Web, como mostra o exemplo a seguir:
``` html
<dcc-trigger label="Mundo"
             action="noticia/mundo/politica"
             value="O vice-presidente do Egito , Mahmoud Mekki, renunciou, informou neste sábado a TV estatal.">
</dcc-trigger>

<dcc-trigger label="Brasil P"
             action="noticia/brasil/politica"
             value="Presidente do Supremo está em casa, segundo assessoria do tribunal.">
</dcc-trigger>

<dcc-trigger label="Brasil E"
             action="noticia/brasil/esporte"
             value="Nas artes marciais, os brasileiros desenvolveram a capoeira, o vale-tudo, e o jiu-jitsu brasileiro.">
</dcc-trigger>

<dcc-trigger label="Bahia"
             action="noticia/bahia/esporte"
             value="A Bahia é um estado brasileiro localizado na região Nordeste.">
</dcc-trigger>

<dcc-lively-talk duration="0s"
                 character="doctor"
                 speech="Doctor: ">
  <subscribe-dcc topic="noticia/#/politica"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0s"
                 character="nurse"
                 speech="Nurse: ">
  <subscribe-dcc topic="noticia/brasil/#"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0s"
                 character="patient"
                 speech="Patient: ">
  <subscribe-dcc topic="noticia/#"></subscribe-dcc>
</dcc-lively-talk>
```

## Tarefa Web Components 2
``` html
<dcc-trigger label="Novas notícias" action="next/rss"></dcc-trigger>

<dcc-rss source="https://www.wired.com/category/science/feed" publish="rss/science">
  <subscribe-dcc topic="next/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-rss source="https://www.wired.com/category/design/feed" publish="rss/design">
  <subscribe-dcc topic="next/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-aggregator publish="aggregate/science" quantity="3">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-aggregator>

<dcc-lively-talk id="doctor"
                 duration="0s"
                 character="doctor"
                 speech="Doctor: ">
  <subscribe-dcc topic="aggregate/science"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk id="nurse"
                 duration="0s"
                 character="nurse"
                 speech="Nurse: ">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk id="patient"
                 duration="0s"
                 character="patient"
                 speech="Patient: ">
  <subscribe-dcc topic="rss/design"></subscribe-dcc>
</dcc-lively-talk>
```