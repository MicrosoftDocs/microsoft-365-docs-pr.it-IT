---
title: Richieste degli interessati per la famiglia Visual Studio nell'ambito del GDPR e del CCPA
description: Richieste degli interessati per la famiglia Visual Studio nell'ambito del GDPR e del CCPA
keywords: Visual Studio, Visual Studio Code, Visual Studio per Mac, documentazione di Visual Studio, privacy, GDPR, CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
ms.openlocfilehash: 96cb6820e24a378351c82264929c3aec99e6d4f6
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "39624799"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli interessati per la famiglia Visual Studio nell'ambito del GDPR e del CCPA

Il [Regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione europea garantisce alle persone (denominate nel regolamento _interessati_) il diritto di gestire i loro dati personali. I dati personali sono ampiamente descritti nel GDPR come dati che si riferiscono a una persona fisica identificata o identificabile. Il GDPR garantisce agli interessati diritti specifici sui propri dati personali; tali diritti includono la possibilità di ottenere delle copie dei dati personali, richiedere di apportare delle modifiche ai dati, limitare il trattamento dei dati, eliminarli o riceverli in un formato elettronico. Una richiesta formale di un interessato rivolta a un titolare (un impiegato o un tipo di agenzia o organizzazione che detiene il controllo dei dati personali) in merito a un'operazione da effettuare sui propri dati personali è denominata _Richiesta dell'interessato_.

Analogamente, il California Consumer Privacy Act (CCPA) fornisce obblighi e diritti in materia di privacy per i consumatori della California, inclusi diritti simili ai diritti dell'interessato del GDPR, ad esempio il diritto di eliminare, ricevere e accedere alle informazioni personali (portabilità).  Nell'ambito dei diritti che i consumatori possono esercitare, il CCPA prevede inoltre l'obbligo di determinate divulgazioni, protezioni contro la discriminazione e requisiti di consenso o rifiuto esplicito per alcuni trasferimenti di dati classificati come "vendite". In generale, la definizione di vendite include la condivisione di dati a titolo oneroso. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](offering-ccpa.md) e le [Domande frequenti sul California Consumer Privacy Act](ccpa-faq.md).

Per informazioni generali sul GDPR, consultare la [sezione riguardante il GDPR del Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

## <a name="products-covered-by-this-guide"></a>Prodotti inclusi in questa guida

Questa guida illustra come usare gli strumenti Microsoft per esportare o eliminare i dati personali raccolti durante una sessione autenticata (dopo aver effettuato l'accesso) di Visual Studio, Visual Studio per Mac e delle estensioni Microsoft per questi prodotti e per Visual Studio Code. La guida illustra inoltre come effettuare richieste dell'interessato per i dati personali raccolti durante l'uso dei siti Web Developer Community di Visual Studio, NuGet.org e ASP.NET. Questi prodotti possono consentire l'uso di strumenti ed estensioni non Microsoft e Microsoft non ha il ruolo di responsabile o titolare del trattamento di dati per questi strumenti ed estensioni. Gli utenti dovranno contattare il provider di tali estensioni o strumenti per conoscerne i criteri riguardanti i dati personali e la raccolta.

## <a name="additional-privacy-information"></a>Ulteriori informazioni sulla privacy

Le Condizioni di licenza software Microsoft relative ai prodotti, l'[Informativa sulla Privacy Microsoft](https://go.microsoft.com/fwlink/?LinkId=660726) e gli [Impegni di Microsoft sul GDPR](https://docs.microsoft.com/legal/gdpr) descrivono le nostre procedure di trattamento dei dati.

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio, Visual Studio per Mac e Visual Studio Code

### <a name="personal-data-we-collect"></a>Dati personali raccolti da Microsoft

In quanto responsabile del trattamento dei dati in conformità al GDPR, Microsoft raccoglie i dati necessari dagli utenti per fornire le esperienze e migliorare Visual Studio e Visual Studio per le estensioni Mac e Microsoft e per Visual Studio Code. Esistono due categorie di dati: i dati dei clienti e i log generati dal sistema. I dati dei clienti includono dati transazionali e interazionali dell'utente necessari a questi prodotti per poter garantire il servizio. Ad esempio, per poter offrire agli utenti esperienze personalizzate come le impostazioni di roaming, Microsoft deve raccogliere le informazioni relative all'account utente e i dati sulle impostazioni. I log generati dal sistema sono composti da dati di utilizzo o di diagnostica usati per identificare e risolvere i problemi e migliorare prodotti e servizi; inoltre, tali log potrebbero contenere informazioni identificabili relative agli utenti finali, come per esempio il nome utente. I log generati dal sistema vengono conservati per un periodo massimo di 18 mesi. Ad esempio, questi log vengono aggregati per giorno di utilizzo del prodotto e includono la data di utilizzo, il nome del prodotto usato (ad esempio "Visual Studio 2017"), l'azione svolta (ad esempio "vs/core/packagecostsummary/solutionload") e il numero di volte in cui è stata eseguita tale azione, come mostrato in questo esempio:

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

Per ulteriori informazioni, vedere [Log generati dal sistema raccolti da Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).

Solo i dati personali allegati alle identità autenticate possono essere assistiti da un DSR. Pertanto, dato che, ad esempio, Visual Studio Code non supporta l'accesso, i log generati dal sistema provenienti da esso non sono allegati a un'identità autenticata e non possono essere serviti. Tuttavia, alcune estensioni Microsoft per Visual Studio Code possono fornire dati autenticati i quali possono usufruire del servizio del DSR. Per ulteriori informazioni, vedere [GDPR e Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). Generalmente Microsoft non conserva i dati per Visual Studio 2013 e versioni precedenti, ma alcune estensioni potrebbero fornire dati allegati a identità autenticate e possono usufruire dei servizi di DSR come specificato di seguito.

### <a name="how-users-can-control-personal-data"></a>Come gli utenti possono controllare i dati personali

Con i metodi riportati di seguito, Visual Studio 2015 e versioni successive, Visual Studio per Mac e Visual Studio Code consentono agli utenti di interrompere la raccolta dei dati e al titolare di esportare o eliminare i dati già raccolti.

#### <a name="in-app-settings"></a>Impostazioni in-app

Gli utenti possono controllare le impostazioni della privacy per questi prodotti. Per ulteriori informazioni, vedere gli articoli seguenti

- [Come gestire le impostazioni di privacy in Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).
- [Come gestire le impostazioni di privacy in Visual Studio per Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).
- [Come disattivare la creazione di report di telemetria in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

#### <a name="exporting-or-deleting-data"></a>Esportare o eliminare dati

I titolari possono gestire i dati dei clienti e i log generati dal sistema raccolti dagli interessati con uno di questi metodi, a seconda di come sia registrato il prodotto della famiglia di Visual Studio o l'estensione Microsoft. In alcuni casi, è necessario utilizzare entrambi i metodi. Entrambi i metodi consentono ai titolari di scaricare una copia della cronologia attività gestita da tale metodo. La chiusura di un account AAD o MSA elimina i dati dei clienti di Visual Studio associati e rende anonimi i dati personali identificabili nei log generati dal sistema relativi a tali prodotti. I log generati dal sistema resi anonimi vengono conservati per un periodo massimo di 18 mesi.

- Gli utenti che hanno registrato un prodotto della famiglia Visual Studio usando un account supportato da un tenant di Azure, ad esempio un account AAD o un account del servizio gestito associato a una sottoscrizione di Azure, possono seguire le istruzioni contenute in [Richieste degli interessati per Azure nell'ambito del GDPR](gdpr-dsr-azure.md).
- Gli utenti che hanno registrato un prodotto della famiglia Visual Studio senza un account supportato da un tenant di Azure, ad esempio molti account che usano un account Microsoft (MSA), possono usare [il Microsoft Privacy Response Center basato sul Web](https://aka.ms/userprivacysite), disponibile tramite il proprio account Microsoft, per visualizzare, controllare ed eliminare i dati dell'attività associati all'account Microsoft presenti in più servizi Microsoft. In questo scenario, l'utente ha il ruolo di titolare per i propri dati personali.

> [!NOTE]
> Quando il titolare di un account MSA elimina il proprio account, i dati personali relativi a questi prodotti vengono eliminati, che l'account risulti supportato da un tenant di Azure o meno; inoltre, i log generati dal sistema vengono resi anonimi.

Per Visual Studio 2013, i dati raccolti vengono resi anonimi. Per Visual Studio 2012 e versioni precedenti, i dati vengono eliminati immediatamente al momento della ricezione. In entrambi i casi, non risulta niente da visualizzare, esportare o eliminare in un secondo momento.

## <a name="visual-studio-developer-community"></a>Community degli sviluppatori di Visual Studio

Microsoft supporta le richieste relative al [Regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) tramite il sito Web di [Community degli sviluppatori](https://developercommunity.visualstudio.com). L'utente potrà visualizzare, esportare o eliminare i dati relativi ai feedback.

### <a name="personal-data-we-collect"></a>Dati personali raccolti da Microsoft

Microsoft raccoglie i dati per riprodurre e risolvere i problemi riscontrati con i prodotti della famiglia di Visual Studio. Questi dati includono dati personali e feedback pubblici. I dati personali includono:

- Le informazioni di profilo della [Community degli sviluppatori](https://developercommunity.visualstudio.com);
- Preferenze e notifiche;
- Gli allegati e i log generati dal sistema forniti dalla [segnalazione di un problema in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) o tramite la [Community degli sviluppatori](https://developercommunity.visualstudio.com);
- I voti.

I feedback pubblici includono: i problemi segnalati, i commenti e le soluzioni.

### <a name="how-users-can-control-personal-data"></a>Come gli utenti possono controllare i dati personali

#### <a name="view"></a>Visualizzazione

Per visualizzare i dati relativi ai feedback, procedere come segue:

1. Accedere alla [Community degli sviluppatori](https://developercommunity.visualstudio.com). Nell'angolo in alto a destra fare clic sul profilo e selezionare **Profilo e preferenze**.
2. Fare clic su una delle schede **Profilo**, **Notifiche**, **Attività** e **Allegati** per visualizzare i dati inviati ai sistemi di feedback.
   1. Per **Profilo** si intende il profilo della [Community degli sviluppatori](https://developercommunity.visualstudio.com), che include nome utente, indirizzo di posta elettronica, informazioni e così via.
   2. **Notifiche consente di controllare le notifiche di posta elettronica ricevute.
   3. Su **Attività** è possibile controllare gli elementi relativi ai feedback lasciati (pubblicazioni, commenti e così via) e le attività effettuate.
   4. **Allegati** consiste in un elenco di cronologia degli allegati in formato `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.

#### <a name="export"></a>Esportazione

È possibile esportare i dati dei feedback come parte del DSR. Verranno creati uno o più archivi in formato .zip che includono:

- Le informazioni di profilo della [Community degli sviluppatori](https://developercommunity.visualstudio.com);
- Le impostazioni di preferenze e notifiche;
- Gli allegati forniti dalla [segnalazione di un problema in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) o tramite la [Community degli sviluppatori](https://developercommunity.visualstudio.com).

> [!NOTE]
> Microsoft escluderà i seguenti feedback pubblici forniti dall'archivio: commenti, soluzioni e problemi segnalati.

Per avviare l'esportazione, procedere come segue:

1. Accedere alla [Community degli sviluppatori](https://developercommunity.visualstudio.com). Nell'angolo in alto a destra fare clic sul profilo e selezionare **Profilo e preferenze**.
2. Fare clic sulla scheda **Privacy** e quindi su **Crea un archivio** per richiedere l'esportazione dei dati.
3. Lo **Stato dell'archivio** verrà aggiornato per indicare la preparazione dei dati. L'intervallo di tempo prima che i dati risultino disponibili dipende dalla quantità di dati da esportare.
4. Quando i dati sono pronti, si riceverà un messaggio di posta elettronica.
5. Per scaricare i dati, fare clic su **Scarica archivio** nel messaggio di posta elettronica oppure passare alla scheda Privacy.

> [!NOTE]
> - Se si sceglie di non ricevere notifiche nella scheda Notifiche, non si riceverà alcun messaggio di posta elettronica.
> - Se si richiede di nuovo l'esportazione, verrà rimosso l'archivio precedente e creato uno nuovo.

#### <a name="delete"></a>Eliminazione

L'eliminazione rimuove le informazioni seguenti dalla [Community degli sviluppatori](https://developercommunity.visualstudio.com):

- Le informazioni del profilo
- Le impostazioni di preferenze e notifiche;
- Gli allegati forniti dalla [segnalazione di un problema in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) o tramite la [Community degli sviluppatori](https://developercommunity.visualstudio.com).
- I voti

> [!NOTE]
> Microsoft non eliminerà, ma renderà anonime, le seguenti informazioni pubbliche: i commenti, le soluzioni e i problemi segnalati.
>
> [!IMPORTANT]
> L'eliminazione di un account AAD o MSA avvia il processo di eliminazione per la [Community degli sviluppatori](https://developercommunity.visualstudio.com).

Per avviare un'eliminazione, procedere come segue:

1. Accedere alla [Community degli sviluppatori](https://developercommunity.visualstudio.com). Nell'angolo in alto a destra fare clic sul profilo e selezionare **Profilo e preferenze**.
2. Fare clic sulla scheda **Privacy** e quindi su **Elimina dati e account** per avviare l'eliminazione dei dati.
3. Verrà visualizzata una schermata di conferma.
4. Digitare "elimina" nella casella e quindi fare clic su **Elimina account**.

Quando si fa clic su **Elimina account:**

- Verrà eseguita la disconnessione.
- L'account, i dati personali e gli allegati della [Community degli sviluppatori](https://developercommunity.visualstudio.com) saranno eliminati.
- Microsoft renderà anonimi i feedback pubblici lasciati. Tali feedback pubblici rimarranno disponibili nella Community degli sviluppatori e l'autore risulterà un utente anonimo.
- Non verrà inviato un messaggio di posta elettronica a seguito dell'eliminazione dell'account in quanto l'utente non sarà più presente nel sistema.
- Se si segnala un nuovo problema o si effettua l'accesso nella [Community degli sviluppatori](https://developercommunity.visualstudio.com), si verrà identificati come nuovi utenti.
- Se si elimina l'account dalla [Community degli sviluppatori](https://developercommunity.visualstudio.com), questo non verrà eliminato dagli altri servizi Microsoft.

## <a name="xamarin-forums"></a>Forum di Xamarin

### <a name="personal-data-we-collect"></a>Dati personali raccolti da Microsoft

Tramite la community di utenti dei [Forum di Xamarin](https://forums.xamarin.com/), Microsoft raccoglie i dati forniti per riprodurre e risolvere i problemi che possono verificarsi con i propri prodotti e servizi. Questi dati includono dati personali e feedback pubblici. I dati personali raccolti sono i dati degli account utente (ad esempio, nomi utente e indirizzi di posta elettronica associati agli account dei Forum di Xamarin) e i feedback pubblici includono bug, problemi, commenti e soluzioni fornite tramite i Forum di Xamarin.

### <a name="how-you-can-control-your-data"></a>Come controllare i dati

#### <a name="xamarin-forums"></a>Forum di Xamarin

##### <a name="view"></a>Visualizzazione

Gli utenti con account attivi del Forum di Xamarin possono visualizzare i dati personali e i feedback pubblici (ad esempio, tutti i thread e i post pubblicati) dalla pagina dell'account del Forum di Xamarin. Gli utenti possono anche modificare i dati personali tramite la pagina dell'account.

##### <a name="export"></a>Esportazione

I Forum di Xamarin sono ospitati da terze parti, i Forum Vanilla. Per richiedere l'esportazione dei dati pubblici, gli utenti devono contattare forums@xamarin.com (monitorato dal team di Xamarin). Microsoft collaborerà, quindi, con i Forum Vanilla per trattare la richiesta.

##### <a name="delete"></a>Eliminazione

I Forum di Xamarin sono ospitati da terze parti, i Forum Vanilla. Per richiedere l'eliminazione dei dati personali e pubblici, gli utenti devono contattare forums@xamarin.com (monitorato dal team di Xamarin). Microsoft provvederà manualmente alla richiesta di eliminazione dei dati personali dell'utente.

> [!NOTE]
> Bugzilla per Xamarin non accetta più nuovi problemi. I titolari di account di Xamarin Bugzilla possono visualizzare un archivio di tutti i bug che hanno segnalato e di tutti i commenti che hanno aggiunto all'indirizzo [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/). Per richiedere l'eliminazione dei dati personali contenuti nell'archivio, gli utenti possono inviare una richiesta all'indirizzo [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose). I feedback pubblici, quali bug, problemi, commenti e soluzioni, che gli utenti hanno pubblicato su Xamarin Bugzilla non verranno eliminati dopo il ricevimento di una richiesta di eliminazione. Verranno invece anonimizzati, rimuovendo il nome e l'indirizzo di posta elettronica associati ai feedback pubblici creati dall'utente che invia la richiesta di eliminazione.

## <a name="nuget"></a>NuGet

Per ulteriori informazioni sul DSR per NuGet.org, vedere [Richieste di dati utente NuGet](https://docs.microsoft.com/nuget/policies/data-requests).

## <a name="aspnet"></a>ASP.NET

Per informazioni su DSR per il sito Web ASP.NET, vedere [Sito Web ASP.NET e trattamento delle richieste dell'interessato per il GDPR](https://www.asp.net/gdpr).

## <a name="iisnet"></a>IIS.NET

Per informazioni su DSR per il sito Web IIS.NET, vedere [Sito Web IIS.NET e trattamento delle richieste dell'interessato per il GDPR](https://www.iis.net/gdpr).

## <a name="other-visual-studio-family-services"></a>Altri servizi appartenenti alla famiglia Visual Studio

### <a name="surveymonkey"></a>SurveyMonkey

Di tanto in tanto, Microsoft invita i clienti a fornire feedback relativi a questi prodotti tramite SurveyMonkey. Questi dati vengono eliminati entro 28 giorni. Nella gestione delle richieste dell'interessato per questi prodotti, se Microsoft riceve risposte autenticate ai sondaggi, queste vengono incluse nell'esportazione ed eliminate insieme alle richieste dell'interessato.

## <a name="learn-more"></a>Ulteriori informazioni

- [Impegni di Microsoft relativi al GDPR con i clienti dei Prodotti software aziendali generalmente disponibili](https://docs.microsoft.com/legal/gdpr)
- [Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Dashboard di privacy di Microsoft](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [Richieste degli interessati per Azure nell'ambito del GDPR](gdpr-dsr-azure.md)
