---
title: 'Gestire la rete di gestione delle informazioni (anteprima) '
description: Come configurare la gestione delle informazioni.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 3ca180dba82e677dbc0d9f112b713df14820ce61
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950773"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Gestire la rete di gestione delle informazioni (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).


Dopo aver [configurato la gestione della conoscenza](set-up-knowledge-network.md), in qualsiasi momento, un amministratore può apportare le modifiche alle impostazioni di configurazione tramite l'interfaccia di amministrazione di Microsoft 365.

Ad esempio, potrebbe essere necessario modificare le impostazioni per una delle seguenti operazioni:
- Aggiungere nuove origini di SharePoint ai miei argomenti.
- Modificare gli utenti che avranno accesso agli argomenti.
- Modificare gli utenti che dispongono delle autorizzazioni per eseguire attività nel centro argomenti.
- Modificare il nome del centro argomenti


## <a name="requirements"></a>Requisiti 
È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e gestire le attività relative alla conoscenza organizzativa.


## <a name="to-access-knowledge-management-settings"></a>Per accedere alle impostazioni di gestione delle informazioni:

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .
2. Nella sezione **informazioni organizzative** fare clic su **Connetti persone alla conoscenza**.<br/>

    ![Connettere le persone alla conoscenza](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Nella pagina **Connect people to Knowledge** selezionare **Manage** to open the **Knowledge Network Settings** pane.<br/>

    ![Knowledge-Network-Settings](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Modificare il modo in cui la rete di informazioni può trovare argomenti

Se si desidera aggiornare le opzioni per le origini degli argomenti di SharePoint, selezionare la scheda **individuazione argomenti** . Questa impostazione consente di selezionare i siti di SharePoint nel tenant che verranno sottoposti a ricerca per indicizzazione e estratti per gli argomenti.

1. Nella scheda **individuazione argomento** , in **selezionare origini argomento di SharePoint**, selezionare **modifica**.
2. Nella pagina **Seleziona origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione. Ciò include:</br>
    a. **Tutti i siti**: tutti i siti di SharePoint nel tenant. Questo acquisisce i siti correnti e futuri.</br>
    b. **All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.  È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. </br>
    c. **Solo siti selezionati**: digitare i nomi dei siti che si desidera includere. È inoltre possibile caricare un elenco di siti. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti. </br>

    ![Scegliere come trovare gli argomenti](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Se si dispone di un numero di siti che si desidera escludere (se si seleziona **tutto, tranne i siti selezionati**) o si include (se sono stati selezionati **solo i siti selezionati**), è possibile scegliere di caricare un file CSV con i nomi e gli URL del sito. È possibile selezionare **Scarica modello di sito. csv** se si desidera utilizzare il file modello CSV.

3. Seleziona **Salva**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Modificare gli utenti che possono visualizzare gli argomenti nell'organizzazione

Selezionare la scheda **individuazione argomento** se si desidera aggiornare gli argomenti individuati nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come le pagine di SharePoint.

1. Nella scheda **individuazione argomento** , in **utenti autorizzati a visualizzare gli argomenti della rete della Knowledge**base, selezionare **modifica**.
2. Gli **utenti che possono visualizzare gli argomenti della pagina della rete della Knowledge** base consentono di scegliere gli utenti che avranno accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e nell'argomento. È possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Solo persone o gruppi di sicurezza selezionati**</br>
    c. **Nessuno**</br>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Seleziona **Salva**.  
 
> [!Note] 
> Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze di gestione delle informazioni assegnate potranno visualizzare gli argomenti.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Modificare gli utenti che dispongono delle autorizzazioni per eseguire attività nel centro argomenti

Selezionare la scheda autorizzazioni per l' **argomento** se si desidera aggiornare gli utenti che dispongono delle autorizzazioni per eseguire le operazioni seguenti nella pagina Centro argomenti:

- Quali utenti possono creare e modificare gli argomenti: creare nuovi argomenti che non sono stati rilevati durante l'individuazione o modificare i dettagli della pagina di argomento esistente.
- Quali utenti possono gestire gli argomenti: confermare o rifiutare gli argomenti individuati.

Per aggiornare gli utenti che dispongono delle autorizzazioni per la creazione e la modifica degli argomenti:

1. Nella scheda **autorizzazioni dell'argomento** , in **utenti autorizzati a creare e modificare gli argomenti**, selezionare **modifica**.</br>
2. Nella pagina **utenti autorizzati a creare e modificare gli argomenti** è possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Solo persone o gruppi di sicurezza selezionati**</br>

    ![Creare e modificare gli argomenti](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Seleziona **Salva**.</br>

Per aggiornare gli utenti che dispongono delle autorizzazioni per gestire gli argomenti:

1. Nella scheda **autorizzazioni dell'argomento** , in **utenti autorizzati a gestire gli argomenti**, selezionare **modifica**.</br>
2. Nella pagina **chi** è in grado di gestire gli argomenti, è possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Utenti o gruppi di sicurezza selezionati**</br>

    ![Gestire gli argomenti](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Seleziona **Salva**.</br>


##  <a name="update-your-topic-center-name"></a>Aggiornare il nome del centro dell'argomento

Selezionare la scheda **centro argomenti** se si desidera aggiornare il nome del centro argomenti. 

1. Nella scheda **centro argomenti** , in **nome centro argomenti**, selezionare **modifica**.
2. Nella casella **nome centro** argomenti della pagina **modifica nome centro argomenti** Digitare il nuovo nome del centro argomenti.
3. Selezionare **Salva**

    ![Modifica nome centro argomenti](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Vedere anche



  






