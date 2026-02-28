# Branch Strategie: Feature Branch Workflow 

**In diesem Dokument wird Unsere Branchstrategie vorgestellt**

*Bitte liest diese Aufmerksam durch und haltet euch an die darin enthaltenen Regeln*

## Das Wichtigste zuerst

- Der Mainbranch ist immer geschützt und es muss immer ein PullRequest erstellt werden wenn von einem anderen Branch gemergt wird.

- Es darf nicht im main herumexperimentiert werden. Jeders feature oder veränderung müssen in einem separaten Branch gelöst werden.

- Bei einem Konflikt beim mergen, muss dies perönlich mit den betroffenen Entwicklern geklärt werden.


## Branch

# Folgende Commits verwenden:

- **Feat**  : Eine neue Funktion oder Feature
- **fix**   : Behebung von Fehlern
- **docs**  : Bei Dokumentationen, Kommentaren
- **chore** : Bei Wartungsaufgaben, "Ausmisten"
- **style** : Bei Code änderungen Kosmetisch (Formatierung)

# Erklärung *Feature Branch Workflow*

Die Grundidee hinter dem Feature-Branch-Workflow ist, dass die gesamte Feature-Entwicklung in einem dedizierten Branch und nicht im main-Branch stattfinden sollte. Diese Einkapselung erleichtert mehreren Entwicklern die Arbeit an einem bestimmten Feature, ohne dabei die Haupt-Codebasis zu stören. Außerdem wird der main-Branch dadurch niemals beschädigten Code enthalten, was für Continuous Integration-Umgebungen ein immenser Vorteil ist.

Die Einkapselung der Feature-Entwicklung ermöglicht außerdem die Nutzung von Pull-Requests, die ein guter Einstiegspunkt für Diskussionen um Branches sind. Andere Entwickler haben dadurch die Möglichkeit, ein Feature zu genehmigen, bevor es in das offizielle Projekt integriert wird. Oder wenn du mitten in der Feature-Entwicklung nicht mehr weiterweißt, kannst du einen Pull-Request starten, um deine Kollegen um Vorschläge zu bitten. Tatsächlichen machen Pull-Requests es deinem Team unglaublich einfach, die Arbeit der anderen zu kommentieren.

Der Git Feature Branch Workflow ist ein zusammenstellbarer Workflow, bei dem andere übergeordnete Git-Workflows genutzt werden können. Auf der Übersichtsseite zu den Git-Workflows haben wir die anderen Git-Workflows besprochen. Der Git Feature Branch Workflow ist auf das Branching-Modell ausgerichtet, d. h. er orientierungsgebendes Framework zum Management und Erstellen von Branches. Andere Workflows sind mehr auf das Repository ausgerichtet. Der Git Feature Branch Workflow kann in andere Workflows integriert werden. Der Git-flow und die Git Forking Workflows nutzen herkömmlicherweise bezüglich ihrer Branching-Modelle einen Git Feature Branch Workflow.

## Funktionsweise

Der Feature-Branch-Workflow nutzt ein zentrales Repository und main steht für den Verlauf des offiziellen Projekts. Aber anstatt direkt auf ihrem lokalen main-Branch zu committen, erstellen Entwickler jedes Mal einen neuen Branch, wenn sie an einem neuen Feature arbeiten. Feature-Branches sollten beschreibende Namen haben, wie animierte-menue-objekte oder issue-#1061. Dadurch soll jedem Branch ein klarer, deutlich fokussierter Zweck zugewiesen werden. Git unterscheidet rein technisch nicht zwischen dem main-Branch und Feature-Branches, deshalb können Entwickler Änderungen am Feature-Branch bearbeiten, stagen und committen.

Darüber hinaus können (und sollten) Feature-Branches auf das zentrale Repository gepusht werden. Dadurch kann ein Feature mit anderen Entwicklern geteilt werden, ohne dass ein offizieller Code davon berührt wird. Da der main-Branch der einzige "besondere" Branch ist, stellt das Speichern mehrerer Feature-Branches auf dem zentralen Repository kein Problem dar. Natürlich ist dies auch eine praktische Methode, um die lokalen Commits aller Teammitglieder zu sichern. Im Folgenden geben wir einen Überblick über den Lebenszyklus eines Feature-Branches.

## Mit dem main-Branch beginnen

Alle Feature-Branches werden auf Basis des aktuellen Codestatus eines Projekts erstellt. In diesem Leitfaden wird vorausgesetzt, dass das Projekt im main-Branch geführt und aktualisiert wird.

1. git checkout main
2. git fetch origin 
3. git reset --hard origin/main

## Erstelle das Repository.

