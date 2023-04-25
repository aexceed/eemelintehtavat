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

Yritys part 2

Ympäristö oli jotenkin hajonnut joten tein uudestaan kaiken tähän pisteeseen saakka. Sls tiedostoonkin löytyi syntaxi kuntoon tiedostosijaintien suhteen, aikaisemmin olin yrittänyt siirtää koko kansiota sls tiedostossa mutta kun muutin yksittäisiksi tiedostoiksi nii rupesikin hommat pelittämään.

![image](https://user-images.githubusercontent.com/129611461/234329607-899a9342-2add-4ce4-b219-3ec6ecdb406c.png)

Ja sitten syötetään state.apply avulla orjille.

![image](https://user-images.githubusercontent.com/129611461/234329508-f3afdf9f-6e9e-4d2b-a6b2-178bfee91b9e.png)

Kokeillaan ajaa tmasterilta cmd.run komennolla.

![image](https://user-images.githubusercontent.com/129611461/234334879-0b8b59f4-6424-4cd2-a65f-d4e9f248bffd.png)

Se onnistui ja sitten python scripti.

![image](https://user-images.githubusercontent.com/129611461/234338312-5ae88d3a-a0cd-4245-986c-4e4313ea1f96.png)

Onnistui, ei onnistunut? Miten sen nyt ottaa en ihan ymmärtänyt virhetulostusta. Syntax erroria ei kyllä scriptistä löydy sen verran pythoni taittuu. Netti osasi kertoa että voi johtua jotenkin jostain pythonin versioista ja siihen liittyen? 

# d)

Tein /srv/salt/ uuden kansion nimeltä asenna ja sinne tälläisen sls tiedoston.

![image](https://user-images.githubusercontent.com/129611461/233990240-db97d9cf-f450-4c67-8bf1-e304f9690557.png)

Ajoin tilan ei toiminut.

![image](https://user-images.githubusercontent.com/129611461/233990355-e0e31933-b931-4e6a-bca2-46b4d875151f.png)

Part 2:

Latasin micron komennolla sudo apt install micro.

![image](https://user-images.githubusercontent.com/129611461/234343058-b97e2111-71e9-4f61-80d0-8f574471406d.png)

Kysyin whereis micro komennolla missä se on ja siirsin sen cp komennolla /srv/salt/hello/ kansioon.

![image](https://user-images.githubusercontent.com/129611461/234343316-81ef1b0a-1eb8-4868-b2c9-60e527101b28.png)

Muokkasin sls tiedostoa lisäämällä sinne micron.

![image](https://user-images.githubusercontent.com/129611461/234343745-99fb47f8-892d-4cba-868f-20eb2ec31ed1.png)

Puskin sen orjille.

![image](https://user-images.githubusercontent.com/129611461/234343639-ca792d42-d08d-434e-9f66-73eef68ee8ec.png)

Yhdistin seuraavaksi orjalle t001 katsomaan toimiiko micro. Heti alussa kirjoitamalla ei toimi micro joten katsotaan onko se edes koneella. whereis micro osaa kertoa että kyllä on. Menen kansioon missä se on ja yritän uudestaan ei mitään mutta ./micro komennolla se aukeaa? Mielenkiintoista en tiedä mistä johtuu.

![image](https://user-images.githubusercontent.com/129611461/234344893-3167aab8-a5fc-4959-be98-ab0cc5c5ed0b.png)

![image](https://user-images.githubusercontent.com/129611461/234344524-010f0693-4566-4284-ae14-5b0af20cbe5e.png)


# Lähteet:

https://docs.saltproject.io/en/latest/ref/states/all/salt.states.cmd.html

https://terokarvinen.com/2023/palvelinten-hallinta-2023-kevat/

https://terokarvinen.com/2018/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=salt%20ssh

https://stackoverflow.com/questions/57891578/how-to-pass-multiple-commands-into-salt-cmd-run

