---
title: Configurare origini di contenuto di apprendimento per Microsoft Viva Learning (Anteprima) nell'Microsoft 365 di amministrazione
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Informazioni su come configurare le origini di contenuto di apprendimento per Microsoft Viva Learning (Preview) nell'Microsoft 365 di amministrazione.
ms.openlocfilehash: aba5c9f4eae3de5a1dfccd306bd38b2e3eeea5d0
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333543"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Configurare origini di contenuto di apprendimento per Microsoft Viva Learning (Anteprima) nell'Microsoft 365 di amministrazione

> [!NOTE]
> Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente. 

Gli amministratori dell'interfaccia di amministrazione di Microsoft 365, da soli o assegnando il ruolo di amministratore delle conoscenze a utenti selezionati nell'organizzazione, possono gestire le impostazioni relative a Viva Learning (Anteprima) e configurare le origini di contenuto di apprendimento.

L'amministratore seleziona quali altre origini di contenuto di apprendimento (ad esempio, SharePoint o origini provider di contenuti di terze parti supportate) saranno disponibili per gli utenti di Viva Learning (Preview). L'amministratore configura quindi tali origini per assicurarsi che il contenuto sia disponibile per la ricerca e l'individuazione e possa essere visualizzato dai dipendenti che usano Viva Learning (Anteprima).

> [!NOTE]
>  Gli utenti a cui si accede a apprendimenti non Microsoft e LinkedIn Pro in un browser o in un visualizzatore incorporato. Questo apprendimento configurato è soggetto alle condizioni di licenza, privacy e servizio separate tra l'organizzazione e la terza parte e non le condizioni viva learning (anteprima). Prima di selezionare questo tipo di apprendimento, verificare di disporre di un contratto per l'organizzazione e gli utenti.

## <a name="assign-the-knowledge-admin-role-optional"></a>Assegnare il ruolo di amministratore della knowledge base (facoltativo)

Per eseguire queste attività è Microsoft 365 amministratore globale.

> [!TIP]
> L'amministratore della conoscenza deve essere moderatamente tecnico e disporre delle credenziali di amministratore di SharePoint esistenti, preferibilmente una persona esperta nell'istruzione, nell'apprendimento, nella formazione o nell'esperienza dei dipendenti nell'organizzazione.

### <a name="add-a-knowledge-admin"></a>Aggiungere un amministratore della knowledge base

Per aggiungere un amministratore della knowledge base per Viva Learning (Anteprima), segui questi passaggi:

1.  Nel riquadro di spostamento sinistro dell'Microsoft 365 di amministrazione passare a **Ruoli**.

2.  Nella scheda **Azure** **AD** della pagina Ruoli selezionare **Amministratore conoscenza.**
 
