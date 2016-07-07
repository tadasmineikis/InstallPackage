# IntallPackage

Skriptas parengiantis aplinką 2-D galaktikų diskų evoliucijos modeliavimui.

# Naudojimas

Susikuriam katalogą, kuriame norime sukurti modeliavimo aplinką:
pvz.:
> mkdir GALEMO
> cd GALEMO

Parsisiunčiam skriptą iš GitHub

> git clone https://github.com/tadasmineikis/InstallPackage.git

Susikuriam simbolinį link'ą:

> ln -s $PWD\InstallPackage\INSTALL $PWD\INSTALL

Suteikiam execute teise failui:

> chmod +x INSTALL

Paleidžiam scriptą su kintamuoju CC, kuris nurodo kompiliatorių C++ kodo kompiliavimui, po linux tai bus g++, jei default g++ kompiliatorius nesukompiliuoja, galima nurodyti, pvz g++-4.9:

> CC=g++ ./INSTALL

Jei matome išvedimą : "Installation completed successfully!", reiškia viskas sėkmingai susikompiliavo.
Sekančios dvi eilutės nurodo iš kur galima parsisiųsti izochronų bankus m33 ir leoA pavyzdžiams:

m33 https://drive.google.com/open?id=0Bwr33zLJzGQORE9uVU5iU3RkMEk

leoA https://drive.google.com/open?id=0Bwr33zLJzGQObDl5dnJvVjJVQTA

Šiuos bankus reikia padėti į iso_bank aplanką atitinkamoje RUN direktorijoje (RUN_leoA ir RUN_m33)
