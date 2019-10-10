# Gestures

Jeg har valgt at arbjede med gestures gennem mouse x/y, som skal skrifte farven i "TriggerText". TriggerText er derfor mit output. Jeg gør brug af 3 gesures, som skrifter farven til henholdsvis blå, rød og gul. 

For at få disse to til at spille sammen med gestures, har jeg ændret lidt i TriggerText:

```
void oscEvent(OscMessage theOscMessage) {
 println("received message");
    if (theOscMessage.checkAddrPattern("/blue")) {
      currentHue = 150;
    } else if (theOscMessage.checkAddrPattern("/red")) {
      currentHue = 0;
    } else if (theOscMessage.checkAddrPattern("/yellow")) {
      currentHue = 40;
    }
}
```
CurrentHue er den variabel der styre farvekoden. Når theOscMessage.checkAddrPattern passer med det tag der er sat på inputtet, så skiftes currentHue til den værdi der passer til det tag.