# h3 komennus

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
Tiedoston sisälle on siis kirjoitettu vain print("Shining some more light"). Samalla tuli testattua että se toimii yhdellä koneella.
![image](https://user-images.githubusercontent.com/129611461/233856610-92cde6bf-9d53-46aa-9dce-fac4190b70ac.png)
