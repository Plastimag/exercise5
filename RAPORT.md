##Palvelinten hallinta harjoitus 5

Kurssin viidennessä harjoituksessa tavoitteena oli tehdä moduli git-varastoon ja kirjoittaa sitten varastoon raportti MarkDownilla.

##Git - varasto

Aloitin harjoituksen tyypilliseen tapaan livetikulta eli linuxin käynnistyttyä päivitin komentokehoitteesta järjestelmän (sudo apt-get update) ja vaihdoin näppäinasetukset suomenkielisiksi (set xkbmap fi). Tämän jälkeen asensin gitin komentokehoitteessa antamalla komennon "sudo apt-get install git" ja loin uuden repositorion GitHubissa (jossa minulla olikin jo tili, repositorio GNU gpl v3.0 lisenssin alaisena).

Tämän jälkeen loin mkdir komennolla harjoitusta varten kansion nimeltä "exercise5" ja vaihdoin gitin asetuksia komentokehoitteessa ensin komennolla "git config --global user.email 'email'" (eli annoin gitille email osoitteeni) ja git config --global user.name "Eemeli Salama" (eli vaihdoin gitin käyttäjänimen).

Seuraavaksi kloonasin githubissa olevan repositorion koneelleni antamalla komentokehoitteessa komennon "git clone https://github.com/Plastimag/exercise5.git". Komentokehoitteeseen tulostui seuraavat tiedot:

Cloning into 'exercise5'...
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
Checking connectivity... done.

##Moduuli

Tämän jälkeen loin käsillä olevaan kansioon (exercise5) uuden kansion antamalla komentokehoitteessa komennon "sudo mkdir module" ja kansion sisälle loin manifests kansion samalla tavalla. Manifests -kansion sisälle loin tekstitiedoston komennolla "sudoedit init.pp", jonka sisältö on seuraava:

class module{
 package {"apache2":
 ensure => "installed", 
 allowcdrom => "true",
 }
}

Seuraavaksi päivitin repositorioon tehdyt muokkaukset. Tämä onnistui antamalla komentokehoitteessa käskyt "git add . && git commit" ja "git pull && git push". Sitten piti vielä täyttää muutosloki (kertoa tehdyistä muutoksista) sekä antaa käyttäjänimi ja salasana. Seuraava tulostus ilmestyi komentokehoitteeseen:

Username for 'https://github.com': plastimag
Password for 'https://plastimag@github.com': 
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 464 bytes | 0 bytes/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/Plastimag/exercise5.git
 ab6151c..a0928e7 master -> master

Tarkistin vielä selaimen kanssa github-sivultani asiat olivat niinkuin pitikin ja huomasin että muutokset olivat tapahtuneet juuri toivotulla tavalla.

Tämän jälkeen lisäsin vielä README- tiedoston githubin kautta (iso painike alavasemmalla kuvassa) ja lisäyksen jälkeen annoin komentokehoitteessa käskyn "git pull" päivittääkseni myös koneessani olevat tiedot. "Pull" käskyn jälkeen tarkistin vielä "ls" -käskyllä että README -tiedosto on ilmestynyt. README -tiedosto oli paikalla kuten pitikin.

Aivan lopuksi tein vielä tämän MarkDown- Raportin + päivitys.
