---
title: 'Configurare la gestione delle informazioni (anteprima) '
description: Come configurare la gestione delle informazioni.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540131"
---
# <a name="set-up-knowledge-management-preview"></a>Configurare la gestione delle informazioni (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare la [gestione delle informazioni](knowledge-management-overview.md). 

> [!Important]
> È importante pianificare il modo migliore per impostare e configurare la gestione della conoscenza nell'ambiente in uso. Ad esempio, è necessario prendere in considerazione quanto segue:
- I siti di SharePoint che si desidera analizzare per gli argomenti.
- Gli utenti a cui si desidera rendere visibili gli argomenti.
- Gli utenti che si desidera concedere le autorizzazioni per la gestione degli argomenti nell'argomento centro.
- Gli utenti che si desidera concedere le autorizzazioni per la creazione o la modifica di argomenti nel centro argomenti.
- Il nome che si desidera assegnare al centro dell'argomento.

> [!Note]
> Potrebbe essere utile creare gruppi di sicurezza per assegnare agli utenti le autorizzazioni necessarie per visualizzare gli argomenti, gestire l'argomento e creare e modificare gli argomenti.

Un amministratore può anche [apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione](manage-knowledge-network.md) tramite le impostazioni di gestione delle informazioni nell'interfaccia di amministrazione di Microsoft 365.

## <a name="requirements"></a>Requisiti 
È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare le attività relative alla conoscenza organizzativa.

## <a name="set-up-your-knowledge-network"></a>Configurare la rete di conoscenze

Se si configura la rete della Knowledge base, è possibile effettuare le seguenti operazioni:

- Individuazione dell'argomento: selezione di origini e argomenti di argomento da escludere dall'individuazione.
- Visibilità sull'argomento: selezione degli utenti che possono visualizzare gli argomenti come elementi salienti, nelle pagine di ricerca e nell'argomento.
- Autorizzazioni per l'argomento: selezione degli utenti autorizzati a creare, modificare e gestire gli argomenti.
- Centro argomenti: creare il centro argomenti.
- Revisione: controllare e applicare le impostazioni.

Per configurare la rete delle informazioni:

1. Nell'interfaccia di amministrazione di Microsoft 365 (admin.microsoft.com), selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .
2. Nella sezione **informazioni organizzative** fare clic su **Connetti persone alla conoscenza**.<br/>

    ![Connettere le persone alla conoscenza](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Nella pagina **Connect people to Knowledge** fare clic su Guida **introduttiva** per eseguire il processo di installazione.<br/>

    ![Informazioni di base](../media/content-understanding/k-get-started.png) </br>

4. Nella pagina **scegliere il modo in cui la rete di informazioni può trovare gli argomenti** , verrà configurata l'individuazione dell'argomento. Nella sezione **selezione origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione. Questo include:</br>
    a. **Tutti i siti**: tutti i siti di SharePoint nel tenant. Questo acquisisce i siti correnti e futuri.</br>
    b. **All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.  È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. </br>
    c. **Solo siti selezionati**: digitare i nomi dei siti che si desidera includere. È inoltre possibile caricare un elenco di siti. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti. </br>

    ![Scegliere come trovare gli argomenti](../media/content-understanding/ksetup1.png) </br>
   
5. Nella sezione **Escludi argomenti per nome** è possibile scegliere di includere i nomi degli argomenti che non si desidera siano inclusi nei risultati individuati. Utilizzare questa impostazione per impedire l'inclusione di argomenti sensibili nell'ambito della rete della Knowledge base. Le opzioni includono:</br>
    a. **Non escludere argomenti** </br>
    b. **Escludere l'argomento contenente i termini seguenti**: se sono presenti argomenti che non si desidera visualizzare agli utenti nell'ambito della rete della Knowledge base.
   -Scaricare il modello specificato.
   -Immettere i nomi degli argomenti che si desidera escludere. È necessario indicare il tipo di corrispondenza come esatto o parziale. Corrispondenza esatta significa che gli argomenti che corrispondono al termine esatto verranno esclusi. La corrispondenza parziale è più rigorosa e significa che verranno esclusi gli argomenti che contengono il termine. Ad esempio, se si immette *doc* come nome dell'argomento, l' *assembly doc* verrà escluso mentre il *Docker* non lo farà. I nomi degli argomenti sono case insensitive.  
        -Selezionare questa impostazione  **+**   per importare il file CSV completato. Selezionare **carica**. Se il file è stato elaborato correttamente, verrà visualizzato un segno di spunta verde. Selezionare **Avanti**.</br>


6. Negli **utenti che possono visualizzare gli argomenti e dove possono visualizzarli** , verrà configurata la visibilità dell'argomento. Negli **utenti che possono visualizzare gli argomenti nell'impostazione della rete di conoscenze** , scegliere chi avrà accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e argomento. È possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Solo persone o gruppi di sicurezza selezionati**</br>
    c. **Nessuno**</br>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze di gestione delle informazioni assegnate potranno visualizzare gli argomenti. 

7. Nella pagina **autorizzazioni per gestione** argomenti scegliere gli utenti che potranno creare, modificare o gestire gli argomenti. Nella sezione **utenti autorizzati a creare e modificare gli argomenti** , è possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Solo persone o gruppi di sicurezza selezionati**</br>
8. Nella sezione **chi può gestire gli argomenti** è possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Utenti o gruppi di sicurezza selezionati**</br>

    ![Autorizzazioni per la gestione degli argomenti](../media/content-understanding/ksetup3.png) </br>

    Selezionare **Avanti**.</br>
9. Nella pagina **Crea centro** argomenti è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire i temi.  Nella casella **nome centro argomenti** Digitare un nome per il centro degli argomenti. Facoltativamente, è possibile digitare una breve descrizione nella casella **Descrizione sito** . </br>

Selezionare **Avanti**.</br>

   ![Creare centro informazioni](../media/content-understanding/ksetup4.png) </br> 

10. Nella pagina **revisione e fine** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche. Se si è soddisfatti delle selezioni, selezionare **attiva**.

    ![Fine e Revisione](../media/content-understanding/ksetup5.png) </br> 

11. Verrà visualizzata la pagina **rete informazioni attivata** che conferma che il sistema inizierà a analizzare i siti selezionati per gli argomenti e a creare il sito del centro informazioni. Scegliere **Fine**.</br>

    ![Attivato](../media/content-understanding/ksetup6.png) </br> 

12. Verrà restituito alla pagina **Connect people to Knowledge** . Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione. 

    ![Impostazioni applicate](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Dopo l'installazione, un amministratore può [apportare modifiche alle impostazioni di gestione delle informazioni selezionate](manage-knowledge-network.md) in qualsiasi momento tornando alla pagina.


## <a name="see-also"></a>Vedere anche



  






