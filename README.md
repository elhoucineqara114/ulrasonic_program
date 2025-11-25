# 📘 TP Arduino – Capteur Ultrason + LED

## 🎯 Objectif du TP
Ce TP a pour but d’apprendre aux étudiants à :
- Utiliser un capteur ultrason **HC-SR04** pour mesurer une distance.
- Allumer une **LED** si un obstacle est détecté à moins de 50 cm.
- Comprendre la logique : **Capteur → Arduino → Actionneur**.

---

## 🧰 Matériel nécessaire
- Arduino UNO  
- Capteur ultrason **HC-SR04**  
- LED  
- Résistance 220 Ω  
- Breadboard  
- Fils de connexion  

---

## 🔌 Schéma de connexion

### HC-SR04 → Arduino
| HC-SR04 | Arduino |
|---------|---------|
| VCC     | 5V      |
| GND     | GND     |
| TRIG    | Pin 9   |
| ECHO    | Pin 10  |

### LED → Arduino
- Anode (patte longue) → **Pin 13**  
- Cathode (courte) → **Résistance 220 Ω** → **GND**

---

## 📝 Principe de fonctionnement
1. Arduino envoie une impulsion de **10 µs** au pin TRIG.  
2. Le capteur envoie une onde ultrasonique.  
3. Cette onde rebondit sur un obstacle et revient.  
4. Le pin ECHO indique la durée du trajet.  
5. Distance calculée :

\[
\text{distance} = \frac{\text{durée (µs)} \times 0.0343}{2}
\]

- 0.0343 = vitesse du son convertie en **cm/µs**  
- Division par 2 = aller + retour  

6. Si la distance < 50 cm → **LED ON**, sinon **LED OFF**.
