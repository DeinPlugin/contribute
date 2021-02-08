# Mitwirken

Bei der Entwicklung der Plattform orientieren wir uns wie bei der Entwicklung eingereichter Plugins an dem [Code of Conduct](https://github.com/DeinPlugin/contribute/blob/main/CODE-OF-CONDUCT.md) von DeinPlugin.

"Amtssprache" auf Github und in den jeweiligen Plattform Repos ist **Englisch**.

## Branching

### feature / fix Branches

-   hier findet die eigentliche Arbeit statt
-   Branches werden nach dem Schema `feature/<was-ist-das-feature>` oder `fix/<was-wird-behoben>` erstellt
-   weitere Präfixe können `ci` (Änderungen an der ci) und `chore` (geringfügige Änderungen wie das hochzählen einer Library version) sein, auch hier wird ein kurzer, aussagekräftiger Name gewählt
-   die CI führt hier für jeden Commit Unittests aus
-   von hier aus werden Pull Requests auf den develop Branch gestellt

### develop Branch

-   ein Mergen auf develop erfordert mindestens ein Approval
-   ein Mergen auf develop wird immer per **sqash merge** durchgeführt
-   auf develop befindet sich die "nightly-Version", die wir auf eine staging-Umgebung deployen können
-   hier werden neue Features auf Herz und Nieren geprüft und das Zusammenspiel des Frontends mit dem Backend getestet
-   wenn Features gesammelt sind kann ein Pull Request auf `main` gestellt werden

### main Branch

-   ein Mergen von develop auf main findet hier nach dem vier-Augen-Prinzip statt – das bedeutet mindestens 2 Approvals
-   ein Mergen von develop auf main wird immer per **fast forward merge** durchgeführt
-   auf der main Branch ist die "latest-Version", von dort wird der Code per CI/CD direkt gebaut und produktiv gestellt

## Commits

-   einheitliche Commits ermöglichen einen guten Überblick über die Entwicklung

-   für das Committen zählt die Faustregel "zu viel committen geht nicht", lieber viele Kleine als einen Großen

-   Commit Messages werden auf Englisch verfasst

-   für die Commit Messages wenden wir **conventional commits** an ([Langfassung bei Interesse](https://www.conventionalcommits.org/en/v1.0.0/))

-   Mögliche Commit Typen

    -   feat: Features
    -   fix: Fehlerbehebungen
    -   chore: Kleinigkeiten
    -   ci: Änderungen an der CI
    -   docs: Änderungen an der Dokumention
    -   refactor: reines refactoring
    -   test: Schreiben / Ändern von tests

-   Beschreibung des Commits:

    -   im Imperativ
    -   beschreibt was der Commit ändert, wenn man ihn auf die Codebase anwendet

-   Struktur eines Commits:

    ```
    <typ>: <beschreibung>

    [optional body]
    ```

    man beachte die Leerzeile

-   Beispiele

    ```
    chore: bump library-x version to 0.1.5
    ```

    ```
    fix: do not print user passwords in cleartext
    ```

    ```
    docs: add documentation for deployment

    the deployment wasn't documented before, I wanted to add some documentation to help new
    contributors to start with the project
    ```

## Mergen

-   Der Ersteller des Pull Requestes merged, niemand anderes!
