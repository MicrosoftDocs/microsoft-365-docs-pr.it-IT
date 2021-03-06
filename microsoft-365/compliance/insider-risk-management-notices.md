---
title: Modelli di avviso relativi ai rischi Insider
description: Informazioni sui modelli di avviso per la gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416480"
---
# <a name="insider-risk-management-notice-templates"></a>Modelli di avviso relativi ai rischi Insider

I modelli di avviso per la gestione dei rischi insider consentono di inviare messaggi di posta elettronica agli utenti quando le loro attività generano una corrispondenza e un avviso dei criteri. Nella maggior parte dei casi, le azioni degli utenti che generano avvisi sono il risultato di errori o attività involontarie senza intento non grave. Le note servono come semplici promemoria per gli utenti per prestare maggiore attenzione, per fornire collegamenti a informazioni per la formazione di aggiornamento o per le risorse dei criteri aziendali. Gli avvisi possono essere una parte importante del programma di formazione sulla conformità interna e possono contribuire a creare un audit trail documentato per gli utenti con attività a rischio ricorrenti.

Creare modelli di avviso se si desidera inviare agli utenti un avviso di promemoria tramite posta elettronica per le corrispondenze dei criteri nell'ambito del processo di risoluzione dei problemi. Gli avvisi possono essere inviati solo all'indirizzo di posta elettronica dell'utente associato all'avviso specifico esaminato. Quando si seleziona un modello di avviso da applicare a una corrispondenza dei criteri, è possibile scegliere di accettare i valori di campo definiti nel modello o sovrascrivere i campi in base alle esigenze.

## <a name="notice-templates-dashboard"></a>Dashboard dei modelli di avviso

La **dashboard dei modelli di avvisi** visualizza un elenco di modelli di avviso configurati e consente di crearne di nuovi. I modelli di avviso sono elencati in ordine di data inverso con il modello di avviso più recente elencato per primo.

![Dashboard del modello di avviso per la gestione dei rischi Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>HTML per gli avvisi

Se si desidera creare più di un semplice messaggio di posta elettronica basato su testo per le notifiche, è possibile creare un messaggio più dettagliato utilizzando HTML nel campo corpo del messaggio di un modello di avviso. Nell'esempio seguente viene fornito il formato del corpo del messaggio per un modello di notifica di posta elettronica basato su HTML di base:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> L'implementazione dell'attributo href HTML nei modelli di avviso per la gestione dei rischi insider attualmente supporta solo virgolette singole anziché virgolette doppie per i riferimenti URL.

## <a name="create-a-new-notice-template"></a>Creare un nuovo modello di avviso

Per creare un nuovo modello di avviso per la gestione dei rischi insider, userai la procedura guidata di avviso in **Insider risk management** solution nel Centro Microsoft 365 conformità.

Completare la procedura seguente per creare un nuovo modello di avviso per la gestione dei rischi insider:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda Modelli **di** avviso.
2. Selezionare **Crea modello di avviso** per aprire la procedura guidata di avviso.
3. Nella pagina **Crea un nuovo modello di avviso** completare i campi seguenti:
    - **Nome modello:** immettere un nome descrittivo per l'avviso. Questo nome viene visualizzato nell'elenco degli avvisi nel dashboard degli avvisi e nell'elenco di selezione degli avvisi quando si inviano avvisi da un caso.
    - **Invia da:** immettere l'indirizzo di posta elettronica del mittente per l'avviso. Questo indirizzo verrà visualizzato nel campo **Da:** in tutti gli avvisi inviati agli utenti, a meno che non venga modificato quando si invia un avviso da un caso.
    - **Campi Cc e Ccn:** utenti o gruppi facoltativi da notificare della corrispondenza dei criteri, selezionati in Active Directory per la sottoscrizione.
    - **Subject**: Le informazioni visualizzate nella riga dell'oggetto del messaggio supportano i caratteri di testo.
    - **Corpo del** messaggio : Informazioni visualizzate nel corpo del messaggio, che supportano valori di testo o HTML.
4. Selezionare **Crea** per creare e salvare il modello di avviso oppure scegliere **Annulla** per chiudere senza salvare il modello di avviso.

## <a name="update-a-notice-template"></a>Aggiornare un modello di avviso

Per aggiornare un modello di avviso per la gestione dei rischi insider esistente, eseguire la procedura seguente:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda Modelli **di** avviso.
2. Nel dashboard delle note selezionare il modello di avviso che si desidera gestire.
3. Nella pagina dei dettagli dell'avviso selezionare **Modifica**
4. Nella pagina **Modifica** è possibile modificare i campi seguenti:
    - **Nome modello:** immettere un nuovo nome descrittivo per l'avviso. Questo nome viene visualizzato nell'elenco degli avvisi nel dashboard degli avvisi e nell'elenco di selezione degli avvisi quando si inviano avvisi da un caso.
    - **Invia da:** aggiornare l'indirizzo di posta elettronica del mittente per l'avviso. Questo indirizzo verrà visualizzato nel campo **Da:** in tutti gli avvisi inviati agli utenti, a meno che non venga modificato quando si invia un avviso da un caso.
    - **Campi Cc e Ccn:** aggiornare gli utenti o i gruppi facoltativi per ricevere una notifica della corrispondenza dei criteri, selezionata in Active Directory per la sottoscrizione.
    - **Subject:** le informazioni di aggiornamento visualizzate nella riga dell'oggetto del messaggio supportano i caratteri di testo.
    - **Corpo del** messaggio : Aggiorna le informazioni visualizzate nel corpo del messaggio, supporta testo o valori HTML.
5. Selezionare **Salva** per aggiornare e salvare l'avviso oppure scegliere **Annulla** per chiudere senza salvare il modello di avviso.

## <a name="delete-a-notice-template"></a>Eliminare un modello di avviso

Per eliminare un modello di avviso per la gestione dei rischi insider esistente, eseguire la procedura seguente:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda Modelli **di** avviso.
2. Nel dashboard delle note selezionare il modello di avviso che si desidera eliminare.
3. Selezionare **l'icona** Elimina sulla barra degli strumenti.
4. Per eliminare il modello di avviso, selezionare **Sì** nella finestra di dialogo di eliminazione. Per annullare l'eliminazione, selezionare **Annulla.**
