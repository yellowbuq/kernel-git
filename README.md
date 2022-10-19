# kernel-git

## Uwaga!
### Na początku spróbuj samodzielnie wyszukać w dostępnych źródłach komendy niezbędne do wykonania każdego z kroków. Dopiero gdy wujek Google zawiedzie - rozwiń rozwiązanie ;) 
### Nie krępuj się i pytaj opiekunów warsztatów o dowolną pomoc i wyjaśnienie. 

## Część I - Rozpoznanie terenu!
### W tej części poznasz podstawowe komendy niezbędne do poruszania się po repozytorium i sprawdzania stanu swojej pracy :) 

Na samym początku zforkuj repozytorium do swojego konta na Githubie! Dziękie temu będziesz mieć swoją własną kopię tego repo u siebie.
Aby to zrobić musisz kliknąć przycisk "Fork" po prawej górnej części ekranu:

![image](https://user-images.githubusercontent.com/5701304/138130291-17e40ddf-b00d-4d1a-85c7-eda738e72057.png)

<br>Gdy to już zrobisz <b>sklonuj repozytorium</b>, aby móc z niego korzystać lokalnie
<details><summary>Rozwiązanie</summary>
<p>

```bash
git clone https://github.com/<nazwa-twojego-konta-na-githubie>/kernel-git.git
```
</p>
</details>
<br><br>

Najpierw rozpoznaj sytuację i sprawdź na którym branchu się znajdujesz:
<details><summary>Rozwiązanie</summary>
<p>

```bash
git status
git branch
```
</p>
</details>
<br><br>

Ściągnij aktualne zmiany z repozytorium. Być może ktoś przed tobą coś zmajstrował...
<details><summary>Rozwiązanie</summary>
<p>

```bash
git fetch
git pull
```
</p>
</details>
<br><br>

Stwórz nowego brancha (nazwa dowolna ale bez spacji, wielkich liter, znaków specjalnych) i przejdź na niego:
<details><summary>Rozwiązanie</summary>
<p>

```bash
git branch <nazwa-brancha>
git checkout <nazwa-brancha>
```
</p>
</details>
<br><br>


Dla przećwiczenia wróć na `main` (dawniej `master`):
<details><summary>Rozwiązanie</summary>
<p>

```bash
git checkout master
```
</p>
</details>
<br><br>


I usuń brancha, który własnie stworzyłeś/łaś:
<details><summary>Rozwiązanie</summary>
<p>

```bash
git branch -D <nazwa-brancha>
```
</p>
</details>
<br><br>

Ludzie są leniwi! Stwórz brancha jednocześnie na niego przechodząc używając jednej komendy:
<details><summary>Rozwiązanie</summary>
<p>

```bash
git checkout -b <nazwa-brancha>
```
</p>
</details>
<br><br>

## Część II - Pora zmajstrować coś samemu!
### W tej części to właśnie Ty zmienisz zawartość repozytorium - dodajesz, modyfikujesz, urządzasz :)  

Na początku sprawdź stan git'a wykorzystując poznane wyżej komendy. Jeśli branch na którym aktualnie się znajdujesz do `main` (`master`), wówczas przejdź do innego istniejącego branch'a lub utwórz nowy.
<details><summary>Rozwiązanie</summary>
<p>

`git status`, `git branch`

</p>
</details>
<br><br>


Teraz czas na dodanie nowego, dowolnego pliku - txt/py/js/cpp - a następnie dodaj w nim kilka linijek kodu/tekstu i sprawdź ponownie status wersjonowanego repozytorium ;) 

W kolejnym kroku dodaj i zacomittuj wybrane pliki oraz dodaj commit message z opisem zaistniałych zmian. 
> <b>Uwaga!</b><br> 
> Commit message powinien być zwięzły, maksymalnie deskryptywny i w formie bezosobowej (oczywiście najlepiej w języku angielskim). Zachowanie tych reguł znacząco ułatwia cykl pracy nad Twoim projektem ;) 
   
<details><summary>Rozwiązanie</summary>
<p>

```bash
git add <PATH_TO_FILE>
git commit -m <MESSAGE_WRITTEN_IN_QUOTES>
```
Wyjście z trybu przeglądania commitów - literka `q`.

</p>
</details>
<br><br>

Teraz sprawdź swój dodany commit komendą do przeglądania dodanych commitów ;)   
<details><summary>Rozwiązanie</summary>
<p>

```bash
git log
```
Wyjście z trybu przeglądania commitów - literka `q`.

</p>
</details>
<br><br>

Aby móc "zpushować" swoje zmiany do serwisu GitHub będziesz musiał się z tym serwisem uwierzytelnić. Można tego dokonać na kilka sposobów:

<ol>
<li><a href="https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token">Token dostępu (dawnej logowanie hasłem)</a></li>
<li><a href="https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent">Kluczem SSH</a></li>
<li>OAuth (domyślny sposób dla VS Code oraz oprogramowania IntelliJ)</li>
</ol>

Najbardziej uniwersjalną metodą jest autentykacja z użyciem kluczy SSH. Sposób ten opisałem poniżej.

Najpierw generujemy pare kluczy następującym poleceniem:
```bash
    ssh-keygen -t ed25519 -C "twój_email@example.com"
```
Po wykonaniu tego polecenia zostaniemy zapytani o to gdzie zpisać ten klucz i o `passphrase`. Polecam nie zmieniać domyślnej lokalizacji klucza, ponieważ może to utrudnić potem gitowi odnalezienie owego klucza. Passphrase to dodakowe hasło które można nałożyć na dany klucz. Dodanie takiego hasła spowoduje iż każdy program próbujący użyć tego klucza zapyta nas najpierw o ustawione hasło. Passphrase jest opcjonalne i nie trzeba go podawać.

W kolejnym kroku kopiujemy zawartość wygenerowanego klucza publiczego z pliku `id_ed25519.pub` (Domyślnie powstałym w ~/.ssh). 

Wchodzimy na Githuba, klikamy w prawy górny róg na ikone profilu i wybieramy settings. W zakładce `SSH and GPG keys` klikamy `Add new` i wklejamy skopiowany klucz.

JUŻ CZAS! 
Umieść swoje lokalne zmiany w repozytorium w serwisie GitHub! Ponownie sprawdź swoje postępy pracy uprzednio poznanymi komendami, a następnie "wypchnij" zmiany do repo:
<details><summary>Rozwiązanie</summary>
<p>

```bash
git push origin <nazwa-brancha>
```

</p>
</details>
<br><br>


Wejdź teraz na GitHub i sprawdź postępy pracy. Czy widzisz nowo utworzony branch? Jeśli tak, stwórz nowego Pull Requesta prosząc osobę siedzącą obok o sprawdzenie twojego kodu - dodaj jako Reviewera przy tworzeniu Pull Requesta (uprzednio musisz dodać osobę obok do contributor'ów Twojego repo).

Po zaakceptowaniu przez nią jakości twoich zmian zmerguj PR do mastera.


## Część III - Post Scriptum

Na końcu stwórz nowy Issue do Repozytorium które sforkowałeś/łaś w pierwszej części. Daj znać co sądzisz o dzisiejszych warsztatach i jak Ci poszło ;) 

Jeśli spodobały Ci się zajęcia zostaw "Gwiazdkę" w Repozytorium :) 

Znośnego wieczoru! 
