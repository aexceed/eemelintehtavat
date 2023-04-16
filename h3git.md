# h3 git


Koneen tiedot:

Windows 11 Home

Prossu: i7-1165G7 @ 2.80GHz

Näyttis: Intel Iris Xe integroitu

RAM: 16 gt

Aloitus 20.50

a) Klikkasin githubiani kirjanmerkkki palkista. Se vei minut tehtävä varastooni josta painoin omaa nimeäni. Valitsin tällä sivulla repositories.
![image](https://user-images.githubusercontent.com/129611461/232245825-7640d926-58e7-4433-b6b0-b7f59063a7e3.png)
Painoin New kohtaa josta pääsin luonti sivulle. 
![image](https://user-images.githubusercontent.com/129611461/232247990-ce3c799f-d8b8-41b2-8894-a1778f828db5.png)
Täytin luontisivun haluamillani asetuksilla joihin kuuluu summer sana repossa, README.md tiedosto sekä GNU 3.0 lisenssi.
![image](https://user-images.githubusercontent.com/129611461/232245914-ba044f1c-8d62-4db2-a4cf-e4c609592e96.png)
![image](https://user-images.githubusercontent.com/129611461/232245936-236748dc-ef34-495c-bdf0-6de1e78fe4af.png)
Tässä lopputulos:
![image](https://user-images.githubusercontent.com/129611461/232246053-a4145454-0e04-4b1c-a6d0-20b2436d34b7.png)

b) Teen tehtävän virtuaalikoneella jossa on ubuntu. Avasin summer-repon, painoin code kohdasta -> SSH ja kirjoitin osoitteen virtuaalikoneen terminaaliin git clone komennon perään koska kopioiminen ei onnistunu jostain syystä koneiden välillä vaikka se on kytketty ja virtuaalikoneella kun menee sivulle niin koko code kohtaa ei ollut edes näkyvissä.
![image](https://user-images.githubusercontent.com/129611461/232246873-58b68455-c027-405a-b32b-765df9d1e8d6.png)
Repo on kloonattu testataan että toimii.
![image](https://user-images.githubusercontent.com/129611461/232246934-5f3b34a1-1b0b-4b25-94bb-b7b31ad20961.png)
Siellä on.
Menin kansioon sisään ja avasin nanolla README.md tiedoston. Kirjoitin sinne Tämä on MUUTOS ja tallensin.
![image](https://user-images.githubusercontent.com/129611461/232247108-32e7285a-98ef-4939-af25-e6fcfe8f3cf3.png)
Seuraavaksi haluan puskea muutoksen gittiin. Kirjoitin git add . ja git commit.
![image](https://user-images.githubusercontent.com/129611461/232247374-9d61ac97-5fb6-4989-bf71-50cd20a65c8e.png)
Samalla tuli tehtyä hieman d) kohtaa kun se halusi tietää kuka olen ja laitoin tiedot sinne.
git commit uudestaan ja kirjoitin samalla muutos logiin mitä tein. git pull ja git push ja sinne meni päivitys.
![image](https://user-images.githubusercontent.com/129611461/232247465-5a21810e-3eae-4a0b-b92f-fcf309c28406.png)
Menin githubiin repon sivulle ja heti näkyi että joku on muuttanut jotain 5 min sitten kommentin kera
![image](https://user-images.githubusercontent.com/129611461/232247540-eb27426f-99ed-4b42-a81b-1f2be12ef90d.png)
Itse sivulla näytti tältä
![image](https://user-images.githubusercontent.com/129611461/232247565-ef8ac794-e0aa-4f50-a902-e939a7f4a81e.png)

c)Tyhmä muutos gittiin: sovitaan vaikka että kissa hyppäsi vahingossa näppikselle kun oli README.md tiedosto auki ja meni vieläpä tallentamaan sen.
![image](https://user-images.githubusercontent.com/129611461/232247658-62288629-b270-427e-b4dc-3a298d49055e.png)
Kirjoitin komennoksi git reset --hard ja tapahtui näin.
![image](https://user-images.githubusercontent.com/129611461/232247693-f0792998-2664-4f0a-a9bd-ef8ddb42d6b1.png)
Avaan README.md tiedoston uudestaan:
![image](https://user-images.githubusercontent.com/129611461/232247716-db72e7ed-841d-4409-ba71-5f9ddbb4aa0f.png)
Kaikki mitä kissani meni äsken vahingossa tallentamaan on poissa.

d) Tutkitaan logia kirjoittamalla git log --patch
![image](https://user-images.githubusercontent.com/129611461/232247787-0634ee87-e18b-492e-8425-14dc869a44f7.png)
Näkyy toimivan alhaalta ylöspäin eli heti alhaalla on kun loin repon tällä windowsilla ja tunnukset eivät ole selvästikkään kunnossa kun on noin epämääräinen sähköposti. Seuraavaksi näkyy eemeli virtuaalikoneella muutokset jossa taas on kunnossa authorin nimi ja sähköposti koska laitoin ne. Muutoksissa näkyy että lisäsin tekstiä README.md tiedostoon. Muutoksissa ei näy sitä kuinka kissa hyppäsi näppikselle ja tallensi muutokset jotka ehdin poistaa reset komennolla.

Lopetus 22.00

Lähteet:
https://terokarvinen.com/2023/palvelinten-hallinta-2023-kevat/ Luettu 15.4.2023
