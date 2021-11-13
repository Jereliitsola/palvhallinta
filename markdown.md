# h3 Versionhallinta - Jere Liitsola

Tein harjoituksen lauantaina 13.11.2021 omalla tietokoneellani. Gittiä ajetaan VirtualBoxissa sijaitsevalla "Debian Bullseye 11" käyttöjärjestelmällä.

## Tiivistelmä

[commonmark.org/help/](https://commonmark.org/help/)

- Kappaleiden väliin hyvä laittaa yksi rivi!
- Linkki -> `[Link](url)`
- Kuva -> `![Image](url)`

- Lista voidaan tehdä sekä - että * merkeillä.
- Lihavoitu teksti kahdella _ merkillä. Esim __Hei!__
- Kursivoitu yhdellä merkillä. Esim _Moikka!_

## a)

Raportti tehty MarkDownina :)

En valitettavasti päässyt osallistumaan torstaina 11.11.2021 tunnille, joten käytin [Tero Karvisen](https://terokarvinen.com/2016/publish-your-project-with-github/?fromSearch=git) github artikkelia päästäkseni alkuun. Käytin lähteenä myös [Career Karman artikkelia](

## b) Pull first

Muokataan tässä tehtävässä tiedostoja _markdown.md_ ja _readme.dm_
Sen jälkeen komennot järjestyksessä

	git add --all
	git pull
	git commit
	git push
	
![Gitfirst](https://user-images.githubusercontent.com/93517790/141511722-b656098c-9cc2-41f6-a5d3-e9b373e317d1.png)

![githubsecond](https://user-images.githubusercontent.com/93517790/141511736-943e421e-f53c-40a1-af9b-2a56ace76923.png)

Githubista voidaan nähdä, että muutoksia on tapahtunut.

![gitthird](https://user-images.githubusercontent.com/93517790/141511743-f17ff188-b625-403c-938f-d2c1d18aef97.png)


## c) Kaikki kirjataan

`git log --all` näyttää kaikki tehdyt commitit.

![gitfifth](https://user-images.githubusercontent.com/93517790/141511748-38aa7996-9c0a-48e0-9d43-f41f4aaa3f8a.png)

`git diff` näyttää kaikki edellisen commitin jälkeen tehdyt muutokset.

![githubfourth](https://user-images.githubusercontent.com/93517790/141511768-030eb310-9eaf-413b-adef-6222f5d397cc.png)

`git blame #tiedostonimi#` näyttää, milloin valitun tiedoston rivit on lisätty.

![gitsixth](https://user-images.githubusercontent.com/93517790/141511754-0f23003c-f818-4b4b-ae61-813a24a93347.png)

## d) Huppis! Tyhmä muutos.

Tehdään jokin tarpeeton muutos README.md tiedostoon.

![githubhuppis](https://user-images.githubusercontent.com/93517790/141513260-2da42e75-721b-43e1-b68f-3cbfa56ca70b.png)

Tuloksena saadaan koodia:

`git reset --hard`

`HEAD is now at d265649 Edit markdown.md file`

Tarkastellaan vielä lopuksi, että muutokset on todellakin __jääneet tekemättä__ komennolla:

`cat README.md`

![muutoksetEI](https://user-images.githubusercontent.com/93517790/141643085-238b6644-c26e-45d6-b288-41fd3da465a4.PNG)

## e) Formula. Tee uusi Salt-tila

Luodaan uusi, suhteellisen helppo salt-tila, jotta saadaan "lisätuntumaa" vielä jokseenkin tuntemattomaan aiheeseen.

Aloitetaan luomalla kansio ja muokkaamalla sen sisälle tulevaa koodi-tiedostoa:

`sudo mkdir -p /srv/salt/startpacket`

`sudoedit /srv/salt/startpacket/init.sls`

Tiedoston sisälle:

![gitti](https://user-images.githubusercontent.com/93517790/141643090-effeca50-b55f-49d7-b6ea-b01de234a0a1.png)

Komentoa hyvä testata ensin:

`sudo salt-call --local -l info state.apply startpacket`

Jonka jälkeen se voidaan ajaa minioneille:

![image](https://user-images.githubusercontent.com/93517790/141643259-33c8b4ac-7b8b-4dca-9c8a-8580f4945038.png)

Komento siis asentaa tree:n, apache2:n, mariadb-commonin ja varmistaa että apache2 on käynnissä.

Lähteet:

https://commonmark.org/help/


https://terokarvinen.com/2016/publish-your-project-with-github/?fromSearch=git


https://careerkarma.com/blog/git-log/ 

Käytetty `git log` -komentoa opiskellessa.


https://www.atlassian.com/git/tutorials/inspecting-a-repository/git-blame 

Käytetty `git blame` -komentoa opiskellessa.






