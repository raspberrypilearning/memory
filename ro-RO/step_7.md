## Provocare: îmbunătățiți jocul

### Faceți mai multe blocuri

Vedeți alt cod care este același pentru toate cele patru butoane?

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur joc (\ (1 \) Snare Drum v) pentru (0,25) bate
    șterge (1 v) din [secvență v]
altceva
    Game Over :: custom
end

atunci când primesc [v blue]
dacă <(punctul (1 v) din [secvență v]) =[1]> apoi
    redare tambur (\ (2 \ ) Bass Drum v) pentru (0.25) bate
    șterge (1 v) din [secvența v]
altceva
    Joc peste :: personalizat
sfârșit
```

Puteți crea un alt bloc personalizat pe care toate butoanele îl pot utiliza?

### Un alt costum

Puteți vedea că jocul dvs. începe cu caracterul dvs. care arată una dintre cele patru culori și că caracterul afișează întotdeauna ultima culoare din secvență în timp ce playerul repetă secvența de culoare?

Puteți adăuga un alt costum alb simplu caracterului dvs. și adăugați un cod astfel încât personajul să afișeze acest costum la începutul jocului și în timp ce playerul repetă secvența?

![captură de ecran](images/colour-white.png)

### Nivel de dificultate

Puteți permite jucătorului să aleagă între joc în modul "ușor" (folosind doar culorile roșu și albastru) și "modul normal" (care utilizează toate cele patru culori)?

Dacă doriți, puteți adăuga chiar și un mod "dur", care face uz de un al cincilea tambur!