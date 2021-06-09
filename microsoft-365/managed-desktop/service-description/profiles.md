---
title: Informazioni sui profili dei dispositivi
description: I vari profili che gli amministratori possono assegnare ai dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842003"
---
# <a name="device-profiles"></a>Profili dei dispositivi

Puoi assegnare configurazioni predefinite diverse ("profili di dispositivo") ai dispositivi, ognuna ottimizzata per le esigenze di tipi specifici di utenti. Sono disponibili tre profili di dispositivo:

- Standard
- Dati sensibili
- Power user

I profili dei dispositivi possono essere pensati come parte di una gerarchia di opzioni di configurazione dei dispositivi.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configurazioni dei dispositivi visualizzate come una piramide. Descrizione seguente":::

Fondamentalmente, ogni dispositivo Microsoft Managed Desktop dispone di una base che include una linea di base di sicurezza standard, criteri di conformità, Windows impostazioni di aggiornamento e gruppi. Per lavorare con Microsoft Managed Desktop, ogni dispositivo deve includere tutti questi elementi, che non possono essere modificati dagli amministratori senza una richiesta di Microsoft Managed Desktop.

I profili dispositivo vengono visualizzati al livello superiore successivo. A Microsoft Managed Desktop dispositivo deve essere assegnato un solo profilo. Gli amministratori possono scegliere il profilo assegnato a un dispositivo.

A un livello ancora superiore sono disponibili [ulteriori personalizzazioni.](customizing.md) Ogni dispositivo può avere una o più personalizzazioni (o no). Possono modificare un livello di livello inferiore (profili di dispositivo o la configurazione di base) o essere una richiesta completamente nuova che viene a più livelli rispetto alla configurazione standard.

Nella parte superiore sono presenti modifiche personalizzate, ad esempio dettagli di rete o applicazioni. Un dispositivo può avere un numero qualsiasi di queste modifiche, che non sono gestite o bloccate da Microsoft Managed Desktop.


## <a name="device-profile-details"></a>Dettagli profilo dispositivo

Nella tabella seguente vengono riepilogate le impostazioni e i relativi valori predefiniti per ogni impostazione configurata dai profili di dispositivo. Queste impostazioni sono configurate con OMA-URIs profili di configurazione personalizzati in Microsoft Endpoint Manager.

<br>

****

|Funzionalità|Dati sensibili|Power User|Standard|
|---|:---:|:---:|:---:|
|**Blocca Archiviazione**|Sì|Sì|No|
|**[Livello blocco cloud](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|Fortemente|Fortemente|Fortemente|
|**Disabilitare gli account Microsoft**|Sì|Sì|No|
|**Disabilitare le OneDrive**|Sì|Sì|No|
|**Passare al desktop sicuro per l'elevazione**|No|Sì|No|
|**Tag dispositivo Microsoft Defender per endpoint**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**Amministratore nel dispositivo?**|No|Sì|No|
|**Profilo Autopilot**|MMD Standard|MMD Power User|MMD Standard|
|**AppLocker**|Sì|No|No|
|**Blocca archivio pubblico**|Sì|Sì|No|
|

Ogni profilo del dispositivo include anche questi elementi:

- Un gruppo di dispositivi Azure Active Directory (AAD) dinamico
- Un gruppo di dispositivi AAD di appartenenza statica
- Profilo Microsoft Endpoint Manager configurazione utente

> [!IMPORTANT]
> Non modificare direttamente l'appartenenza a questi gruppi. Utilizzare l'interfaccia come descritto in [Riassegnare profili](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitazioni

Puoi richiedere eccezioni ai profili di dispositivo e ai relativi dettagli come farei con qualsiasi altro criterio. Tieni presente che puoi avere solo uno di ogni profilo di dispositivo nell'organizzazione Azure Active Directory ("tenant"). Ad esempio, non puoi richiedere che il profilo del dispositivo dati sensibili disabiliti AppLocker solo per alcuni utenti. Tutti i dispositivi con il profilo dati sensibili devono avere la stessa configurazione.

Ogni dispositivo può avere un solo profilo. Se un determinato dispositivo viene usato da più utenti, tutti gli utenti di tale dispositivo avranno la stessa configurazione.
