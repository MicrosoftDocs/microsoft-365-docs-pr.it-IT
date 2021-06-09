---
title: Creare e gestire gruppi di dispositivi in Microsoft Defender for Endpoint
description: Creare gruppi di dispositivi e impostare livelli di correzione automatizzati su di essi confermando le regole applicabili al gruppo
keywords: gruppi di dispositivi, gruppi, correzione, livello, regole, gruppo aad, ruolo, assegnare, classificare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d4f62acde4e7d790c7a7c8635f51c99f0823687d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842771"
---
# <a name="create-and-manage-device-groups"></a>Creazione e gestione di gruppi di dispositivi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- Azure Active Directory
- Office 365

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


In uno scenario aziendale, ai team delle operazioni di sicurezza viene in genere assegnato un set di dispositivi. Questi dispositivi sono raggruppati in base a un set di attributi, ad esempio domini, nomi di computer o tag designati.

In Microsoft Defender for Endpoint puoi creare gruppi di dispositivi e usarli per:
- Limitare l'accesso agli avvisi e ai dati correlati a gruppi di utenti di Azure AD specifici con [ruoli RBAC assegnati](rbac.md) 
- Configurare impostazioni di correzione automatica diverse per diversi set di dispositivi
- Assegnare livelli di correzione specifici da applicare durante indagini automatizzate
- In un'indagine filtra **l'elenco Dispositivi** in base a gruppi di dispositivi specifici usando il **filtro** Gruppo.

Puoi creare gruppi di dispositivi nel contesto dell'accesso basato sui ruoli (RBAC) per controllare chi può eseguire azioni specifiche o visualizzare informazioni assegnando i gruppi di dispositivi a un gruppo di utenti. Per ulteriori informazioni, vedere [Manage portal access using role-based access control](rbac.md).

>[!TIP]
> Per un'analisi completa dell'applicazione RBAC, vedere: Il SOC è in esecuzione [flat con RBAC.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

Come parte del processo di creazione di un gruppo di dispositivi, dovrai:
- Imposta il livello di correzione automatico per il gruppo. Per ulteriori informazioni sui livelli di correzione, vedere [Use Automated investigation to investigate and remediate threats.](automated-investigations.md)
- Specifica la regola di corrispondenza che determina quale gruppo di dispositivi appartiene al gruppo in base al nome del dispositivo, al dominio, ai tag e alla piattaforma del sistema operativo. Se un dispositivo è abbinato anche ad altri gruppi, viene aggiunto solo al gruppo di dispositivi con il livello più alto.
- Selezionare il gruppo di utenti di Azure AD che deve avere accesso al gruppo di dispositivi.
- Classificare il gruppo di dispositivi rispetto ad altri gruppi dopo che è stato creato.

>[!NOTE]
>Un gruppo di dispositivi è accessibile a tutti gli utenti se non gli assegni alcun gruppo di Azure AD.

## <a name="create-a-device-group"></a>Creare un gruppo di dispositivi

1. Nel riquadro di spostamento, **selezionare** Impostazioni  >  **gruppi di dispositivi**.

2. Fai **clic su Aggiungi gruppo di dispositivi.**

3. Immetti il nome del gruppo e le impostazioni di automazione e specifica la regola di corrispondenza che determina quali dispositivi appartengono al gruppo. Vedi [Come inizia l'indagine automatizzata.](automated-investigations.md#how-the-automated-investigation-starts)

    >[!TIP]
    >Se si desidera raggruppare i dispositivi in base all'unità organizzativa, è possibile configurare la chiave del Registro di sistema per l'affiliazione di gruppo. Per altre informazioni sul tagging dei dispositivi, vedi [Creare e gestire tag dispositivo.](machine-tags.md)

4. Visualizzare in anteprima diversi dispositivi che saranno corrispondenti a questa regola. Se si è soddisfatti della regola, fare clic sulla **scheda Accesso** utente.

5. Assegnare i gruppi di utenti che possono accedere al gruppo di dispositivi creato.

    >[!NOTE]
    >È possibile concedere l'accesso solo ai gruppi di utenti di Azure AD assegnati ai ruoli RBAC.

6. Scegliere **Chiudi**. Le modifiche alla configurazione vengono applicate.

## <a name="manage-device-groups"></a>Gestire i gruppi di dispositivi

Puoi alzare di livello o abbassare di livello il rango di un gruppo di dispositivi in modo che gli sia stata data una priorità maggiore o inferiore durante la corrispondenza. Quando un dispositivo viene abbinato a più di un gruppo, viene aggiunto solo al gruppo con il livello più alto. È inoltre possibile modificare ed eliminare gruppi.



>[!WARNING]
>L'eliminazione di un gruppo di dispositivi può influire sulle regole di notifica tramite posta elettronica. Se un gruppo di dispositivi è configurato in base a una regola di notifica tramite posta elettronica, verrà rimosso da tale regola. Se il gruppo di dispositivi è l'unico gruppo configurato per una notifica tramite posta elettronica, la regola di notifica tramite posta elettronica verrà eliminata insieme al gruppo di dispositivi.

Per impostazione predefinita, i gruppi di dispositivi sono accessibili a tutti gli utenti con accesso al portale. Puoi modificare il comportamento predefinito assegnando gruppi di utenti di Azure AD al gruppo di dispositivi.

I dispositivi non corrispondenti ad alcun gruppo vengono aggiunti al gruppo Dispositivi non raggruppati (impostazione predefinita). Non è possibile modificare la classificazione di questo gruppo o eliminarlo. Tuttavia, è possibile modificare il livello di correzione di questo gruppo e definire i gruppi di utenti di Azure AD che possono accedere a questo gruppo.

>[!NOTE]
> L'applicazione delle modifiche alla configurazione del gruppo di dispositivi può richiedere alcuni minuti.


### <a name="add-device-group-definitions"></a>Aggiungere definizioni di gruppi di dispositivi
Le definizioni dei gruppi di dispositivi possono includere anche più valori per ogni condizione. Puoi impostare più tag, nomi di dispositivi e domini sulla definizione di un singolo gruppo di dispositivi.

1. Crea un nuovo gruppo di dispositivi, quindi seleziona **la scheda** Dispositivi.
2. Aggiungere il primo valore per una delle condizioni.
3. Selezionare `+` questa opzione per aggiungere altre righe dello stesso tipo di proprietà.

>[!TIP]
> Utilizzare l'operatore 'OR' tra le righe dello stesso tipo di condizione, che consente più valori per proprietà.
> Puoi aggiungere fino a 10 righe (valori) per ogni tipo di proprietà: tag, nome dispositivo, dominio.

Per altre informazioni sul collegamento alle definizioni dei gruppi di dispositivi, vedi Gruppi di [dispositivi - Microsoft 365 sicurezza](https://sip.security.microsoft.com/homepage).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso al portale tramite il controllo dell'accesso basato sui ruoli](rbac.md)
- [Creare e gestire tag di dispositivi](machine-tags.md)
- [Ottenere l'elenco dei gruppi di dispositivi tenant usando l Graph API](/graph/api/device-list-memberof)
