# Tecniche avanzate di redazione degli atti giuridici mediante text editor e markup language (parte II)

> In questi mesi sono preso dalla preparazione ed esecuzione del [Corso PCT accreditato CNF fino agli inizi di Marzo](https://avvocati-e-mac.it/blog/2023/1/31/corso-pct-accreditato-ed-office-hour). Mi sono quindi reso conto che le pubblicazioni vere di articoli sul sito si stanno rarefacendo.
> Ho quindi deciso di “riciclare” la tesina che ho svolto nel 2021 a conclusione del corso di perfezionamento “Coding for lawyers e legal tech. Programmazione per giuristi, intelligenza artificiale e blockchain per il professionista legale del futuro” coordinato dal [prof. Ziccardi](https://ziccardi.eu)
> Vista la mole del testo ho deciso di dividerla in 3 parti che, spero, possano anche essere lette separatamente.
> Se vuoi ricevere il manoscritto completato (finemente impaginato in LaTeX grazie a Pandoc e Markdown) oltre che ricevere questi articoli, [iscriviti alla mia newsletter](https://www.avvocati-e-mac.it/mailinglist), a fine Marzo 2023 inviarò a tutti gli iscritti il PDF (se leggi questo articolo dopo tale data sappi che iscrivendoti alla newsletter avrai la possibilità di leggere anche tutte quelle precedenti).
> Ultimo avvertimento: lo stile, visto a chi mi rivolgevo, non è quello del sito ma più “aulico”.
> Buona lettura.



# Tipografia per avvocati e scrittori digitali

Lo scopo principale della scrittura è quello di persuadere il lettore o, quantomeno, veicolare il pensiero dell’autore e farlo comprendere al lettore.

La comunicazione quindi è il principale scopo della scrittura. Oltre al contenuto anche la forma dello stesso è importante: è di tutta evidenza che un buon contenuto unito con una forma non adeguata riduce il coinvolgimento del lettore e forma grafica e contenuto si compenetrano nel realizzare un documento scritto.

Come abbiamo visto nei punti precedenti, chi scrive, sostiene l’importanza di dividere la fase di scrittura da quella di impaginazione; ciò non dimeno ritiene che per l’impaginazione di un documento, **la tipografia**, sia importante se non essenziale.

Ciò in ragione del fatto che **qualsiasi testo scritto viene presentato al lettore in una qualche forma tipografica**.

La tipografia trova la sua origine nei volumi miniati del medioevo da cui poi la stampa tipografica ha copiato le regole e la struttura evolvendo ed innovando da essa.

La conoscenza della tipografia tuttavia è da sempre relegata al mondo della carta stampata e dell’editoria e non al mondo dell’ufficio dove, come si diceva nei punti precedenti, si è usato fino a tempi relativamente recenti la macchina da scrivere.

_Matthew Butterick_ con il suo libro _Typography for lawyer_ [^typography] è stato, nel mondo anglosassone, uno dei primi pionieri a proporre l’importanza della tipografia nel mondo legale (e non solo) oltre a divulgare i principi fondamentali della tipografia applicati al mondo legale.

## Tipografia digitale con \LaTeX

Per quanto qui ci interessa occorre segnalare uno strumento informatico che si avvantaggia delle regole della tipografia rendendo trasparente all’utente finale inesperto l’uso di tali regole.

Tale strumento è \TeX\ (leggasi _tek_:  le lettere infatti T, E, X corrispondono alle lettere greche tau, epsilon e chi e sono una abbreviazione di ΤΕΧΝΗ – technē, dal greco che significa “arte” o “mestiere”).  
Questo programma, creato nel 1978 da _Donald Knuth_, è un programma di tipografia digitale adatto alla stesura di testi scientifici e matematici.

Su detto strumento, relativamente complesso da padroneggiare, sono stati ricavati linguaggi di livello più alto (ovvero linguaggi che richiedono una conoscenza minore dei meccanismi di \TeX\) come \LaTeX\ di cui pare opportuno dare alcuni brevi cenni.

\LaTeX\ è un linguaggio di markup, ovvero scritto in testo semplice ma con l’aggiunta di specifiche espressioni per distinguere differenti “enfasi” da dare al testo, per la predisposizione di testi tipo-composti.

Rispetto ai programmi WYSIWYG, come i programmi di video-scrittura, \LaTeX\ utilizza un approccio opposto ovvero _WYSIWYM_ (_What You See Is What You Mean_, cioè “ciò che vedi è quello che intendi”). Tale approccio privilegia i contenuti alla forma. Secondariamente, suddividendo le due operazioni, permette di ottenere una volta “compilato”, ovvero tradotto il linguaggio di markup in un documento finale impaginato, un documento con caratteristiche tipografiche avanzate.

Se il formato Microsoft Word è lo standard per gli uffici il formato \LaTeX\ è lo standard per la produzione di documenti scientifici / accademici di carattere matematico.

Se scrivere in \LaTeX\ ha svariati vantaggi, tra cui il fatto di scrivere in testo semplice (come vedremo più approfonditamente nel punto successivo), vi sono degli innegabili svantaggi; primo tra cui la necessità di imparare il linguaggio di _markup_ di \LaTeX\.

Se sul lungo periodo imparare l’utilizzo del _markup_ di \LaTeX\ non è un grosso problema, all’inizio fare ciò richiede un investimento relativamente grosso. Si consideri inoltre che \LaTeX\ ha anche una serie di componenti aggiuntivi che permettono di espandere notevolmente le sue funzionalità. Ciò se da una parte permette a questo programma di essere molto flessibile e personalizzabile in base alle esigenze specifiche di un singolo utente, richiede anche di imparare l’utilizzo di tali componenti aggiuntivi.

La strada indicata dall’accademia scientifica, tuttavia, evidenzia possibili altre soluzioni che potrebbero permettere al mondo dell’ufficio di appropriarsi di questi strumenti evoluti con un minor consumo di energie e ulteriore necessità di imparare ad utilizzare troppi strumenti nuovi.

# Usare il testo semplice per scrivere e revisionare un documento

Il testo semplice, ovvero un documento di testo senza alcun tipo di formattazione aggiuntiva, è alla base dell’informatica moderna. La maggior parte dei programmi è scritta in testo semplice. 
Spesso per superare le limitazione del testo semplice si aggiunge ad esso un _markup_ ovvero una serie di segni “speciali” e propri del singolo linguaggio che permettono di attribuire particolari caratteristiche al testo.

L’esempio più noto nell’era moderna di linguaggio di _markup_ è l’HTML ovvero _HyperText Markup Language_ (traducibile letteralmente: linguaggio a marcatori per ipertesti) che è di fatto alla base del _World Wide Web_ ovvero Internet.

Anche l’HTML seppur onnipresente nella nostra vita moderna (ogni pagina web che navighiamo è in questo formato) ha delle caratteristiche che non lo rendono sufficientemente semplice per fare quello che qui si vuole ottenere, ovvero semplicemente scrivere.

A riprova di ciò sono nati nel tempo programmi WYSIWYG per creare pagine HTML.

Nel 2004 tuttavia è nato un linguaggio di _markup_ pensato fin da subito per essere semplice (permette di essere imparato in poco tempo) e pensato per scrivere: il **markdown**.

Il [markdown](https://daringfireball.net/projects/markdown/) nasce da un'idea di _John Gruber_ di [DaringFireball](https://daringfireball.net) e dal contributo di Aaron Swartz.

> _Markdown is a text-to-HTML conversion tool for web writers._
>
> “Markdown è uno strumento di conversione da testo a HTML per gli scrittori del web.”
>
> *John Gruber* introduzione al markdown (link:<https://daringfireball.net/projects/markdown/>)

*Gruber* all’epoca aveva iniziato a scrivere il proprio blog [^blog] e trovava scomodo e complesso scrivere tutto in HTML. Così pensò di implementare (aiutato poi da Swartz che dei due è il vero programmatore) un interprete _Perl_ [^perl] per scrivere in modo semplice e solamente testuale i suoi articoli del blog che poi, grazie allo script Perl, venivano convertiti in formato HTML e potevano essere pubblicati sul web.

La caratteristica peculiare del markdown è che il testo scritto in questo formato è facilmente leggibile da qualsiasi persona che non lo conosca ed è possibile impararne le regole di base in pochissimo tempo.

I file .MD, l’estensione del markdown, sono dei semplici file di testo, ovvero file con estensione .TXT.

## Perché riscoprire strumenti del passato dell’informatica?

Nel corso dello sviluppo del software per computer, soprattutto quello commerciale, si è assistito ad un progressivo approccio di semplificazione dell’attività di interfaccia tra uomo e macchina.

Se questo da un lato ha portato ad ampliare l’utenza che utilizza un computer, prima riservata a personale altamente istruito solitamente in ambito universitario, dall’altro lato, anche per scelte prettamente commerciali, i software sono diventati progressivamente trasparenti per l’utente finale il quale, di fatto, se non vuole non deve approfondire il funzionamento della macchina sotto il cofano. Questo approccio “oscurantista” ha tuttavia creato dei soggetti che utilizzano il computer senza tuttavia avere una conoscenza approfondita dello stesso e per limitati compiti specifici.

La padronanza di uno strumento complesso come il computer, tuttavia, richiede almeno in parte che l’utilizzatore finale conosca il suo funzionamento e gli strumenti di base con cui interagire con esso. In particolare gli strumenti più complessi che vengono resi _invisibili_ all’utente finale sono anche quelli dotati di maggior potenza e flessibilità.

Gli strumenti del “passato” dell’informatica hanno proprio queste caratteristiche: sono inizialmente ostici agli utenti inesperti e poco avvezzi a come funziona un computer ma permettono di svolgere compiti che abitualmente sono relegati ad utenti esperti.

## I vantaggi del testo semplice

Il testo semplice è la base dell’informatica moderna da quando non si usano più schede perforate di carta per impartire istruzioni ad un computer.

Il testo semplice ha svariate caratteristiche che, da sempre, lo rendono vantaggioso:

1. _È a prova del tempo_: essendo alla base dell’informatica non esiste un computer che non possa leggere un documento in testo semplice;
2. _È facile da manipolare ed automatizzare_: essendo utilizzabile da qualsiasi computer può essere elaborato con praticamente qualsiasi strumento software sia esso un programma di elaborazione di testi che un linguaggio di programmazione; quest’ultima caratteristica permette di automatizzare attività ripetitive su di un testo che, per i programmi di video-scrittura è impossibile fare o comunque è limitato dalla possibilità di utilizzare programmi compatibili con essi;
3. _È possibile avere uno strumento specifico per un compito specifico_: come abbiamo visto nella parte introduttiva di questo scritto avere uno strumento che svolga bene un compito specifico è fondamentale per ottimizzare i processi di lavoro e di scrittura; nel mondo dell’informatica e soprattutto nel mondo Unix [^unix] sono stati creati nel tempo strumenti proprio pensati con questa filosofia.

## Scrivere programmando

Da ultimo scrivere utilizzando il testo semplice permette di utilizzare gli strumenti della programmazione in modo più incisivo nella scrittura. 

Nel mondo giuridico esistono una serie piuttosto significativa di attività ripetitive. Tutti gli atti giuridici, ad esempio, contengono dati (delle parti, dei beni a cui fanno riferimento etc …) e l’inserimento di tali dati in un atto è attività a basso valore e prono ad errori. L’automazione di tali inserimenti in un documento massimizza l’attività dello scrittore nella realizzazione di contenuti e minimizza la possibilità di errore di inserimento e battitura.

Ancora, nella revisione del testo è necessario modificare parole su larga scala ed utilizzare _pattern_ di testo [^regex] per eseguire operazioni complesse sul testo stesso. Tutto ciò e molto ancora è possibile fare con semplice testo ed un adeguato programma per gestirlo.

### Come gestire la revisione di un testo semplice?

Da ultimo il lettore si potrebbe domandare come è possibile revisionare, casomai a più mani, un testo semplice.

Anche qui il mondo della programmazione, che - se ci si pensa - non è poi così lontano da quello della scrittura, può venire in soccorso. In particolare il sistema di controllo delle versioni denominato GIT ed inventato per sviluppare il kernel (il sistema operativo) di Linux può aiutarci.

Qui non interessa entrare nel dettaglio di come funziona un sistema di controllo delle versioni ma nel mondo della programmazione il codice di un programma (di fatto uno scritto) viene manipolato e modificato a volte da centinaia di sviluppatori. Tenere traccia di chi ha fatto una specifica modifica può diventare una operazione titanica se non impossibile.

GIT permette con un sistema di _commit_, di invii di modifiche, di tenere traccia non solo delle modifiche ma anche di chi le ha apportate ed eventualmente comparare differenti stati del testo.

Se può sembrare qualcosa di inusuale si segnala che in Italia Carlo Piana [^git_piana] ha già utilizzato questo strumento per la redazione di contratti e tracciamento delle loro modifiche.


[^multitasking]: Con multitasking (in italiano multiprocessualità), in informatica, si indica la capacità di un software di eseguire più programmi contemporaneamente, oggi si usa questo termina anche per significare la capacità (presunta) di un soggetto di svolgere più attività contemporaneamente.

[^typography]: Potete approfondire l’argomento **Typography for lawyers** al seguente link: <https://typographyforlawyers.com> è inoltre possibile acquistare il libro nella sua forma cartacea grazie a servizi come _Amazon.it_. A questo link: <https://www.avvocati-e-mac.it/webinar/2018-04-10-tipografia-per-avvocati> è possibile visionare il webinar gratuito tenuto da chi scrive e basato sugli spunti di _Butterick_ apportando qualche necessaria modifica conseguente alle peculiarità del mondo legale italiano.

[^blog]: Un **blog**, è un particolare tipo di sito web in cui i contenuti vengono visualizzati in una cronologia inversa (dal più recente al più lontano nel tempo). In genere il blog è gestito da uno o più soggetti che prendono il nome di _blogger_ che pubblicano, più o meno periodicamente, contenuti multimediali, in forma testuale o in forma di _post_ (traducibile in invio / pubblicare), concetto assimilabile o avvicinabile a un articolo di giornale.

[^perl]: **Perl** è un linguaggio di programmazione ad alto livello creato nel 1987 da Larry Wall. È stato originariamente pensato come linguaggio di manipolazione del testo e di file. Per approfondimenti link Wikipedia: <https://it.wikipedia.org/wiki/Perl>.

[^unix]: La **filosofia Unix** è una metodologia di sviluppo del software proposta nel 1969 da Ken Thompson e adottata dagli sviluppatori del sistema operativo Unix e da alcuni sistemi Unix-like.
Si basa sul motto: “_Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface._” traducibile in italiano come: “Scrivete programmi che facciano una cosa e che la facciano bene. Scrivete programmi che funzionino insieme. Scrivete programmi che gestiscano flussi di testo, perché quella è un'interfaccia universale.”. La frase, che suggerisce l'adozione della programmazione modulare a componenti e l'utilizzo dei canali standard (come il testo semplice)  per la comunicazione tra differenti processi / programmi.

[^regex]: Un’**espressione regolare** (in lingua inglese _regular expression_ o, in forma abbreviata _regex_) è una sequenza di simboli (quindi una stringa) che identifica un insieme di stringhe o caratteri rientranti in uno specifico _pattern_ o modello generale link Wikipedia per approfondimenti: <https://it.wikipedia.org/wiki/Espressione_regolare>. 

[^git_piana]: A questo link <https://www.techeconomy2030.it/2019/02/07/leg-git-usare-git-per-progetti-legali/> è possibile leggere l’articolo pubblicato dall’_avv. Carlo Piana_ per ulteriori approfondimenti. Per curiosità del lettore si segnala che questo stesso documento è stato scritto implementando GIT.