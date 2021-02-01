guild.ai
https://my.guild.ai/
Beispiele entnommen aus guild.ai Tutorial

Großartiger redditpost: 
https://www.reddit.com/r/MachineLearning/comments/cf97z8/d_current_state_of_experiment_management_tools/


Checklist für neue Projekte:

**Installation**
$ pip install guildai 

**Config: guild.yml**
https://my.guild.ai/t/guild-files/159

- description: Erklärung d. operation, wenn help aufgerufen wird
- main: Entrypoint der Operation. 
- flags-import: Diejenigen Variablen, die aus config in die Operation übertragen werden sollen (oder "all")
- output-scalars: Explizit geloggte oder als Ausgabe vorkommende skalare (können Metriken sein).

*Projekt Info:
$ guild operations

**Skripte Einbinden**
Skript ausführen: $ guild run <file>.py

**Modelle trainieren**
* Modell mit übergebenen Parametern trainieren:
- $ guild run train.py x='[-1,0,1]'
- $ guild run train.py x='[-1,1]' noise='[1,2]' # -> 4 runs, in jeder Parameterkombination

* Modell aus guild.yml ausführen:
- $ guild run train (ohne .py!)

* Grid Search
- $ guild run train.py x=linspace[-0.6:0.6:4]

* Random Search
- $ guild run train.py x='[-2.0:2.0]' --max-trials 5

* Bayesian Optimization
- $ guild run train.py 
**Hyperparameter setzen**

**Modelle vergleichen**
* Guild View/Tensorboard starten: 
- $ guild view
Guild View enthält Metadaten der runs.
- § guild tensorboard
Ermöglicht vergleich von Parametern und Korrelation zu Metriken

* In Terminal vergleichen: 
- $ guild runs
- $ guild runs info
- $ guild compare --min loss (Ordnet runs nach loss)
- $ guild compare --table --min los --top 3

**Nützliches**
* Sourcecode eines Runs auflisten:
- $ guild ls --sourcecode

* Sourcecode eins Runs extrahieren:
- $ guild open --sourcecode --path train.py

* Runs auflisten
- $ guild runs -m  (-m für 20 weitere, 20 pro m.)

* Runs löschen
- $ guild runs rm

* Gelöschte runs auflisten
- $ guild runs --deleted

* Gelöschte runs wiederherstellen
- $ guild runs restore

* Runs labeln
- $ guild select -o train.py --min loss (besten run oder so auswählen)
- $ guild label --tag best <id vom vorigen befehl)

* Runs filtern möglich
- guild runs --help

* Runs exportieren
- $ guild export --move archived-runs (verschiebt runs nach archived-runs)
