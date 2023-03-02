# Jak rozwiązać zadania dotyczące layoutu na Githubie

> Zapoznaj się z [przydatnymi komendami GITa](https://mate-academy.github.io/fe-program/tools/git/useful-commands)

> Zapoznaj się z [komendami terminala](https://mate-academy.github.io/fe-program/tools/terminal/useful-commands)

## !!!!!!!!! WAŻNE !!!!!!!!!

- Aby uniknąć problemów z uprawnieniami, **NIE UMIESZCZAJ folderu projektów na pulpicie**;
- ŚCIEŻKA nie powinna zawierać SPACJI. np. `C:\Users\Twoja Nazwa\projekty`;
- Lepszym rozwiązaniem jest umieszczenie repozytoriów w `D:\projekty` lub `C:\Users\TwojaNazwa\projekty` na systemie Windows, lub w `/Users/TwojaNazwa/projekty` na systemie MacOS.

## Przed rozpoczęciem pierwszego zadania na Githubie

- Otwórz swoją stronę profilową na [Platformie MA](https://mate.academy/profile)
- Przewiń w dół i kliknij przycisk `Połącz` obok Githuba
- Potwierdź autoryzację aplikacji Mate academy

## Postępuj zgodnie z tymi instrukcjami dla wszystkich zadań HTML/CSS na Githubie:

### 1. Otwórz zadanie na platformie MA
- Kliknij przycisk `Zrób fork`
- Spowoduje to otwarcie strony repozytorium zadania na Githubie

### 2. **Forkuj** repozytorium
![How to fork the repo](./images/fork-the-repo.png)

### 3. W URL powinieneś zobaczyć swoją nazwę zamiast "mate-academy"
![After the repo fork](./images/after-the-repo-fork.png)

#### Aby sprawdzić, czy Platforma MA widzi forkowane repozytorium
- Wróć do zadania na platformie MA
- Odśwież stronę
- Przycisk powinien zmienić się na `Otwórz zadanie`
- Przejdź do forkowanego repozytorium na Githubie

#### Jeśli musisz usunąć forkowane repozytorium
<details>
  <summary>Kliknij tutaj, aby zobaczyć instrukcje</summary>

  - Otwórz ustawienia projektu ![Open project settings](./images/open-project-settings.png)
  - Usuń repozytorium ![Delete the repo](./images/delete-the-repo.png)
</details>

### 4. **Sklonuj** forka repozytorium
- kliknij zielony przycisk `Code`;
- wybierz zakładkę `HTTPS`;
- upewnij się, że link zawiera Twoją nazwę użytkownika Github (NIE `mate-acaedmy`);
- skopiuj link;
- otwórz **Git Bash** (Windows) lub **ZSH** (macOS) w folderze projektów;
- uruchom `pwd` w terminalu, aby sprawdzić, czy jesteś w folderze `projects`;
  - jeśli nie, przejdź do niego za pomocą komendy `cd` z wymaganą ścieżką;
- sklonuj repozytorium, uruchamiając polecenie `git clone` z URL-em, który skopiowałeś na Github
    ```
    git clone the-link-from-github
    ```
    
![Klonowanie repozytorium](./images/clone-the-repo.png)
![Powodzenie klonowania](./images/clone-success.png)

<details>
  <summary>Jak otworzyć Git Bash</summary>

  ![Git Bash here](./images/git-bash-here.png)
</details>

<details>
  <summary>Jak wkleić URL projektu do Terminala (Git Bash)</summary>

  ![Jak wkleić URL projektu do Terminala](./images/paste-url-to-terminal.png)
</details>

### 5. Otwórz projekt w IDE
- uruchom `code layout_hello-world` w terminalu;
- zobaczysz nazwę projektu jako nazwę folderu głównego w VSCode;

![Projekt otworzył się poprawnie](./images/project-in-vscode-correct.png)

<details>
  <summary>Projekt otworzył się ŹLE</summary>

  ![Projekt otworzył się źle](./images/project-in-vscode-wrong.png)
</details>

### 6. Otwórz Terminal w swoim IDE
- Użyj skrótu ``ctrl + ` `` (Windows) lub ``cmd + ` `` (MacOS)
- Sprawdź, czy jesteś wewnątrz projektu (nazwa projektu jest ostatnią częścią w terminalu)
- Sprawdź, czy terminal w VSCode to Git Bash (Windows) lub ZSH (macOS)

<details>
 <summary>Kliknij, aby zobaczyć, jak wybrać domyślny terminal w VSCode</summary>

 - Wybierz opcję `Select default shell` ![Wybierz domyślny terminal](./images/select-default-shell.png)
 - Wybierz Git Bash (Windows) lub zsh (macOS) ![Okno domyślnego terminala](./images/default-shell-popup.png)
 - Zamknij wszystkie otwarte terminale
 - Wszystkie nowe terminale będą Git Bash (lub zsh)
</details>

### 7. Uruchom `npm install` (lub po prostu `npm i`).
A następnie poczekaj, aż pobieranie wszystkich pakietów zostanie zakończone.

> Uwaga: Powinieneś wykonać tę komendę raz dla każdego nowego zadania.

<details>
 <summary>Jeśli nie masz Node.js</summary>

 ![Jeśli nie masz Node.js](./images/if-you-have-node-15.png)
</details>

<details>
 <summary>Jeśli uruchomisz `npm i` poza projektem</summary>

 ![Jeśli uruchomisz npm install poza projektem](./images/if-you-run-npm-i-outside-the-project.png)
</details>

<details>
 <summary>Jeśli masz Node.js 15 lub nowszą wersję</summary>

 ![Jeśli masz Node.js 15 lub nowszą wersję](./images/if-you-have-node-15.png)
</details>

<details>
 <summary>Jak przeinstalować Node.js</summary>

 - Otwórz `Dodaj lub usuń programy` ![Otwórz Dodaj lub usuń programy](./images/open-add-remove-programs.png)
 - Odinstaluj Node.js ![Odinstaluj Node.js](./images/uninstall-node-js.png)
 - Pobierz i zainstaluj Node.js https://nodejs.org/download/release/v14.16.1/ 
 - Usuń `node_modules` ![Usuń node_modules](./images/delete-node-modules.png)
 - Ponownie wykonaj komendę `npm i` ![npm install success](./images/npm-install-success.png)
</details>

### 8. Uruchomienie `npm start` w celu sprawdzenia, czy działa

Polecenie w terminalu nigdy się nie zakończy.

- Polecenie powinno otworzyć przeglądarkę pod adresem `http://localhost:8080/`.
- W tym momencie powinno być widoczne początkowe znaczniki strony.
- Jeśli strona jest pusta, dodaj tekst do `<body>` w pliku `src/index.html`.
- Tekst powinien pojawić się w przeglądarce.

<details>
 <summary>Jeśli strona jest nadal pusta po dodaniu tekstu</summary>

 - Zaktualizuj stronę, naciskając `ctrl + r` (`cmd + r` dla macOS).
 - Jeśli strona jest nadal pusta, sprawdź, czy zapisałeś zmiany. ![Wyłączona automatyczna zapisywanie](./images/autosave-is-disabled.png)
 - Włącz automatyczne zapisywanie. ![Włącz automatyczne zapisywanie](./images/enable-autosave.png)
</details>

<details>
 <summary>Jeśli strona jest otwarta na innym porcie (nie :8080)</summary>

 - Jeśli widzisz inny port, ![Niepoprawny port](./images/wrong-server-port.png)
 - oznacza to, że już uruchomiłeś inne polecenie `npm start` w terminalu (może to być inny projekt).
 - Zatrzymaj polecenie `npm start` w bieżącym terminalu, naciskając `ctrl + c` (wszystkie systemy operacyjne).
 - Zamknij inny terminal uruchamiający `npm start`.
 - Uruchom polecenie ponownie dla bieżącego projektu.
 - Adres URL powinien teraz wynosić `http://localhost:8080/`.
 - Jeśli adres URL nadal jest nieprawidłowy, po prostu uruchom ponownie komputer.
</details>

# 9. Otwórz kolejny terminal do wykonania kolejnych kroków.

Użyj przycisku "+" lub naciśnij ``ctrl + shift + ` `` lub ``cmd + shift + ` ``.

![Otwórz kolejny terminal](./images/open-one-more-terminal.png)

### 10. Utwórz branch `develop`

Uruchom:

```
git checkout -b develop

```

lub

```
git switch -c develop

```


<details>
  <summary>Jeśli widzisz informację, że branch "develop" już istnieje</summary>

  ![Develop already exists](./images/develop-already-exists.png)
  - Uruchom `git branch`, aby zobaczyć wszystkie istniejące branch-e ![Show git branches](./images/show-git-branch.png)
  - Jeśli `develop` jest oznaczone gwiazdką `*`, to wszystko jest w porządku
  - W przeciwnym razie, uruchom `git checkout develop` (bez klucza `-b`) ![Switch to develop](./images/switch-to-develop.png)
</details>

### 11. Zaktualizuj linki `DEMO LINK` i `TEST REPORT LINK`
- Otwórz plik `readme.md`
- Zastąp tekst `<your_account>` swoją nazwą użytkownika Github w linkach `DEMO LINK` i `TEST REPORT LINK`

![Zaktualizuj link do demo](./images/update-demo-link.png)

### 12. Zaimplementuj zadanie opisane w `readme.md`.

Kod powinien zostać napisany w pliku `index.html` oraz innych plikach w folderze `src`.

### 13. Sprawdź styl kodu
Uruchom polecenie:

```
npm run lint

```

<details>
  <summary>Jeśli występują błędy</summary>

  - Napraw wszystkie błędy i uruchom polecenie ponownie

  ![Linter errors](./images/linter-errors.png)
</details>

<details>
  <summary>Jak znaleźć linie z błędami lintera</summary>

  ![The lines with errors](./images/lines-with-linter-errors.png)
</details>

<details>
  <summary>Ten błąd oznacza, że musisz naprawić CRLF</summary>

  ![CRLF linter error](./images/crlf-linter-error.png)

  - Uruchom polecenie `git config --global core.autocrlf false`
  - I napraw CRLF we wszystkich plikach, które zostały zmienione

  ![CRLF in current file](./images/crlf-error-after-global-config.png)
</details>

<details>
  <summary>Jak naprawić autoformatowanie w VSCode</summary>

  - Oto [dokumentacja](https://code.visualstudio.com/docs/languages/html#_formatting) 
  - Uruchom polecenie `Alt + Shift + F`, aby sformatować dokument

  ![HTML autoformat settings](./images/html-autoformat-settings.png)
  ![HTML autoformat json](./images/html-autoformat-json.png)
</details>

### 14. Sprawdź, czy Twoje rozwiązanie spełnia wszystkie wymagania
- Przeczytaj `checklist.md`;
- Popraw swój kod;
- Uruchom testy;
    ```
    npm test
    ```
- Wyniki testów powinny otworzyć się w przeglądarce;
- Jeśli nie, sprawdź, czy naprawiłeś wszystkie błędy stylu kodu (`npm run lint`)

> Jeśli nie możesz uruchomić testów z jakiegoś dziwnego powodu, użyj zrzutu ekranu z `backstop_data/bitmaps_reference/Entire_document.png`, aby upewnić się, że Twoja strona wygląda tak, jak powinna.

#### Jeśli widzisz test, który nie przeszedł

Napraw swój kod HTML i CSS, aby Twoja strona była identyczna z oczekiwanym wynikiem.

![Failed tests](./images/failed-tests.png)
![How to compare a test with reference](./images/how-to-compare-test-with-reference.png)


### Jeśli widzisz błąd ERR_CONNECTION_REFUSED

![Connection refused error](./images/connection-refused-error.png)

- Sprawdź, czy masz inną kartę terminala, w której uruchomiony jest polecenie `npm start`;
- Otwórz nową kartę terminala i uruchom `npm start`;
- Sprawdź, czy strona jest otwarta pod adresem `http://localhost:8080/`;
- Uruchom ponownie polecenie `npm test`, aby zobaczyć wyniki.

### 15. Przygotuj swoje zmienione pliki do zapisania

```
git add ./src`
```

- Nie dodawaj nieistotnych plików w tym momencie, takich jak `package-lock.json` czy testowe migawki.
- Zawsze możesz sprawdzić, które pliki zostały zmienione lub dodane, używając polecenia `git status`.

### 16. Zapisz swoje zmiany

Wykonaj `commit` z komunikatem opisującym, co robi ten kod.

```
git commit -m 'add task solution'
```


<details>
  <summary>fatal: unable to auto detect email address</summary>

  - to oznacza, że zapomniałeś skonfigurować swojego nazwiska i adresu e-mail w Git
  - Zobacz polecenia powyżej komunikatu o błędzie i wykonaj je pojedynczo z podaniem swojego adresu e-mail i nazwy.

  ![If you forgot to set GIT name and email](./images/forgot-to-configure-git.png)
  ![Set GIT name and email](./images/set-git-name-and-email.png)
</details>

<details>
  <summary>no changes added to commit</summary>

  ![No changes added to commit](./images/no-changes-added-to-commit.png)
</details>

<details>
  <summary>LF will be replaced with CRLF</summary>

  - zapomniałeś naprawić CRLF 

  ![Forgot to fix CRLF](./images/forgot-to-fix-crlf.png)
</details>

### 17. Wyślij swój kod na Github
Uruchom:

```
git push origin develop
```


<details>
  <summary>niepowodzenie w przesłaniu niektórych odnośników</summary>

  ![Nie utworzono brancha develop](./images/forgot-to-create-develop.png)
  ![Zresetuj i utwórz branch develop](./images/reset-head-and-create-develop.png)

  - Skomituj zmiany ponownie po utworzeniu brancha `develop`
</details>

<details>
  <summary>Jeśli zostaniesz poproszony o uwierzytelnienie</summary>

  ![Github auth popup](./images/github-auth-popup.png)
  ![Autoryzuj menedżer poświadczeń GIT](./images/authorize-git-credentials-manager.png)
  ![Sukces pushowania](./images/push-success.png)
</details>

<details>
  <summary>fatal: unable to access</summary>

  ![Brak uprawnień](./images/permissions-denied.png)
  ![Dodaj poprawne origin](./images/add-correct-origin.png)
</details>

### 18. Opublikuj swoją stronę na GitHub Pages.
Uruchom:

```
npm run deploy
```

> Jeśli otrzymujesz jakieś błędy, uruchom polecenie `npm run deploy -- -l`, aby uzyskać więcej szczegółów.

Proces deployowania wymaga trochę czasu na przygotowanie twojej strony na Github po zakończeniu komendy.

Aby sprawdzić, czy strona została pomyślnie opublikowana, musisz sprawdzić ustawienia projektu na Github:
- Otwórz forka repozytorium na Github;
- Kliknij zakładkę `Settings` u góry;
- Wybierz sekcję `Pages` z panelu po lewej stronie;
- Na górze powinien pojawić się link do twojej publicznej strony (taki sam jak `DEMO LINK` w `readme.md`)
- Jeśli na górze nie ma linku, sprawdź, czy pojawił się branch `gh-pages` w repozytorium;
  - Jeśli nie, uruchom `npm run deploy -- -l`, aby uzyskać więcej szczegółów
- Poczekaj około 2 minut i ponownie załaduj `Settings > Pages`, aby zobaczyć link;
- Otwórz go, aby zobaczyć swoją stronę.

## 19. Utwórz Pull Request (PR)
- Wybierz kartę `Pull requsts`;
- Kliknij zielony przycisk `New pull request`;
- Zmień gałąź `compare` po prawej stronie na `develop`;
- Kliknij przycisk `Create pull request`;
- Skopiuj `DEMO LINK` oraz `TEST REPORT LINK` z pliku `readme.md` do opisu PR;
- Kliknij przycisk `Create pull request` raz jeszcze;
- Sprawdź, czy Twój `DEMO LINK` oraz `TEST REPORT LINK` działają poprawnie (otwórz stronę i wyniki testów);
- Sprawdź, czy zadanie pojawiło się na liście.

![New pull request](./images/new-pull-request.png)
![Create pull request](./images/create-pull-request.png)

<details>
  <summary>Sprawdź Twój DEMO LINK</summary>

  - Zapomniałeś dodać swoją nazwę użytkownika Github do `DEMO_LINK` i `TEST_REPORT_LINK`

  ![Forgot to fix DEMO LINK](./images/forgot-to-put-your-name-to-demo-link.png)
</details>

<details>
  <summary>Sprawdź Twój TEST REPORT LINK</summary>

  - Zapomniałeś uruchomić testów przed wykonaniem polecenia `npm run deploy`

  ![Forgot to run tests before deploy](images/forgot-to-run-tests-before-deploy.png)
</details>

### 20. Aktualizacja PR
Aby zaktualizować swój PR, powtórz kroki 13-18 (nie ma potrzeby tworzenia nowego PR).

> Jeśli potrzebujesz DODATKOWEJ RECENZJI KODU, kliknij przycisk "re-request" na stronie PR.

![Image of re-request button](https://user-images.githubusercontent.com/38065883/104471439-89929200-55c3-11eb-824a-596bfb8aa246.png)

## Dla użytkowników systemu Linux
> Jeśli używasz systemu _Linux_, upewnij się, że dostosowałeś uprawnienia do zapisu, aby umożliwić działanie skryptów bez użycia `sudo`. Poprawne uprawnienia oznaczają, że nie widzisz błędów takich jak `permission denied` po uruchomieniu poleceń w terminalu.

## Komendy NPM
- `npm install` instaluje zależności projektu i uruchamia `postinstall`
  - który tworzy pliki referencyjne do testów i pikselowej perfekcji
- `npm start` uruchamia serwer wymagany do pracy i testów
- `npm test` uruchamia linter i testy
  - `npm run lint` uruchamia linter (sprawdzenie stylu kodu)
  - `npm run test:only` uruchamia tylko testy pikselowej perfekcji
- `npm run deploy` publikuje stronę i raport z testów na `gh-pages`

## Przydatne linki
- [Przydatne komendy GIT](https://mate-academy.github.io/fe-program/tools/git/useful-commands)
- [Komendy terminala](https://mate-academy.github.io/fe-program/tools/git/useful-commands)
- [HTML, CSS styleguide](https://mate-academy.github.io/style-guides/htmlcss.html)
- [Praca z Figma](./figma.md)
- [Tworzenie pull requestu z forka](https://help.github.com/en/articles/creating-a-pull-request-from-a-fork)


