---
layout: 'post'
title: "Appunti su AWK"
author: 'Claudio'
lang: 'it'
---

In questi giorni ho avuto la necessità di estrapolare da un file di testo alcune stringhe di mio interesse. Il file aveva un pattern ben definito e ogni valore era intervallato da uno spazio.

Una possibilità poteva essere l'utilizzo di un software per fogli elettronici, ma ho voluto preferire un approccio più pulito.
Sotto consiglio di un collega ho provato a utilizzare AWK, un comodo strumento da linea di comando preinstallato in tutte le distribuzioni Linux più comuni, orientato alla manipolazione di dati testuali.

Inizio creando un file di esempio, che per comodità chiamerò *values.txt*:

{% highlight shell %}
FV143 Tybi Poetz tpoetz0@sciencedaily.com Genderfluid	
FV222 Brose Took btook1@cdbaby.com Bigender	
SV354 Teador Landells tlandells2@telegraph.co.uk Agender
FV447 Hailee Slocum	hslocum3@exblog.jp Female
FV551 Celestia Butterly cbutterly4@abc.net.au Agender
SV891 Ky Pietersma kpietersma5@feedburner.com Agender
SV196 Marlie Kneal mkneal6@huffingtonpost.com Polygender
FV264 Cyndia Gilbank cgilbank7@vinaora.com Non-binary
SV119 Gill Sabati gsabati8@msn.com Bigender
SV971 Sada Giddens sgiddens9@squarespace.com Bigender
{% endhighlight %}

Posso per esempio filtrare il contenuto del file, mostrando solamente la prima colonna, digitando da terminale il seguente comando:

{% highlight shell %}
awk '{print $1}' values.txt
{% endhighlight %}

Il cuore del comando impartito poc'anzi è contenuto all'interno delle parentesi graffe, dove è possibile scrivere lo script vero e proprio che in questo caso andrà a selezionare la prima colonna.

Per selezionare più colonne, è sufficiente scrivere a seguito di *$1* il numero delle colonne di nostro interesse:

{% highlight shell %}
awk '{print $1 "\t" $4}' values.txt
{% endhighlight %}

Al fine di rendere più leggibile il risultato, ho inserito una tabulazione "\t" tra le due colonne, che altrimenti sarebbero state visualizzate senza spaziatura.
