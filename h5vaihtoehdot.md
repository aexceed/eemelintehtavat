# h5 vaihtoehdot

Koneen tiedot:

Windows 11 Home

Prossu: i7-1165G7 @ 2.80GHz

Näyttis: Intel Iris Xe integroitu

RAM: 16 gt

Aloitus 14.20

# x)

Control windows with salt:
- Aloita toimivalla linux herra orja arkkitehtuurilla ja lataa uusin versio saltista
- lataa tulevalla windows orjalla sama salt versio
- hyväksy orja
- tee jako kansiot 
- testaa pakettien latausta
- testaa powershelliä mitenkä se orja tottelee
- testaa chocolatey

Opiskelijan raportti: https://pseppanen296518693.wordpress.com/
- Tarkista että kummallakin on sama versio jos ei niin korjaa
- lataa salt-minion
- syötä masterin ip
- hyväksy orja
- tehdään tiedoston jakopaikka masterille
- haetaan githubista kirjasto että voidaan ladata windowsille ohjelmia
- lataa orjalla sovellus

Lopetus 15.00

# a)

Klo 18.30 aloitin VM windowsin laitailun osoitteesta https://developer.microsoft.com/en-us/windows/downloads/virtual-machines/ ja 2 tuntia myöhemmin se on käynnissä vihdoin ja viimein. Kuka keksi että nykyajan läppärit eivät tarvitse enään nettipiuhalle paikkaa? Ei paljoa langattomalla hyödytty gigan netistä latailussa. Latasin salt-minionin koneelle ja asensin sen.

![image](https://user-images.githubusercontent.com/129611461/235317312-0a5ef607-c177-4b7b-81a2-f491c31a8386.png)

Päätin käyttää kurssin alussa saatua herra orja asennussettiä minkä masterilla sitten ohjaan windows orjaa. Asennus tarvitsi masterin ipn ja sen hommasin komennolla hostname -I. Sen jälkeen menin masterille hyväksymään uuden orjani.

![image](https://user-images.githubusercontent.com/129611461/235317280-d4438c50-4e7a-414b-9d6b-90eceb7d8ebd.png)

Testataan onko windows hereillä test.pingillä

![image](https://user-images.githubusercontent.com/129611461/235319387-f54b5bb7-51f0-41b0-b908-72ad293e64de.png)

Ei kuulu mitään, käynnistin windows koneen uudestaan ja siltikään ei kuulu mitään, mielenkiintoista. Ensimmäisenä mieleen tuli jos orja ja herra ovat eriversioissa. Testataan se.

![image](https://user-images.githubusercontent.com/129611461/235319501-6e51f2da-47a1-4ee1-908d-f459a84ba140.png)

Sama versio, loppui ymmärrys ja seuraavia tehtäviä katsottuani totean ettähän ei tässä pääse eteenpäin ennenkuin saa yhteyden. Aika lopettaa tältä päivältä taas ettei mene tunteisiin kun kone ei tottele. Klo 22.10


# b)

Nyt loppui vähän luetun ymmärtäminen että mitä tässä halutaan tehdä

![image](https://user-images.githubusercontent.com/129611461/235319035-7996766b-7c46-407a-b865-808a08d77076.png)

# Lähteet

https://pseppanen296518693.wordpress.com/

https://johanlindell.fi/palvelintenhallinta#h6

https://terokarvinen.com/2018/control-windows-with-salt/


