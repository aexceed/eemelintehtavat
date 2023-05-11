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

Debian siis onnistui, ei nyt tullut ensimmäisenä kokeillusta vagrantfilestä otettua kuvaa mutta muutama rivi oli väärällä paikalla ja väärinpäin, ne muutettua rupesi toimimaan. Rivit jotka olivat väärinpäin oli config.vm.box ja config.vm.define. Seuraavaksi kokeillaan lisätä toiseksi tutuin käyttöjärjestelmä eli ubuntu, muutin rakenteen myös samaan muotoon ja ./vagrant up komentoa kokeilemaan.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/3c56d450-b539-4bca-838c-468ebf638f70)

Ubuntukin lähti toimimaan debianin rinnalla, kummatkin siis minioneina vielä. SSH yhteys tuli testattua samassa ja pääsin ubuntu koneelle sisään. Sitten on aika repäistä kun kerran näin hyvin lähti rullaamaan, otetaan tuntematon centOS vielä minioniksi ja koitetaan samalla laittaa masteri ubuntu päälle.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/cc803fd7-1184-4e04-b105-15d5e8acc6ba)

Alku on lupaava:

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/3989a0e2-8cb4-4d87-bc69-a5b4382ca2ad)

Koneet käynnistyivät, kirjaudutaan emasterille ./vagrant ssh emaster. Koneelle päästy sisään, katsotaan onko siellä avaimia hyväksyttävänä ja hyväksytään jos on.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/b279886c-51e3-4750-ac81-d605b45801ff)

Olen ehkä itsekkin hieman yllättynyt että avaimet löytyivät, hyväksyin ne ja testasin yhteyttä test.ping mikä osoittautui onnistuneeksi. Seuraavaksi yritetään lisätä vielä jotain haastavampaa ja kokeillaan jos saisi Windowsin ja Windows serverin lisättyä. Ubuntu serverinkin voi poimia matkalla mukaan jos löytyy. 

Netistä löytyi tietenkin hyvä syntaxi sivu itse vagrantilta (kuka olisi uskonut) mistä saa nämä käyttöjärjestelmien ns. "nimet". Sieltä mukaan sain kaikki kolme ja lisäsin ne vagrantfileen.

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/fef442d2-13c7-49ad-bd46-3d67a858b456)

Seuraavaksi käynnistellään taas ./vagrant up komennolla. Ensimmäisellä kerralla vähän yskii eilisen onnistuiden koneiden käynnistämiset. Koneet käynnistyvät yksi kerrallaan ja antaa timeouttia aina uuden kohdalla. Voi olla että tässä kohtaa läppärin tehot ja muisti ovat aika koetuksella jo. Ihan mielenkiintoista mitenkä se hakee netistä näitä käyttöjärjestelmiä jotka ovat muiden kuin itse niiden tekijöiden niin sanotussa jaossa. 

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/1d65e627-5d59-4a52-b485-ba07881139ca)

Ubuntu serveri löytyi ja asentui mutta windows serverin kohdalla lakkaa toimimasta. Seuraavanlaista erroria pukkaa:

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/17e39000-6ec2-4aec-aca0-4e23a31494fc)

Hetken mietittyäni tajuan että vagrantfilen alussa annetut komennothan ovat vain toimia linux pohjaisilla käyttöjärjestelmillä ja tarvitsisin omanlaisen windows koneille. Ajan sen vielä uudestaan ja nyt se ottaa Windows 10 mukaan kanssa mutta siinä tuleekin toinen virhe ilmoitus ja kone timeouttaa hetken ajan odotettuaan vastausta seuraavaan kohtaan:

![image](https://github.com/aexceed/eemelintehtavat/assets/129611461/91bdb5f7-ba1d-4843-ac01-bd1c44eab67a)

Sitten vaan googlamaaan virhettä.
Valmius: Alpha

# Lähteet:

https://terokarvinen.com/2023/palvelinten-hallinta-2023-kevat/

https://stackoverflow.com/questions/60940227/two-operating-systems-in-a-single-vagrantfile

https://app.vagrantup.com/boxes/search
