# GRNVS

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

## KAP 1 - Physikalische Schicht

### Signale, Informationen und deren Bedeutung
#### Information und Entropie

<details>
    <summary>Signale, Symbole</summary>
    Signal: zeitabhängige, messbare physikalische Größe. </br>
    Symbol: Definierte, messbare Signaländerung</br>
</details>

<details>
    <summary>Informationstheorie nach Shannon, Informationsgehalt</summary>
    Der Informationsgehalt eines Zeichens drückt aus, wieviel Information durch das Zeichen übertragen wird.
</details>

Je seltener ein Zeichen auftritt, desto höher sein Informationsgehalt.
Der Informationsgehalt eines vorhersagbaren Zeichens ist 0.

*Informationsgehalt* I des Zeichens x mit der Aufenthaltswahrscheinlichkeit p(x) (Einheit: bit)

*Entropie* ist der mittlere Informationsgehalt einer Quelle.

*Bedingte Entropie* zweier Zufallsvariablen X und Y entspricht der verbleibenden Unsicherheit über Y, wenn X bekannt ist.

<details>
    <summary>Informationstheoretisches Modell eines gedächtnislosen Kanals (zeichnen)</summary>
    siehe Skript
</details>
Empfangsentropie = Sendeentropie abzüglich eines Informationsverlusts durch den Kanal zuzüglich der Fehlinformation 

Transinformation = Sendeentropie abzüglich des Informationsverlusts bzw. Empfangsentropie abzüglich der Fehlinformation

<details>
    <summary> Transinformation </summary>
    Mutual Information, die von Sender zu Empfänger über einen gedächtnislosen Kanal transportiert wird. 
</details>

#### Neue Begriffe:
Zeitdiskretisierung, Abtasttheorem, Quantisierung, 

Leitungskodierung (Abbildungs-/Interpretationsvorschrift), 

Rauschen, Dämpfung, Verzerrung (Störfaktoren), 

Kanalkodierung (Fehlererkennung/-korrektur), 

Impulsformung, Modulation (Erzeugung eines Signals)

### Signaldarstellung
#### Fourierreihe
Überlagerung von sin-/ cos-Schwingungen unterschiedlicher Frequenzen = Periodische Zeitsignale
#### Einfache Signaleigenschaften

#### Fouriertransformation


### Abtastung, Rekonstruktion und Quantisierung
Natürlich vorkommende Signale sind i.d.R. zeit- und wertkontinuierlich

Es ist also eine Zeit- und Wertdiskretisierung notwendig

<details>
    <summary> Zeitdiskretisierung von Signalen </summary>
    Abtastung
</details>
Abtastwerte sind Stützstellen als Gewichte für eine passende Ansatzfunktion (Interpolation).

<details>
    <summary> Abtasttheorem von Shannon und Nyquist </summary>
    Ein auf B bandbegrenztes Signal muss mind. mit der Frequenz 2B abgetastet werden, um das Signal verlustfrei rekonstruieren zu können, d.h. damit keine Information verloren geht. 
</details>
Aliasing: Überlapping der periodischen Wiederholungen des Spektrums. Verlustfreie Rekonstruktion ist nicht mehr möglich. 

<details>
    <summary> Wertdiskretisierung von Signalen </summary>
    Quantisierung
</details>
Codierung der unterschiedlichen Signalstufen. Jeder Signalstufe wird dabei ein bestimmtes Codewort zugeordnet. Verteilung der Signalstufen im Quantisierungsintervall. 

## Übertragungskanal
### Kanaleinflüsse
Modell mit Dämpfung (geringere Signalamplitude beim Ausgang als am Eingang), Tiefpassfilterung (höhere Frequenzen werden stärker gedämpft, als niedrige), Verzögerung (Übertragung benötigt eine gewisse Zeit), Rauschen in Form von Additive White Gaussian Noise. 

Ein Kanal wirkt wie ein Tiefpass (Tiefpasscharakteristik) und zusätzliches Rauschen stört die Übertragung. Niedrige Frequenzen passieren ungehindert (Tiefpass), Dämpfung hoher Frequenzen, Vernachlässigung von Signalanteilen ab einer bestimmten Frequenz (weil die Dämpfung zu stark ist)

### Nachrichtenübertragung

### Übertragungsmedien