3.  Nel pannello **Amministratore della** Knowledge Base seleziona **Amministratori assegnati** e quindi seleziona **Aggiungi.**

     ![Pagina Ruoli nell'Microsoft 365 di amministrazione che mostra il pannello Amministratore della Knowledge Base per aggiungere un utente.](../media/learning/learning-add-knowledge-admin-1.png)

3.  Nel pannello **Aggiungi amministratori** seleziona la persona scelta per il ruolo e quindi seleziona **Aggiungi.**

     ![Pagina Ruoli nell'Microsoft 365 di amministrazione che mostra il pannello Aggiungi amministratori per aggiungere un utente.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>Rimuovere un amministratore della knowledge base

Per rimuovere un amministratore della knowledge base per Viva Learning (Anteprima), segui questi passaggi:

1.  Nel riquadro di spostamento sinistro dell'Microsoft 365 di amministrazione passare a **Ruoli**.

2.  Nella **scheda** **Azure AD** della pagina Ruoli selezionare **Amministratore conoscenza.**
 
3.  Nella **scheda Amministratori** assegnati  del pannello Amministratore della Knowledge Base selezionare **Rimuovi** e quindi selezionare la persona che si desidera rimuovere dal ruolo. Per confermare, selezionare **Rimuovi**.

     ![Pagina Ruoli nell'Microsoft 365 di amministrazione che mostra il pannello Amministratori assegnati per rimuovere un utente.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>Configurare le impostazioni per le origini di contenuto di apprendimento

Per eseguire queste attività, Microsoft 365 amministratore globale o amministratore della knowledge base.

Per configurare le impostazioni per l'apprendimento delle origini di contenuto in Viva Learning, attenersi alla seguente procedura:

1.  Nel riquadro di spostamento sinistro dell'Microsoft 365 di amministrazione passare **a** Impostazioni  >  **Impostazioni organizzazione**.

2.  Nella scheda **Servizi della**  pagina Impostazioni organizzazione selezionare Viva **Learning (anteprima).**

     ![Impostazioni pagina nell'interfaccia Microsoft 365 di amministrazione che mostra l'app Di apprendimento elencata.](../media/learning/learning-sharepoint-configure1.png)

3.  Nel pannello **Viva Learning (anteprima)** seleziona le origini di contenuto di apprendimento che vuoi configurare per l'organizzazione e quindi seleziona **Salva.**

     ![Riquadro di apprendimento nell'interfaccia Microsoft 365 di amministrazione che mostra le opzioni delle origini di contenuto.](../media/learning/learning-sharepoint-configure2.png)

Tra tutte le origini di apprendimento esistenti, alcune saranno abilitate per impostazione predefinita. Queste origini di apprendimento includono:

- LinkedIn Learning (contenuto gratuito)
- Microsoft Learn
- Microsoft 365 Formazione

> [!NOTE]
> Il contenuto gratuito di LinkedIn viene fornito agli utenti in base alle norme sulla privacy e al contratto per gli utenti di LinkedIn. LinkedIn riceverà l'indirizzo IP dell'utente, tutti i cookie precedentemente impostati da LinkedIn e setterà un nuovo cookie per tenere traccia dell'uso del contenuto gratuito. Gli utenti non devono accedere con LinkedIn per ricevere contenuti gratuiti.<br><br>
Per i contenuti premium di LinkedIn, l'organizzazione ha bisogno di una sottoscrizione per il team per accedere a tale contenuto. Gli utenti dovranno accedere a LinkedIn per accedere a tale apprendimento, fornito in base alle condizioni dell'organizzazione e degli utenti con LinkedIn.<br><br> Per i contenuti non Microsoft (ad eccezione del contenuto LinkedIn gratuito), assicurati che l'organizzazione abbia una sottoscrizione per consentire agli utenti di accedere a tale contenuto utilizzando un account aziendale prima di connetterlo a Viva Learning (Anteprima). Le sottoscrizioni personali degli utenti a provider di apprendimento non Microsoft non verranno integrate con Viva Learning (Preview). Gli utenti a cui si accede a apprendimenti non Microsoft e LinkedIn Pro in un browser o in un visualizzatore incorporato. Se gli utenti passano al contenuto in cui non hanno una sottoscrizione dell'organizzazione, potrebbero visualizzare una pagina del provider in cui possono iscriversi per un singolo abbonamento. Tutto l'apprendimento non Microsoft viene fornito ai sensi delle condizioni del provider non Microsoft e non come parte di Viva Learning. 

Per abilitare o disabilitare un'origine contenuto di apprendimento, selezionare la casella di controllo accanto all'origine. Se un'origine è abilitata, sarà visibile un segno di spunta.

## <a name="third-party-content-providers"></a>Provider di contenuti di terze parti 

Il set di provider di apprendimento connessi disponibili potrebbe cambiare in qualsiasi momento. Più provider verranno uniti man mano che il programma cresce. I provider disponibili potrebbero anche scegliere di interrompere la connessione con Viva Learning (Anteprima).

### <a name="skillsoft-as-a-content-source"></a>Skillsoft come origine di contenuto  

Per Viva Learning (Anteprima), gli utenti che hanno Skillsoft abilitato e scelgono di visualizzare il contenuto di Skillsoft verranno atterrato in una pagina Percipio che chiede loro di immettere il nome del sito Percipio dell'organizzazione. Dopo aver immesso il nome del sito dell'organizzazione, gli utenti verranno indirizzati alla pagina per accedere al sito Percipio dell'organizzazione. Gli utenti accederanno utilizzando le credenziali esistenti e visualizzano il contenuto selezionato in origine. Agli utenti verrà richiesto di immettere il nome del sito Percipio una sola volta, finché la cache del browser non viene cancellata. Per semplificare questa esperienza per gli utenti, è consigliabile includere il nome del sito Percipio nelle comunicazioni interne inviate su Viva Learning (Anteprima).

Si tratta di un'esperienza temporanea per l'anteprima e stiamo lavorando con Skillsoft per abilitare l'integrazione specifica del tenant per la disponibilità generale, che ignora il passaggio che richiede agli utenti di fornire il nome del sito Percipio dell'organizzazione. 

### <a name="details-on-microsoft-substrate"></a>Dettagli sul substrato Microsoft  

Per i dati copiati in Viva Learning (Preview) da un servizio non Microsoft (provider di formazione o sistema di gestione dell'apprendimento), non è possibile estrarre, correggere o eliminare direttamente i dati in Viva Learning (Anteprima). I dati importati da provider non Microsoft vengono aggiornati tempestivamente per riflettere le modifiche e le eliminazioni nei dati di origine non Microsoft.

È necessario collaborare con il fornitore del servizio non Microsoft per accedere, correggere, eliminare o estrarre dati in base alle condizioni di licenza, servizio o privacy del servizio non Microsoft. Le modifiche apportate verranno riflesse nei dati elaborati per l'uso in Viva Learning (Preview) al termine dei cicli di aggiornamento dei dati del servizio non Microsoft e Viva Learning (Anteprima). Se si disattiva la connessione tra Viva Learning (Anteprima) e un servizio non Microsoft, tutti i dati importati in precedenza da tale servizio verranno eliminati. 

## <a name="next-step"></a>Passaggio successivo

[Configurare SharePoint come origine di contenuto di apprendimento per Microsoft Viva Learning (anteprima)](configure-sharepoint-content-source.md)