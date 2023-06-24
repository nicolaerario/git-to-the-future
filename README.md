> [Istruzioni in italiano](#esercizio-2)

# Exercise 2

1. Last week was particularly productive at `Damage Inc.`: we developed a big feature that says "good morning" to all our users!  
   Today you will test it and then start a new one: we will say "good night" to our logged-in users!

2. We are confident in you. Start directly with the new feature: create a `good_night.txt` file with our message. (You can always continue manually through your editor as well, if you want):

```shell
echo 'Good Night!' > good_night.txt # Use single quotes or escape with '\!'
```

3. Well done!!! Now make a nice commit of your work and then move on to test the previous feature:

```shell
git add -A
git commit -m "feat: Add GoodNight feature"
```

4. Opening the file `good_morning.txt` you notice that it does not correctly report the message _"Good Morning!"_.  
   Your colleague `Marty GitFly` has introduced a small bug.  
   It is up to you to fix it now.
   Correct the message and then proceed with the commit:

```shell
echo 'Good Morning!' > good_morning.txt
git commit -am "fix: GoodMorning feature"
```

> _Note:_ The `flag -am` was used to create our commit this time. This is actually a shorthand for `-a (--all)` plus `-m (--message)` (which we have already seen).  
> The `-a` flag adds to the staging area any files, modified or deleted, that Git has previously tracked; it has no effect on untracked files, however.

5. Well, now let's take a look at our `history`:

```shell
git log --oneline
```

6. As you can see, the commits of the two "features" are succeeded by that of the fix. Nothing wrong with that, but we can make sure that we deliver a neater job (and without showing our colleague's error).  
   We can rewrite our history with an interactive `rebase (-i)`.  
   `HEAD` represents the `tip` of our current branch: let's select the three `parent` commits from here:

```shell
git rebase -i HEAD~3
```

7. Running the command will open the commit editor, with our three chosen commits, in order, preceded by a keyword (and an hash); Below is a legend with all available keywords (commands) and their descriptions.  
   By default, each commit, has `pick`. Saving and closing the editor in this state will essentially return you to the starting situation.  
   Let's rewrite history instead!  
   Let's cut the line with our last commit (`pick fix: GoodMorning feature`) by moving it between the first two.  
   Already by doing this we are, in effect, telling Git to apply the commit of the fix "before" the commit of the second feature.

   > _Note:_ Moving a commit into the history is not always possible without triggering conflicts.

   But we can do more!  
   Let's change the command `pick` to `fixup` (also abbreviated simply as `f`):  
   `f fix: GoodMorning feature`.  
   This way we tell Git to take the commit and "squash" it to the one immediately above, using the latter's commit message.  
   We save and close the commit editor and the rebase will end.  
   Launching a new log, we will see that the fix commit is gone.  
   Opening the `good_morning.txt` file, however, we will see that our changes are indeed there:

```shell
git log --oneline
```

We then deliver a very good job, clean and tidy. The `Damage Inc.` thanks us, and the next morning, on our desk, we find a coffee with a note saying, _"From your careless colleague, Marty."_

---

# Esercizio 2

1. La scorsa settimana è stata particolarmente produttiva alla `Damage Inc.`: abbiamo sviluppato una corposa feature che augura il buongiorno a tutti i nostri utenti!  
   Oggi ti occuperai ti testarla e ne inizierai una nuova: quella per dare la buonanotte ai nostri utenti loggati!

2. Siamo fiduciosi. Inizia direttamente dalla nuova feature: crea un file `good_night.txt` con il nostro messaggio. (Puoi sempre proseguire anche manualmente tramite il tuo editor, se credi):

```shell
echo 'Good Night!' > good_night.txt # Use single quotes or escape with '\!'
```

3. Ben fatto! Ora fai un bel commit del tuo lavoro e poi passa a testare la precedente feature:

```shell
git add -A
git commit -m "feat: Add GoodNight feature"
```

4. Aprendo il file `good_morning.txt` ti accorgi che non riporta correttamente il messaggio _"Good Morning!"_.  
   Il tuo collega `Marty GitFly` ha introdotto un piccolo bug.  
   Tocca a te risolverlo adesso.
   Correggi il messaggio e poi procedi con il commit:

```shell
echo 'Good Morning!' > good_morning.txt
git commit -am "fix: GoodMorning feature"
```

> _Nota:_ Per creare il nostro commit stavolta é stato usato il `flag -am`. Si tratta in realtà di una shorthand per `-a (--all)` più `-m (--message)` (che abbiamo già visto).  
> Il flag `-a` aggiunge alla staging area tutti i file, modificati o cancellati, già tracciati da Git in precedenza; non ha nessun effetto invece sui file non tracciati.

5. Bene, adesso diamo un'occhiata alla nostra `history`:

```shell
git log --oneline
```

6. Come vedi, ai commit delle due "features", succede quello del fix. Niente di male in questo, ma possiamo fare in modo di consegnare un lavoro più ordinato (e senza far vedere l'errore del nostro collega).  
   Riscriviamo la nostra history con un `rebase interattivo (-i)`.  
   `HEAD` rappresenta la "testa" del nostro branch attuale: selezioniamo da qui i tre commit "antenati":

```shell
git rebase -i HEAD~3
```

7. Lanciato il comando si aprirà l'editor dei commit, con i nostri tre commit prescelti, in ordine, preceduti da una keyword (ed un hash); Sotto, una legenda con tutte le keywords (comandi) disponibili e le rispettive descrizioni.  
   Di default, ogni commit, ha `pick`. Salvando e chiudendo l'editor in questo stato, essenzialmente si tornerà alla situazione di partenza.  
   Riscriviamo la storia invece!  
   Tagliamo la riga con il nostro ultimo commit (`pick fix: GoodMorning feature`) spostandola tra le prime due.  
   Già facendo questo stiamo, in pratica, dicendo a Git di applicare il commit del fix "prima" di quello della seconda feature.

   > _Nota:_ Spostare un commit nella history non è sempre possibile senza innescare conflitti.

   Ma possiamo fare di più!  
   Cambiamo il comando `pick` in `fixup` (anche abbreviato semplicemete in `f`):  
   `f fix: GoodMorning feature`.  
   In questo modo diciamo a Git di prendere il commit ed "unirlo" a quello subito sopra, utilizzando il messaggio di commit di quest'ultimo.  
   Salviamo e chiudiamo l'editor dei commit, il rebase si concluderà.  
   Lanciando un nuovo log, vedremo che il commit del fix è sparito.  
   Aprendo il file `good_morning.txt`, però, vedremo che le nostre modifiche sono effettivamente presenti:

```shell
git log --oneline
```

Consegnamo quindi un ottimo lavoro, pulito ed ordinato. La `Damage Inc.` ci ringrazia e la mattina dopo, sulla nostra scrivania, troviamo un caffè con un biglietto che dice: _"Dal tuo collega distratto, Marty"_
