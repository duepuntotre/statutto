# Statutto <a target="_blank" href="https://apps.apple.com/it/app/id1502551398"><img src="https://lh3.googleusercontent.com/8mbGc4gAuQw8A0VvCG1VoF3Vk9IEno0Z0p4c0mUhew5qPwe3VMvhl_dgQGlQGNe5NgXAgWataVtTgVxRdg=w120"></a> <a target="_blank" href="https://play.google.com/store/apps/details?id=it.duepuntotre.statutto"><img src="https://lh3.googleusercontent.com/mxdkR4YgDDXlXWEY26d3PPQevzEPmK7zHQeoLezE-6NUCKtXi7k6R0MZbXW20bAdyEEfwDVoi29R1SNZew=w120"></a>

Statutto rappresenta un modo semplice e gratuito per consultare tutti i testi disponibili.

Funzionalità:
* segnalibri (possibilità di salvare gli articoli per una più rapida consultazione)
* ricerca (in tutti i testi, in un singolo testo, in un libro, in un titolo, in un capo e in una sezione)
* open content (possibilità di contribuire a modificare e/o aggiornare, aggiungere e annotare tutti gli articoli


Testi disponibili:
* Costituzione
* Preleggi
* Codice civile
* Codice di procedura civile
* Codice penale
* Codice di procedura penale
* Disposizioni di attuazione e transitorie del codice civile
* Disposizioni di attuazione e transitorie del codice di procedura civile
* Disposizioni di coordinamento e transitorie per il codice penale
* Norme di attuazione, di coordinamento e transitorie del codice di procedura penale
* Regolamento per l'esecuzione del codice di procedura penale
* Codice penale militare di pace
* Codice penale militare di guerra
* Disposizioni di coordinamento, transitorie e di attuazione dei codici penali militari di pace e di guerra
* Codice della strada
* Regolamento di esecuzione e di attuazione del nuovo codice della strada
* Codice antimafia
* Codice del consumo
* Codice dei contratti pubblici
* Codice del processo tributario
* Codice dell'ambiente
* Codice dei beni culturali e del paesaggio
* Codice del turismo
* Codice del Terzo settore
* Codice delle pari opportunità
* Codice dell'amministrazione digitale

# Come posso contribuire?

Attraverso [GitHub](https://guides.github.com/activities/hello-world) è possibile modificare e/o aggiornare, aggiungere e annotare tutti i testi di Statutto. 

# Documentazione di base

* Non si possono usare i doppi apici ```"```
* Non si può inserire l'"a capo" ma il codice tag ```<br>```
* I valori tra le parentesi quadre ```[ ]``` possono essere lasciati vuoti
* Nella struttura quando un nodo non ha sottonodi vanno indicati X-Y
* X = al numero del primo articolo; Y = al numero dell'ultimo articolo;
* X e Y possono essere uguali quando il nodo di riferimento contiene un solo articolo
* Se il nodo madre ha un articolo esterno ai sottonodi può essere usata la forma Z|X-Y dove Z è il numero dell'articolo nel nodo madre
* Se il numero degli articoli di X Y Z ha il suffisso -bis, -ter, -etc. questo va sostituito con bis, ter, etc. (ovvero privato del trattino: es. 416bis)

# Come aggiungere un testo

Inserire
```
	{
		"titolo": "Nome comune del testo",
		"sottotitolo": "Nome tecnico (es. D.Lgs. gg mese aaaa, n. x)",
		"note": "Aggiornato al Ultimo riferimento"
	}
```
nella prima parte
```
codici = [
	...
];
```
prima del tag di chiusura
```
];
```

# Come aggiungere la struttura di un testo

Inserire
```
	"Titolo del codice": "X-Y", //Esempio senza sottonodi

	"Titolo del codice": { //Esempio con sottonodi
		"Primo nodo della struttura (es. Libro I - Delle persone e della famiglia)": "X-Y", //Esempio di primo nodo senza ulteriori sottonodi
		"Primo nodo della struttura (es. Libro I - Delle persone e della famiglia)": { //Esempdio di primo nodo con sottonodi
			"Secondo nodo della struttura (es. Titolo I - Delle persone fisiche)": {
				"Terzo nodo della struttura (es. Capo I - Disposizioni generali)": {
					"Quarto nodo della struttura (es. Sezione I - Delle condizioni necessarie per contrarre matrimonio)": "X-Y",
					"Quarto nodo della struttura": "X-Y"
				}
			}
		}
	}
```
nella seconda parte
```
struttura = {
	...
};
```
prima del tag di chiusura
```
};
```

# Come aggiungere un articolo

```
Inserire

	{
		"codice": "Titolo del codice",
		"libro": "[Primo nodo della struttura]",
		"titolo": "[Secondo nodo della struttura]",
		"capo": "[Terzo nodo della struttura]",
		"sezione": "[Quarto nodo della stuttura]",
		"articolo": "Art. X [- Descrizione]",
		"testo": "Testo dell'articolo",
		"note": "[Note]"
	}
```
nella terza parte
```
articoli = [
	...
];
```
prima del tag di chiusura
```
];
```
