---
layout: post
title: GRNVS Summary
---
Kap 0 - Einführung
=====
<details>
    <summary>ISO / OSI Schichtenmodell:</summary>
    <table style="width:100%">
        <tr>
            <td>Anwendungsschicht</td>
            <td>Application Layer</td>
            <td>HTTP, STMP, POP3</td>
        </tr>
        <tr>
            <td>Darstellungsschicht</td>
            <td>Presentation Layer</td>
        </tr>
        <tr>
            <td>Sitzungsschicht</td>
            <td>Session Layer</td>
        </tr>
        <tr>
            <td>Transportschicht</td>
            <td>Transport Layer</td>
            <td>TCP / UDP</td>
        </tr>
        <tr>
            <td>Vermittlungsschicht</td>
            <td>Network Layer</td>
            <td>IPv4 / IPv6</td>
        </tr>
        <tr>
            <td>Sicherungsschicht</td>
            <td>Data Link Layer</td>
            <td>UEEE 802.3 (Ethernet)</td>
        </tr>
        <tr>
            <td>Physikalische Schicht</td>
            <td>Physical Layer</td>
        </tr>
    </table></br>
</details>

KAP 1 - Physikalische Schicht
=====
### Signale, Informationen und deren Bedeutung
#### Information und Entropie

***
<details>
    <summary>Signale, Symbole</summary>
    Signal: zeitabhängige, messbare physikalische Größe. </br>
    Symbol: Definierte, messbare Signaländerung</br>
</details>

<details>
    <summary>Informationstheorie nach Shannon, Informationsgehalt</summary>
    Der Informationsgehalt eines Zeichens drückt aus, wieviel Information durch das Zeichen übertragen wird.
</details>

<details>
    <summary>Informationstheoretisches Modell eines gedächtnislosen Kanals (zeichnen)</summary>
    siehe Skript
</details>

<details>
    <summary>Empfangsentropie</summary>
    ist die Sendeentropie abzüglich eines Informationsverlusts durch den Kanal zuzüglich der Fehlinformation 
</details>

<details>
    <summary>Transinformation</summary>
    ist die Sendeentropie abzüglich des Informationsverlusts bzw. Empfangsentropie abzüglich der Fehlinformation </br>
    Mutual Information, die von Sender zu Empfänger über einen gedächtnislosen Kanal transportiert wird. 
</details>

Je seltener ein Zeichen auftritt, desto höher sein Informationsgehalt.
Der Informationsgehalt eines vorhersagbaren Zeichens ist 0.

*Informationsgehalt* $I$ des Zeichens $x$ mit der Aufenthaltswahrscheinlichkeit $p(x)$ (Einheit: bit)

*Entropie* ist der mittlere Informationsgehalt einer Quelle.

*Bedingte Entropie* zweier Zufallsvariablen $X$ und $Y$ entspricht der verbleibenden Unsicherheit über $Y$, wenn $X$ bekannt ist.

#### Neue Begriffe:

Zeitdiskretisierung, Abtasttheorem, Quantisierung, 

Leitungskodierung (Abbildungs-/Interpretationsvorschrift), 

Rauschen, Dämpfung, Verzerrung (Störfaktoren), 

Kanalkodierung (Fehlererkennung/-korrektur), 

Impulsformung, Modulation (Erzeugung eines Signals)

### Signaldarstellung
***
#### Fourierreihe

Überlagerung von sin-/ cos-Schwingungen unterschiedlicher Frequenzen = Periodische Zeitsignale

#### Einfache Signaleigenschaften

#### Fouriertransformation


### Abtastung, Rekonstruktion und Quantisierung
***
<details>
    <summary> Zeitdiskretisierung von Signalen </summary>
    Abtastung
</details>

<details>
    <summary> Abtasttheorem von Shannon und Nyquist </summary>
    Ein auf B bandbegrenztes Signal muss mind. mit der Frequenz 2B abgetastet werden, um das Signal verlustfrei rekonstruieren zu können, d.h. damit keine Information verloren geht. 
</details>

<details>
    <summary> Wertdiskretisierung von Signalen </summary>
    Quantisierung
</details>

Natürlich vorkommende Signale sind i.d.R. zeit- und wertkontinuierlich

Es ist also eine Zeit- und Wertdiskretisierung notwendig

Abtastwerte sind Stützstellen als Gewichte für eine passende Ansatzfunktion (Interpolation).

Aliasing: Überlapping der periodischen Wiederholungen des Spektrums. Verlustfreie Rekonstruktion ist nicht mehr möglich. 

Codierung der unterschiedlichen Signalstufen. Jeder Signalstufe wird dabei ein bestimmtes Codewort zugeordnet. Verteilung der Signalstufen im Quantisierungsintervall. 

## Übertragungskanal

### Kanaleinflüsse
***
<details>
    <summary> Dämpfung </summary>
    Geringere Signalamplitude beim Ausgang als am Eingang
</details>

<details>
    <summary> Tiefpassfilterung </summary>
    Höhere Frequenzen werden stärker gedämpft als niedrigere
</details>

Modell mit **Dämpfung** (geringere Signalamplitude beim Ausgang als am Eingang), Tiefpassfilterung (höhere Frequenzen werden stärker gedämpft, als niedrige), Verzögerung (Übertragung benötigt eine gewisse Zeit), Rauschen in Form von Additive White Gaussian Noise. 

Ein Kanal wirkt wie ein **Tiefpass** (Tiefpasscharakteristik) und zusätzliches Rauschen stört die Übertragung. Niedrige Frequenzen passieren ungehindert (Tiefpass), hohe Frequenzen werden gedämpft, Vernachlässigung von Signalanteilen ab einer bestimmten Frequenz (weil die Dämpfung zu stark ist)

### Kanalkapazität
***
<details>
    <summary> Wovon ist die erzielbaren Datenrate auf einem Kanal mit beigegebener Bandbreite abhängig? </summary>
    Benötigt: Zusammenhang zwischen Bandbreite, Anzahl unterschiedlicher Signalstufen, Verhältnis zwischen Leistung des Nutzsignals und des Rauschens. 
</details>

<details>
    <summary> Was ist die Nyquist-Rate? </summary>
    $f_N = 2B$
    Eine untere Schranke für die minimale Abtastrate (Abtasttheorem), obere Schranke für die Anzahl an Symbolen je Zeiteinheit, die nach der übertragung über den Kanal unterscheidbar sind.
</details>

<details>
    <summary> Was besagt Hartleys Gesetz? </summary>
    Obere Schranke für die Kanalkapazität durch gegebene Bandbreite $B$ mit $M$ unterscheidbaren Signalstufen. 
</details>

Rauschen erschwert die Unterscheidung von Signalstufen mit steigender Feinheit der Signalstufen. 

<details>
    <summary> Gib das Mass für die Stärke des Rauschens an!</summary>
    Signal to Noise Ratio in Dezibel!
</details>



### Nachrichtenübertragung

### Übertragungsmedien