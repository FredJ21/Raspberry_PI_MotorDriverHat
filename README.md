# Raspberry PI - Motor Driver Hat

| <a href="photos/FJ1_9877.jpg"><img src="photos/FJ1_9877.jpg" width="350"></a>|<a href="photos/FJ1_9879.jpg"><img src="photos/FJ1_9879.jpg" width="350"></a>|
|-----|-----|

### Présentation

La carte "Motor Driver" est une carte d'extention pour Rasberry PI 3 ou 4, permettant de piloter 2 moteurs à courant continue de forte puissance (* voir plus bas), des servos moteurs, et d'autres periphériques via les Gpio.    

Elle propose une connectivité pour les besoins en alimentation électrique et pour le raccordement des moteurs, ainsi que de mulitples entrées/sorties GPIO, facilitant, par exemple, l'utilisation de servos moteurs.   


***Principales caracteristiques*** :

- entrée d'alimentation 5V pour la Raspberry
- entrée d'alimentation 5 à 7V pour les servos moteurs
- entrée d'aliementaion 6 à 27V pour les moteurs
- 2 ponts en H composés de 4 BTS7960 (43 Ampères)
- Led de controle du sens de rotation
- 6 entrées/sorties GPIO PWM avec alimentation servos moteurs
- 4 entrées/sorties GPIO+Gnd (accessoires) + Led  
- 2 sorties de amplifiées via MOSFET
- connecteur I2C
- buzzer (bip bip)
- bouton poussoir


***Les atouts*** notables de cette carte sont donc : la séparation des alimentations RPI/Motor/Servos et l'intégration de deux ponts en H puissant sur une surface réduite.


***Important*** : même si les BTS7960, des deux ponts en H, supportent un courrant de plus de 40 ampères , il n'est pas envisagable d'utiliser la carte "Motor Driver" à une telle intensité de courrant.

La limite de courrant admissible est principalement dû à la taille et l'épaisseur des pistes de cuivre du PCB , ainsi qu'à l'absence dissipateur thermique sur les composants actif.  

**TODO**: il est necessaire de réaliser encore quelques tests pour déterminer les limites d'utilisation   

### Repérage des points de raccordement

![schema](schemas/RPI_MotorDriverHat.png)

### Exemple d'utilisation

Cette exemple utilise deux regulateurs DC/DC de type "UBEC"
* 5V pour la Rasberry
* 5V (ou lègèrement plus) pour les sorties PWM des servos moteurs

La batterie est également raccordée directement à la carte pour alimenter les moteurs au travers des deux ponts en H.

![exemple](schemas/RPI_MotorDriverHat_Exemple.png)

---
### H Bridge BTS7960 - IBT_2

La carte RPI "Motor Driver" reprend l'architecture du module **Arduino IBT_2**. Elle est l'équivalent à 2 ponts en H IBT_2 qui permettent à la Raspberry de piloter 2 ou 4 moteurs à l'aide de signaux PWM.  

|<a href="img/IBT_2.png"><img src="img/IBT_2.png" width="250"></a>|<ul><li>Input Voltage: 6 ~ 27Vdc.</li><li>Driver: Dual BTS7960 H Bridge Configuration.</li><li>Peak current: 43-Amp.</li><li>PWM capability of up to 25 kHz.</li><li>Control Input Level: 3.3~5V.</li><li>Control Mode: PWM or level</li><li>Over-voltage Lock Out.</li><li>Working Duty Cycle: 0 ~100%.</li><li>Under-voltage Shut Down.</li></ul>|<a href="schemas/RPI_and_IBT_2.png"><img src="schemas/RPI_and_IBT_2.png" width="350"></a>
|-|-|-|


---
### Schematic Diagram

![Schematic Diagram](schemas/Schematic.png)


### PCB

![exemple](schemas/PCB.png)


### Authors
Frederic JELMONI

### MIT License
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

### Copyright
Copyright (c) 2021 Frederic JELMONI
