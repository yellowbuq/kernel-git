# kernel-git

## Zadanie do wykonania!
Na samym początku zforkuj repozytorium do swojego konta na Githubie! Dziękie temu będziesz mieć swoją własną kopię tego repo u siebie.
Aby to zrobić musisz kliknąć przycisk "Fork" po prawej górnej części ekranu:

![image](https://user-images.githubusercontent.com/5701304/138130291-17e40ddf-b00d-4d1a-85c7-eda738e72057.png)

Gdy to już zrobisz sklonuj repozytorium, aby móc z niego korzystać lokalnie:
```bash
git clone https://github.com/<nazwa-twojego-konta-na-githubie>/kernel-git.git
```

Najpierw rozpoznaj sytuację oraz zobacz na którym branchu się znajdujesz:
```bash
git status
git branch
```

Ściągnij aktualne zmiany z repozytorium. Być może ktoś przed tobą coś zmajstrował...
```bash
git fetch
git pull
```

Stwórz nowego brancha (nazwa dowolna ale bez spacji, wielkich liter, znaków specjalnych) i przejdź na niego:
```bash
git branch <nazwa-brancha>
git checkout <nazwa-brancha>
```

Dla przećwiczenia wróć na `master`:
```bash
git checkout master
```

I usuń brancha, który własnie stworzyłeś/łaś:
```bash
git branch -D <nazwa-brancha>
```

Ludzie są leniwi! Stwórz brancha jednocześnie na niego przechodząc używając jednej komendy:
```bash
git checkout -b <nazwa-brancha>
```

Dodaj coś do repozytorium! Lub usuń.. Tylko tym razem nie pushuj zmian - zrobimy to zaraz wspólnie. Zachowaj cykl developerski poznany we wcześniejszej części warsztatów - `git status`, `git add`, `git diff`, `git commit`. W razie problemów nie krępuj się i zapytaj kogoś z prowadzących.

Sprawdz swój dodany commit przy pomocy:
```bash
git log
```
Wyjście z trybu przeglądania commitów - literka `q`.

Teraz umieść swoje lokalne zmiany w repozytorium. Będąc na swoim branchu:
```bash
git push origin <nazwa-brancha>
```

Wejdź teraz na GitHub i stwórz nowego Pull Requesta prosząc osobę siedzącą obok o sprawdzenie twojego kodu - dodaj jako Reviewera przy tworzeniu Pull Requesta.

Po zaakceptowaniu przez nią jakości twoich zmian zmerguj PR do mastera.

Na końcu stwórz nowy Issue do Repozytorium, w którym powiesz nam co sądzisz o dzisiejszych warsztatach.
