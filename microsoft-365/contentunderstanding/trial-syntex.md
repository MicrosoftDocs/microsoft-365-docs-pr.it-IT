---
title: Eseguire una versione di valutazione di Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Informazioni su come pianificare ed eseguire un programma pilota di valutazione per SharePoint Syntex nell'organizzazione.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327117"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Eseguire una versione di valutazione di Microsoft SharePoint Syntex

In questo articolo viene descritto come configurare ed eseguire un programma pilota di valutazione per la SharePoint Syntex nell'organizzazione. Sono inoltre consigliate le procedure consigliate per la versione di valutazione.

## <a name="sign-up-for-a-trial"></a>Iscriversi per una versione di valutazione

La versione di valutazione SharePoint Syntex consente l'accesso a 300 utenti per 30 giorni.

> [!NOTE]
> Nella versione di valutazione sono inclusi fino a 300 utenti per garantire l'aggiunta automatica di 1 milione di crediti ai builder. Non è necessario includere 300 utenti perché una versione di valutazione abbia esito positivo.

È possibile ottenere la versione di valutazione da una delle origini seguenti:

- Pagina [SharePoint Syntex prodotto](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- Il [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com)
    1.  Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com).
    2.  Vai a **Fatturazione**  >  **Servizi di acquisto.**
    3.  Scorrere fino al pulsante **Componenti aggiuntivi**.
    4.  Nel riquadro SharePoint Syntex selezionare **Dettagli.**
    5.  Selezionare **Ottieni una versione di valutazione gratuita**.
    6.  Per confermare la versione di valutazione, seguire i passaggi rimanenti della procedura guidata.

È necessario essere un amministratore Microsoft 365 globale o un amministratore di fatturazione per attivare una versione di valutazione.

### <a name="who-should-be-involved-in-a-trial"></a>Who essere coinvolto in una versione di valutazione

|Ruolo  |Attività  |
|---------|---------|
|Microsoft 365 amministratore globale o amministratore fatturazione    |     Attivare la versione di valutazione e assegnare le licenze    |
|Microsoft 365 amministratore globale o SharePoint amministratore globale     |   Configurare SharePoint Syntex e creare centri contenuti      |
|Utenti aziendali     |    Creazione e test di modelli     |

### <a name="before-you-activate-a-trial"></a>Prima di attivare una versione di valutazione

Per pianificare correttamente una SharePoint Syntex, considerare i fattori seguenti:

- I test più significativi vengono completati in scenari e dati "reali".
- È possibile attivare una versione di SharePoint Syntex una sola volta per ogni tenant.

Un tenant di prova o demo può essere usato come "esecuzione a secco" per eseguire i passaggi di attivazione e i controlli amministrativi. Ma è probabilmente meglio valutare la creazione di modelli in un tenant di produzione.

Per ottimizzare il valore di una versione di valutazione in un tenant di produzione, la pianificazione e l'impegno aziendale sono essenziali. È consigliabile coinvolgere una o più aree aziendali per identificare da tre a sei casi d'uso che potrebbero essere potenzialmente indirizzati da SharePoint Syntex. Questi casi d'uso devono:

- Includere scenari che possono essere risolti tramite il modello di elaborazione dei moduli o di comprensione dei documenti.
- Avere una chiara comprensione dello scopo di tutti i metadati estratti; ad esempio, visualizzare la formattazione o l'automazione usando Power Automate. Sebbene SharePoint Syntex si concentri sulla classificazione dei documenti e sull'estrazione dei metadati, il valore da quantificare è ciò che questi metadati abilitano.
- Basarsi su un set di dati definito; ad esempio, siti SharePoint o raccolte specifiche. Un'errata SharePoint Syntex comune è che i modelli generici possono essere applicati a tutto il contenuto dell'organizzazione. Una visualizzazione più accurata è che i modelli sono creati per aiutare a risolvere problemi aziendali specifici in posizioni mirate.

Tutti questi casi d'uso potrebbero non essere adatti per SharePoint Syntex. L'obiettivo di una versione di valutazione di qualità non è dimostrare SharePoint Syntex tutti gli scenari. Al contrario, la versione di valutazione dovrebbe aiutare a comprendere meglio il valore del prodotto.

Per ognuno dei casi d'uso pianificati, identificare gli utenti esperti in materia nel contenuto o nel processo correlato. La creazione di modelli SharePoint Syntex è incentrata sugli esperti di dominio nel contenuto, anziché sui professionisti IT o sulle risorse per sviluppatori.

## <a name="activate-a-trial"></a>Attivare una versione di valutazione

Quando avvii una versione di valutazione, devi:

- Assegnare licenze agli utenti pertinenti.
- Eseguire [l'installazione aggiuntiva di SharePoint Syntex](set-up-content-understanding.md).
    - Potrebbe essere necessario [creare ulteriori centri contenuti.](create-a-content-center.md)

Dopo l'attivazione della versione di valutazione, puoi creare modelli ed elaborare i file. Vedi [le linee guida per la creazione del modello.](create-a-content-center.md)

## <a name="during-a-trial"></a>Durante una versione di valutazione

I periodi di prova sono limitati, quindi è meglio concentrarsi inizialmente sul fatto che i modelli SharePoint Syntex possano classificare i documenti ed estrarre i metadati per i casi di utilizzo definiti. Al termine del periodo di valutazione, è possibile valutare il modo in cui i metadati possono essere sfruttati.

## <a name="after-a-trial"></a>Dopo una versione di valutazione

In base al risultato della versione di valutazione, è possibile decidere se procedere all'utilizzo di produzione di SharePoint Syntex.

### <a name="proceed-to-production-use"></a>Passare all'uso in produzione

Per garantire la continuità del servizio, è necessario acquistare il numero necessario di licenze e assegnarle agli utenti. Gli utenti di prova che non hanno una licenza completa alla fine del periodo di prova non saranno in grado di utilizzare completamente SharePoint Syntex.

Potrebbe essere necessario stimare l'utilizzo previsto dell'elaborazione dei moduli e pianificare l'importo previsto dei crediti di Generatore di intelligenza artificiale. Per assistenza, vedi Stimare la capacità di [Generatore di intelligenza artificiale che fa al caso tuo.](https://powerapps.microsoft.com/ai-builder-calculator/)

### <a name="dont-proceed-to-production-use"></a>Non procedere con l'uso in produzione

Se non acquisti licenze dopo la versione di valutazione:

- Non sarà possibile creare nuovi modelli.
- Le librerie che eseguono modelli non classificano più automaticamente i file o estraggono i modelli.
- I file classificati in precedenza o i metadati estratti non saranno interessati. 
- I Centri contenuti e i modelli di comprensione dei documenti non verranno eliminati automaticamente. Questi rimarranno disponibili per l'uso se decidi di acquistare licenze in futuro.
- I modelli di elaborazione dei moduli verranno archiviati nell'istanza DIS (Common Data Services) dell'ambiente Power Platform predefinito. Questi potrebbero essere usati con licenze future per SharePoint Syntex o con le funzionalità di Generatore di intelligenza artificiale nella piattaforma Power.

## <a name="see-also"></a>Vedere anche

[Adozione SharePoint Syntex Microsoft: introduzione](adoption-getstarted.md)
