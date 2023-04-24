# h4 komennus

Koneen tiedot:

Windows 11 Home

Prossu: i7-1165G7 @ 2.80GHz

Näyttis: Intel Iris Xe integroitu

RAM: 16 gt

Aloitus klo 18.20

# a)

Etsin kansion missä koneeni olivat piilossa ja oikeata hiiren puolta klikkaamalla otin powershellin auki kyseisessä kansiossa. Komennot ./vagrant up ja sen jälkeen ./vagrant ssh tmaster että pääsen sisään. tmaster koneella menin /srv/salt/ kansioon, tein hello kansion sinne ja kirjoitin nanolla hello.sh scriptin.

![image](https://user-images.githubusercontent.com/129611461/233856255-cace1baa-9c1d-4068-82b0-e169fdfc3a08.png)

Testataan että toimii ensin yhdellä koneella:

![image](https://user-images.githubusercontent.com/129611461/233856336-72452cfc-042d-457c-be1e-5ffe81601a0a.png)


# b)
Tein hello.py nimisen python scriptin jota käytetään kirjoittamalla python3 hello.py ja se sanoo tälläistä:

![image](https://user-images.githubusercontent.com/129611461/233852618-e4f663f8-5c20-4689-9691-6909752acc81.png)

Tiedoston sisälle on siis kirjoitettu vain print("Shining some more light here"). Samalla tuli testattua että se toimii yhdellä koneella.

Seuraavaksi laitoin kummatkin scriptit hello kansioon /srv/salt/ paikassa jotta ne olisivat orjien saavutettavissa.

![image](https://user-images.githubusercontent.com/129611461/233984138-51722968-a3c0-4982-bcfb-2e5e927a985b.png)

Vaihdoin oikeudet että niitä voi varmasti ajaa komennolla sudo chmod 755 *tiedostojen nimi*.

# c)

Automatisoin näiden asennuksen orjille kait? Tässä kohtaa ei enään ihan ajatus toiminut että mitenkä tämä pitäisi tehdä. Eli loin init.sls tiedoston tämän näköisenä:

![image](https://user-images.githubusercontent.com/129611461/233985131-8ec38dd8-5a8b-4220-8d3b-094a49a54c34.png)

Lopetus 21.00 ja jatkuu seuraavan päivänä 14.10

Kopioin ne vielä varmuudeksi orjille ja siellä ne ilmeisesti olivat.

![image](https://user-images.githubusercontent.com/129611461/233856610-92cde6bf-9d53-46aa-9dce-fac4190b70ac.png)

Koitin ajella tiedostoja en tiedä miksi, kuuluiko se edes tehtävän antoon mutta oikeudet ei riittäneet vaikka ne oli vaihdettu.

![image](https://user-images.githubusercontent.com/129611461/233985720-05db6d21-0f44-4dac-be47-99a94a70b2b5.png)

# d)

Tein /srv/salt/ uuden kansion nimeltä asenna ja sinne tälläisen sls tiedoston.

![image](https://user-images.githubusercontent.com/129611461/233990240-db97d9cf-f450-4c67-8bf1-e304f9690557.png)

Ajoin tilan ei toiminut.

![image](https://user-images.githubusercontent.com/129611461/233990355-e0e31933-b931-4e6a-bca2-46b4d875151f.png)

TLDR:
En tiedä en ymmärrä loppui motivaatio. Lopetan oman hyvinvointini vuoksi tähän tämän viikon tehtävät. Illalla oman luetun ymmärtämisen virheen takia koitin ajaa scriptejä ja etsin 2 tuntia miksi en saa niitä ajettua vaikka eihän niitä edes tarvinnut. VItutus huipussa ei pysty pitää tehdä muitakin kursseja välillä.


# Lähteet:

https://docs.saltproject.io/en/latest/ref/states/all/salt.states.cmd.html

https://terokarvinen.com/2023/palvelinten-hallinta-2023-kevat/

https://terokarvinen.com/2018/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=salt%20ssh

https://stackoverflow.com/questions/57891578/how-to-pass-multiple-commands-into-salt-cmd-run

