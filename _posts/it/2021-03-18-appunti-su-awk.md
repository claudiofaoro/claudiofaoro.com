---
layout: 'post'
title: "Appunti su AWK"
author: 'Claudio'
lang: 'it'
---

In questi giorni ho avuto la necessità di estrapolare da un file di testo alcune stringhe di mio interesse. Il file aveva un pattern ben definito e ogni valore era intervallato da uno spazio.

Una possibilità poteva essere l'utilizzo di un software per fogli elettronici, ma ho voluto preferire un approccio più pulito.
Sotto consiglio di un collega ho provato a utilizzare AWK, un comodo strumento da linea di comando preinstallato in tutte le distribuzioni Linux più comuni, orientato alla manipolazione di dati testuali.

Iniziamo subito con un file di esempio:

{% highlight shell %}
1 Tybi Poetz tpoetz0@sciencedaily.com Genderfluid	
2 Brose Took btook1@cdbaby.com Bigender	
3 Teador Landells tlandells2@telegraph.co.uk Agender
4 Hailee Slocum	hslocum3@exblog.jp Female
5 Celestia Butterly cbutterly4@abc.net.au Agender
6 Ky Pietersma kpietersma5@feedburner.com Agender
7 Marlie Kneal mkneal6@huffingtonpost.com Polygender
8 Cyndia Gilbank cgilbank7@vinaora.com Non-binary
9 Gill Sabati gsabati8@msn.com Bigender
10 Sada	Giddens	sgiddens9@squarespace.com Bigender
{% endhighlight %}

Per comodità ci salveremo questo testo all'interno di un file che chiamerò  
