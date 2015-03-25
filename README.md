Kantinens infoskærmssystem.

infoscreen.py kører i en tmux på infoskærmsmaskinen.

Opsætning
---------

Infoskærmsmaskinen (herefter bare kaldet `odroid`) er en Odroid som er
monteret bag skærmen i kantinen.  Man kan logge ind på maskinen via
SSH ved først at forbinde til kantine.diku.dk, og derefter videre til
odroid med bruger `odroid` og løsen `odroid`.

Når maskinen starter op kører den lightdm, som automatisk logger
brugeren `odroid` ind i en session, der kører scriptet `.xinitrc`.
Vi har vedhæftet vores `.xinitrc` i dette repo.

Dette scripts primære ansvar er at starte en `tmux`-session der kører
infoskærmsscriptet, samt starte en enkelt window manager.

Disse dele er pt. ikke i Git, så lad være med at slette dem med mindre
du ved hvordan man erstatter dem.

`odroid` er en rimeligt hurtig maskine, *bortset* fra dens faste
lager, som er verdens mest langso^Wgrundige Micro-SD-kort.  Hvis det
virker som om den hænger, så er det sandsynligvis bare fordi den læser
fra disken.

Sådan gør man manuelt
---------------------

Grundet vor sofistikerede og fremskredne teknologi er det ikke enkelt
at starte infoskærmen.  Her er den nutids-kompatible procedure:

  0) Log ind på odroid-maskinen med odroid-brugeren.

  1) Start en tmux.

  2) Gå ind i `infoscreen`-mappen.

  3) Kør: export DISPLAY=:0

  4) Kør: dbus-launch ./infoscreen.py

  5) Vent til maskinen crasher, gå derefter til 0.
