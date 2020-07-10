---
title: Microsoft Secure Score
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, come migliorare la posizione di sicurezza e gli amministratori di sicurezza che possono aspettarsi.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094799"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite. Può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).

Seguendo i suggerimenti per il Punteggio sicuro è possibile proteggere l'organizzazione dalle minacce. Da un Dashboard centralizzato nel centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, dei dati, delle app, degli strumenti e dell'infrastruttura di Microsoft 365.

Secure Score aiuta le organizzazioni:  

* Segnalare lo stato corrente della posizione di sicurezza dell'organizzazione.
* Migliorare la propria posizione di sicurezza fornendo individuabilità, visibilità, orientamento e controllo.  
* Confronta con benchmark e stabilisci indicatori di prestazioni chiave (KPI).

Le organizzazioni accedono alla visualizzazione robusta delle metriche e delle tendenze, all'integrazione con altri prodotti Microsoft, al confronto tra organizzazioni simili e molto altro ancora. Il Punteggio può anche riflettere quando le soluzioni di terze parti sono state indirizzate alle azioni consigliate.

![Homepage del Punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funzionamento

Si ricevono punti per la configurazione delle funzionalità di sicurezza consigliate, per l'esecuzione di attività relative alla sicurezza o per l'azione di miglioramento con un'applicazione o un software di terze parti o con una attenuazione alternativa. Alcune azioni di miglioramento offrono solo punti quando sono state completate e alcune forniscono punti parziali se sono state completate per alcuni dispositivi o utenti. Se non è possibile o non si desidera applicare una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.

Viene mostrato il set completo di possibili miglioramenti, indipendentemente dalla licenza, in modo da poter comprendere le procedure consigliate per la sicurezza e migliorare il punteggio. La posizione di sicurezza assoluta è rappresentata da un punteggio sicuro, che rimane invariato indipendentemente dalle licenze di prodotto possedute dall'organizzazione. Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente in uso.

Il Punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine di azione per la visualizzazione e il miglioramento. Secure Score sincronizza anche tutti i giorni per ricevere i dati di sistema relativi ai punti ottenuti per ogni azione.

### <a name="key-scenarios"></a>Scenari principali

- [Controllare il punteggio corrente](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Confronta il tuo punteggio con organizzazioni come le tue](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visualizzare le azioni di miglioramento e decidere un piano d'azione](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Avviare i flussi di lavoro per l'analisi o l'implementazione](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Centro sicurezza e integrazione di Microsoft 365 ServiceNow](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Come vengono segnate le azioni di miglioramento

Ogni azione di miglioramento vale 10 punti o meno. La maggior parte sono segnati in modo binario, se si implementa l'azione di miglioramento, come creare un nuovo criterio o attivare un'impostazione specifica, si ottiene il 100% dei punti. Per altre azioni di miglioramento, i punti vengono assegnati come percentuale della configurazione totale. Ad esempio, se l'azione di miglioramento dichiara di ottenere 10 punti, proteggendo tutti gli utenti con l'autenticazione a più fattori e si dispone solo di 50 di 100 totale degli utenti protetti, si riceverebbe un punteggio parziale di 5 punti (50 protected/100 Total * 10 Max PTS = 5 pts partial Punteggio).

### <a name="products-included-in-secure-score"></a>Prodotti inclusi nel punteggio sicuro

Sono attualmente disponibili suggerimenti per Microsoft 365 (incluso Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP e cloud app Security. Sono disponibili suggerimenti per gli altri prodotti di sicurezza. Gli elementi consigliati non riguardano tutte le superfici di attacco associate a ciascun prodotto, ma sono una buona linea di base. È inoltre possibile contrassegnare le azioni di miglioramento riportate da terze parti o da una attenuazione alternativa.

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Microsoft Secure Score ha aggiornato le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.

Se si attivano le impostazioni predefinite per la sicurezza, verranno assegnati punti completi per le azioni di miglioramento seguenti:

- Verificare che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro (9 punti)
- Richiedere l'AMF per i ruoli amministrativi (10 punti)
- Abilitare il criterio per bloccare l'autenticazione legacy (7 punti)

>[!IMPORTANT]
>Le impostazioni predefinite per la sicurezza includono funzionalità di sicurezza che forniscono una sicurezza analoga alle azioni di miglioramento "criterio di accesso a rischio" e "criterio di rischio utente". Invece di impostare questi criteri in base alle impostazioni predefinite per la sicurezza, è consigliabile aggiornare i relativi stati in "risolti tramite attenuazione alternativa".

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per avere l'autorizzazione per accedere a Microsoft Secure score, è necessario essere assegnati a uno dei ruoli seguenti in Azure Active Directory.

### <a name="read-and-write-roles"></a>Ruoli di lettura e scrittura

Con l'accesso in lettura e in scrittura, è possibile apportare modifiche e interagire direttamente con il Punteggio sicuro. È inoltre possibile assegnare l'accesso in sola lettura ad altri utenti.

* Amministratore globale
* Amministratore della sicurezza
* Amministratore di Exchange
* Amministratore di SharePoint
* Amministratore account

### <a name="read-only-roles"></a>Ruoli di sola lettura

Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare le aree dei punteggi o modificare i confronti personalizzati.

* Amministratore del supporto tecnico
* Amministratore utenti
* Amministratore del servizio
* Ruolo con autorizzazioni di lettura per la sicurezza
* Operatore della sicurezza
* Ruolo con autorizzazioni di lettura globali

## <a name="risk-awareness"></a>Sensibilizzazione ai rischi

Microsoft Secure Score è un riepilogo numerico della postura di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misure relative alla sicurezza. non si tratta di una misura assoluta del modo in cui il sistema o i dati verranno violati. Piuttosto, rappresenta la misura in cui sono stati adottati controlli di sicurezza nell'ambiente Microsoft, che possono contribuire a compensare il rischio di essere violati. Nessun servizio online è completamente immune dalle violazioni della sicurezza e il Punteggio sicuro non deve essere interpretato come garanzia contro la violazione della sicurezza in alcun modo.

## <a name="whats-new"></a>Novità 

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche. Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilità con il Punteggio identità sicuro e l'API del grafico

Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato. Tali modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza. Tuttavia, questi aggiornamenti sono stati resi temporaneamente incompatibili con il Punteggio di Microsoft Secure e l'API del grafico.

Nel tempo, il Punteggio di sicurezza dell'identità e l'API del grafico adotteranno il nuovo modello di punteggio. Fino a quel momento, i clienti vedranno le differenze nei punteggi riportati da Microsoft Secure score, Identity Secure score e l'API del grafico. Vi chiediamo scusa per qualsiasi inconveniente che questo comporta, e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.

### <a name="updated-improvement-actions"></a>Azioni di miglioramento aggiornate

- Aggiunta delle azioni di miglioramento di Azure Active Directory
- Aggiunta delle azioni di miglioramento di Azure Advanced Threat Protection
- Supporto per le indicazioni sulla sicurezza del trifosfato di adenosina di Microsoft Defender [& vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Tutti i consigli di sicurezza rilasciati forniti da TVM sono ora disponibili

### <a name="updated-interface-and-functionality"></a>Interfaccia e funzionalità aggiornate

* Tutte le nuove visualizzazioni metriche e tendenze per le discussioni su OICOL e Lead Level
* Nuove modalità di monitoraggio e benchmark del Punteggio
* Migliorare il monitoraggio e la comprensione delle regressioni dei punteggi
* Filtrare, contrassegnare, ricercare e raggruppare le azioni di miglioramento
* Gestire gli obiettivi futuri utilizzando le proiezioni dei punteggi e le azioni pianificate
* E altro ancora!

### <a name="june-2020"></a>Giugno 2020

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Azione di miglioramento rimossa per Microsoft Defender Advanced Threat Protection

* Attivazione delle regole di riduzione della superficie di attacco

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Sono state aggiunte azioni di miglioramento per Microsoft Defender Advanced Threat Protection

* Impedire a Adobe Reader di creare processi figlio
* Utilizzare Advanced Protection against ransomware
* Blocca tutte le applicazioni di Office dalla creazione dei processi figlio
* Bloccare le applicazioni di Office dalla creazione di contenuto eseguibile
* Blocca JavaScript o VBScript dall'avvio del contenuto eseguibile scaricato
* Bloccare l'esecuzione di script potenzialmente offuscati
* Bloccare i contenuti eseguibili dal client di posta elettronica e webmail
* Bloccare l'applicazione di comunicazione di Office dalla creazione dei processi figlio
* Blocca processi non attendibili e non firmati che vengono eseguiti da USB
* Blocca la persistenza tramite la sottoscrizione di eventi WMI
* Blocca le applicazioni di Office dall'inserimento di codice in altri processi
* Bloccare l'esecuzione di file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile
* Bloccare le creazioni dei processi originati da comandi di PSExec e WMI
* Bloccare la sottrazione di credenziali dal sottosistema di autorità di sicurezza locale di Windows (lsass.exe)
* Bloccare le chiamate API Win32 dalle macro di Office

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

In caso di problemi, fatecelo sapere inviando la [sicurezza, la Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Si sta monitorando la community e viene fornita assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Ottenere visibilità nella posizione di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