So kannst du vom Repository zum main-Branch wechseln, die neuesten Commits pullen und die lokale Repository-Kopie des main-Branches mit der neuesten Version aktualisieren.

## Einen neuen Branch erstellen

Verwende für jedes Feature oder Issue, an dem du arbeitest, einen separaten Branch. Nachdem du einen Branch erstellt hast. checkst du ihn lokal aus, damit alle deine Änderungen auf diesem Branch stattfinden.

1. git checkout -b new-feature

Dadurch wird ein Branch namens "new-feature" auf Basis des main-Branches ausgecheckt und das Flag -b weist Git an, den Branch zu erstellen, sofern es ihn noch nicht gibt.

## Aktualisieren, Hinzufügen, Committen und Pushen von Änderungen

Auf diesem Branch kannst du Änderungen wie gewohnt bearbeiten, stagen und committen und das Feature mit so vielen Commits wie nötig erstellen. Genau wie mit Git kannst du an Features arbeiten und Commits durchführen. Wenn du fertig bist, pushe deine Commits und der Feature Branch in Bitbucket wird aktualisiert.

1. git status
2. git add (eine Datei)
3. git commit

## Feature Branch zu Remote pushen

Es ist immer empfehlenswert, deinen Feature Branch in das zentrale Repository zu pushen. So schaffst du dir ein praktisches Backup und gibst auch anderen Entwicklern, mit denen du zusammenarbeitest, die Möglichkeit, Commits zu diesem neuen Branch zu sehen.

1. git push -u origin new-feature

Mit diesem Befehl wird new-feature zum zentralen Repository (origin) gepusht und das Flag -u fügt es als Remote-Tracking-Branch hinzu. Nach dem Einrichten des Tracking-Branches kannst du den Branch new-feature mit git push ohne jegliche Parameter automatisch in das zentrale Repository pushen. Um Feedback zum neuen Feature-Branch zu erhalten, kannst du eine Pull-Anfrage in einer Repository-Managementlösung wie Bitbucket Cloud oder Bitbucket Data Center erstellen. Hier kannst du Reviewer hinzufügen und vor dem Mergen einen letzten Blick auf den Code werfen.

## Einarbeiten von Feedback

Jetzt kommentieren und genehmigen deine Teamkollegen die gepushten Commits. Bearbeite ihre Kommentare lokal und committe und pushe die vorgeschlagenen Änderungen zu Bitbucket. Deine Updates erscheinen dann im Pull-Request.

## Pull-Request mergen

Vor dem Mergen musst du eventuelle Merge-Konflikte lösen, falls andere Entwickler Änderungen an dem Repository vorgenommen haben. Wenn deine Pull-Anfrage genehmigt wurde und es keine Konflikte gibt, kannst du deinen Code zum main-Branch hinzufügen. Führe das Mergen über die Pull-Anfrage in Bitbucket durch.

## Pull-Anfragen

Mithilfe von Branches kann man neben der Isolierung der Feature-Entwicklung auch Änderungen anhand von Pull-Anfragen diskutieren. Sobald ein Teammitglied ein Feature fertiggestellt hat, wird dieses nicht sofort in den main-Branch gemergt. Stattdessen pusht das Teammitglied den Feature-Branch zum zentralen Server, erstellt eine Pull-Anfrage und bittet darum, dass die Ergänzungen in den main-Branch gemergt werden. Dadurch erhalten andere Entwickler Gelegenheit, die Änderungen zu überprüfen, bevor sie Teil der Haupt-Codebasis werden.

Code-Review ist ein großer Vorteil von Pull Requests. Sie sind jedoch eigentlich dafür gedacht, damit ihr euch über Code austauschen könnt. Du kannst dir Pull Requests als Diskussion über einen bestimmten Branch vorstellen. Das bedeutet auch, dass sie zu einem viel früheren Zeitpunkt im Entwicklungsprozess genutzt werden können. Wenn ein Entwickler beispielsweise bei einem bestimmten Feature Hilfe braucht, muss er nur einen Pull Request senden. Interessierte werden dann automatisch benachrichtigt und können die Frage direkt neben den entsprechenden Commits sehen.

Sobald eine Pull-Anfrage akzeptiert wird, läuft die tatsächliche Veröffentlichung eines Features ähnlich ab wie beim zentralisierten Workflow. Zunächst musst du sicherstellen, dass dein lokaler main-Branch mit dem Upstream-main-Branch synchronisiert ist. Dann mergst du den Feature-Branch in den main-Branch und pushst den aktualisierten main-Branch zurück zum zentralen Repository.

Pull-Requests können durch Quellcodeverwaltungslösungen wie Bitbucket Cloud unterstützt werden.