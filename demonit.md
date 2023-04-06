# h2 Demonit
Aloitus 12.15

x)
- luo sls tiedosto
- kirjoita sisälle pätkä että se asentaa openssh ja config tiedoston
- Muuta config tiedostoa hieman
- suorita tila
- testaa toiminta

a) Käynnistin koneet ./vagrant up komennolla. Menin sshd_config tiedostoon tmasterilla ja t001 koska en ollut ihan varma kummalla ne pitäisi avata ja avasin sieltä portit 777 ja 8888.

![image](https://user-images.githubusercontent.com/129611461/230346947-518e248b-e40e-4760-a6d1-cd0fba482fd3.png)

Otin yhteyttä annetulla komennolla ja tuli outo errori. Sitten tajusin että pitää varmaan käynnistää ssh uudelleen joten käynnistin sen komennolla sudo salt 't001' service.restart ssh.

![image](https://user-images.githubusercontent.com/129611461/230347967-c5ecedd5-ac52-4240-a109-2897155784db.png)

Siinä lukee että portti auki joten oletettavasti tehty oikein.

b)Loin tmasterille sshd.sls tiedoston johon kopioin koodin sivuilta. Ajoin komennon mutta epäonnistui.
![image](https://user-images.githubusercontent.com/129611461/230353685-ef416e91-c1c4-40e9-9b46-ad8d329ac9d6.png)

13.45 tauko

15.00 jatkuu

Olin unohtanut luoda kopion sshd_config tiedostosta srv/salt kansioon joten loin sen.
![image](https://user-images.githubusercontent.com/129611461/230375256-64d07077-95ae-4cb5-af9e-fdba969ff44b.png)

Nytten se toimi.

![image](https://user-images.githubusercontent.com/129611461/230375123-36783bbb-5338-48b2-a92c-ad66a4eac336.png)

Testasin yhdistämällä t001

![image](https://user-images.githubusercontent.com/129611461/230373098-cb20fd87-2328-4c30-b198-c67ffc455c8a.png)

c)Muutin config tiedostosta portin 8888 -> 888

![image](https://user-images.githubusercontent.com/129611461/230374262-b26d18c6-b580-4ab8-a6c8-104b6aa28d1b.png)

Demoni käynnistyi uudestaan kun ajoin komennon muuttuneella config tiedostolla:

![image](https://user-images.githubusercontent.com/129611461/230374010-27468dab-b111-400d-9024-376e53238727.png)

Mikään ei muuttunut joten demoni ei käynnistä itseään uudestaan:

![image](https://user-images.githubusercontent.com/129611461/230373740-27887dda-e473-4c2e-9c40-e51083a7b825.png)

Käyttämäni lähteet:

https://terokarvinen.com/2018/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=salt%20ssh Luettu 6.4.2023

https://terokarvinen.com/2018/secrets-in-salt-pillars/?fromSearch=salt Luettu 6.4.2023
