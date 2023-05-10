# h6 puolikas

Koneen tiedot:

Windows 11 Home

Prossu: i7-1165G7 @ 2.80GHz

Näyttis: Intel Iris Xe integroitu

RAM: 16 gt

# Puolikas

Ensimmäisenä ideana tuli mieleen komentaa montaa eri käyttöjärjestelmää ja sitä lähdetään työstämään. Aikaisemmassa tehtävässä h5 yhteys ei toiminut oikein windowsiin mutta ehkäpä tällä kertaa sekin saadaan korjattua. Ensin tutkitaan nettiä mitenkä tämä käytännössä toimii ja vagrantfilen kirjoittelua sekä riittääkö oma osaaminen.

Alkuun olisi tavoitteena että masteri on ubuntu joka hallitsee centos, debian ja ubuntu koneita. Muuttelin vähän vagrantfileä ja koitin käynnistellä mutta eipä oikein tykännyt.

![image](https://user-images.githubusercontent.com/129611461/236854571-5fbc023d-3a90-4402-9b6f-8546b1c3649e.png)

Palataan takas perusteisiin elikkä yksi kerrallaan. Vagrantfilestä kommentoin pois kaiken paitsi yhden koneen ja aloitetaan debianista mikä on saatu joskus toimimaan. Laiskana ihmisenähän teen tämän samaan saltdemo kansioon kuin kurssilla tarvitut master + 2 orjaa on tehty.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/33950e9b-12f5-4076-adab-2ab8a452e495)

Tälläisessä muodossa lähdetään testaamaan, Vagrant configure kohdassa päädyin takaisin kurssilla käytettyyn "2" kohtaan joka tuntui ratkaisevalta ominaisuudelta tässä koska sen vaihdettuani takaisin rupesikin yksi kone käynnistymään.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/4a5f7cd9-3910-409f-a753-e40306a8c1ed)

Debian siis onnistui, ei nyt tullut ensimmäisenä kokeillusta vagrantfilestä otettua kuvaa mutta muutama rivi oli väärällä paikalla ja väärinpäin, ne muutettua rupesi toimimaan. Rivit jotka olivat väärinpäin oli config.vm.box ja config.vm.define. Seuraavaksi kokeillaan lisätä toiseksi tutuin käyttis eli ubuntu, muutin rakenteen myös samaan muotoon ja ./vagrant up komentoa kokeilemaan.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/3c56d450-b539-4bca-838c-468ebf638f70)

Ubuntukin lähti toimimaan debianin rinnalla, kummatkin siis minioneina vielä. SSH yhteys tuli testattua samassa ja pääsin ubuntu koneelle sisään. Sitten on aika repäistä kun kerran näin hyvin lähti rullaamaan, otetaan tuntematon centOS vielä minioniksi ja koitetaan samalla laittaa masteri ubuntu päälle.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/cc803fd7-1184-4e04-b105-15d5e8acc6ba)

Alku on lupaava:

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/3989a0e2-8cb4-4d87-bc69-a5b4382ca2ad)

Koneet käynnistyivät, kirjaudutaan emasterille ./vagrant ssh emaster. Koneelle päästy sisään, katsotaan onko siellä avaimia hyväksyttävänä ja hyväksytään jos on.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/b279886c-51e3-4750-ac81-d605b45801ff)

Olen ehkä itsekkin hieman yllättynyt että siellä oli ja ne hyväksyivät sekä test.ping toimi.

Valmius: Alpha

# Lähteet:

https://terokarvinen.com/2023/palvelinten-hallinta-2023-kevat/

https://stackoverflow.com/questions/60940227/two-operating-systems-in-a-single-vagrantfile
