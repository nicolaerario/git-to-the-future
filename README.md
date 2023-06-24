> [Istruzioni in italiano](#esercizio-1)

# Exercise 1

1. Welcome to `Damage Inc.`!!!
   We need you to add a wonderful `feature` to our project: add a file and show us how to write a proper `Hello World`.

```shell
echo "Hello World" > hello-world.txt
```

(or you can create and edit the file with your favorite editor)

2. Right after that, when you are done and everything is ready, add the file to the `staging area` and go ahead and `commit` it:

```shell
git add hello-world.txt
git commit -m "feat: Add hello world message"
```

3. Okay, all good. Before sending the `PR` though, we realized that it's not a punchy enough "Hello world"...: it's missing a nice `!`.
   Even if you have already committed, you can add the fix without having to make another commit just for this small change, if you want.

   Edit the file by making the requested change and then:

```shell
git add -A
git commit --amend --no-edit
```

All done! Our **last** commit is `updated` with the changes we wanted but without creating an extra one.

> NOTE: To add to the `staging area`, this time we used the `-A` "flag" instead of the filename; this flag, shorthand equivalent to `--all` adds to the staging area "all files" (new, modified and deleted) in the `working tree`. Many tutorials suggest using the command `git add .` (note the dot); this command is very similar to the first one but has a subtle difference (for which I advise against it and avoid using it): it adds to the staging area "all files" present _in the current path (folder and subfolders)_. This means that we must always pay attention to the path we are in before using it.
> In addition, to the `--amend` flag we also passed the `--no-edit` flag; without the latter flag `git` would have opened the `commit editor` giving us the ability to edit the commit title as well.

---

# Esercizio 1:

1. Benvenuto nella `Damage Inc.`!!!
   Abbiamo bisogno che tu aggiunga una meravigliosa `feature` al nostro progetto: aggiungi un file e dimostraci come si scrive un `Hello World` come si deve.

   Quindi:

```shell
echo "Hello World" > hello-world.txt
```

(oppure crea ed edita il file con il tuo editor preferito)

2. Subito dopo, quando hai finito ed è tutto pronto, aggiungi il file nella `staging area` e procedi pure con il `commit`:

```shell
git add hello-world.txt
git commit -m "feat: Add hello world message"
```

3. Ok, tutto perfetto. Prima di mandare la `PR` però, ci siamo accorti che non è un "Hello world" abbastanza incisivo: manca un bel `!` al nostro messaggio!
   Anche se hai già fatto il commit, puoi rimediare senza doverne fare un altro solo per questa piccola modifica, se vuoi.

   Edita il file apportando la modifica richiesta e poi:

```shell
git add -A
git commit --amend --no-edit
```

Tutto fatto! Il nostro **ultimo** commit è stato "aggiornato" con le modifiche che volevamo ma senza crearne uno in più.

> NOTA: Per aggiungere alla `staging area`, stavolta abbiamo usato il "flag" `-A` anziché il nome del file; questo flag, abbreviazione equivalente a `--all` aggiunge alla staging area "tutti i file" (nuovi, modificati e cancellati) presenti nel `working tree`. Molti tutorial suggeriscono di usare il comando `git add .` (notare il punto); questo comando è molto simile al primo ma ha una sottile differenza (per la quale io lo sconsiglio ed evito di usarlo): aggiunge alla staging area "tutti i file" presenti _nel path corrente (cartella e sottocartelle)_. Questo significa che dobbiamo fare sempre attenzione al path in cui ci troviamo prima di utilizzarlo.  
> Inoltre, al flag `--amend` abbiamo passato anche il flag `--no-edit`; senza quest'ultimo flag `git` avrebbe aperto il `commit editor` dandoci la possibilità di modificare anche il titolo del commit.
