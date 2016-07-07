# IntallPackage

Skriptas parengiantis aplinką 2-D galaktikų diskų evoliucijos modeliavimui Skripto veikimui reikalinga turėti instaliavu git. Po ubuntu tai galima padaryti:
> sudo apt-get install git

# Naudojimas

Susikuriam katalogą, kuriame norime sukurti modeliavimo aplinką:
pvz.:
> mkdir GALEMO

> cd GALEMO

Parsisiunčiam skriptą iš GitHub

> git clone https://github.com/tadasmineikis/InstallPackage.git

Susikuriam simbolinį link'ą:

> ln -s $PWD\InstallPackage\INSTALL $PWD\INSTALL

Suteikiam execute teises failui:

> chmod +x INSTALL

Paleidžiam scriptą su kintamuoju CC, kuris nurodo kompiliatorių C++ kodo kompiliavimui, po linux tai bus g++, jei default g++ kompiliatorius nesukompiliuoja, galima nurodyti, pvz g++-4.9 (su 'senais' kompiliatoriais neveikia, pvz g++-4.6):

> CC=g++ ./INSTALL

Jei matome išvedimą : "Installation completed successfully!", reiškia viskas sėkmingai susikompiliavo.
Sekančios dvi eilutės nurodo iš kur galima parsisiųsti izochronų bankus m33 ir leoA pavyzdžiams:

m33 https://drive.google.com/open?id=0Bwr33zLJzGQORE9uVU5iU3RkMEk

leoA https://drive.google.com/open?id=0Bwr33zLJzGQObDl5dnJvVjJVQTA

Šiuos bankus (išarchyvavus failus) reikia padėti į iso_bank aplanką atitinkamoje RUN direktorijoje (RUN_leoA ir RUN_m33). Galima izochronų bankus laikyti ir kitur, bet tuomet reikia nurodyti kelią iki jų template faile, kuris yra atitinkamose RUN direktorijose. 

# Ką daro script'as

1. Patikrina ar instaliuotas git, jei ne - instaliavimas atšaukiamas.
2. Patikrina ar visos reikalingos bibliotekos intaliavimui yra systemoje. Patikrinimui naudojamas ldconfig. 
  - Jei ldconfig sistemoje nerastas, instaliavimas tęsiamas nepatikrinus bibliotekų.
  - Jei ldconfig randamas, tačiau nerandamos bibliotekos, nurodoma kokių konrečiai bibliotekų trūksta ir instaliavimas atšaukiamas.
  - jei bibliotekų trūksta, jas galima instaliuoti taip (veikia po ubuntu):
  > sudo apt-get install libarmadillo-dev libgsl0-dev
3. Klonuojamos Galaxy, GalaxyPipeline ir GCMD repositorijos iš GitHub ir bandoma jas kompiliuoti.
4. Jei viskas sėkmingai, sukuriamos pavyzdinės direoktorijos RUN_m33 ir RUN_leoA, kuriuose sukuriami simboliniai link'ai į visus reikalingus exe failus modelio veikimui, t.y.:
  - galemo: python skriptas modeliavimui
  - galaxy_2.0 : programinis paketas atliekantis 2-D galaktikos disko modeliavimą
  - gCMD_0.21.5 : programinis paketas generuojantis sintetinius žvaigždžių katalogus
  - nukopijuojami visi reikalingi failai leoa.README ir m33.README modelių veikimui. Dėl vietos apribojimų, izochronų bankus reikia parsisiųsti atskirai ir padėti į iso_bank katalogus.
5. Pavyzdiniai modeliai skaičiuojami:
> ./galemo leoa.README 1
> ./galemo m33.README 1
  
