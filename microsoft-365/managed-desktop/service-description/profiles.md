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
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691281"
---
# <a name="device-profiles"></a>Profili dispositivo

Puoi assegnare configurazioni predefinite diverse ("profili di dispositivo") ai dispositivi, ognuna ottimizzata per le esigenze di tipi specifici di utenti. Sono disponibili tre profili di dispositivo:

- Standard
- Dati sensibili
- Power user

I profili dei dispositivi possono essere pensati come parte di una gerarchia di opzioni di configurazione dei dispositivi.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configurazioni dei dispositivi visualizzate come una piramide. Descrizione seguente":::

Fondamentalmente, ogni dispositivo Microsoft Managed Desktop ha una base che include una linea di base di sicurezza standard, criteri di conformità, impostazioni di Windows Update e gruppi. Per utilizzare Microsoft Managed Desktop, ogni dispositivo deve includere tutti questi elementi, che non possono essere modificati dagli amministratori senza una richiesta a Microsoft Managed Desktop.

I profili dispositivo vengono visualizzati al livello superiore successivo. A ogni dispositivo Desktop gestito Microsoft deve essere assegnato un solo profilo. Gli amministratori possono scegliere il profilo assegnato a un dispositivo.

A un livello ancora superiore sono disponibili [ulteriori personalizzazioni.](customizing.md) Ogni dispositivo può avere una o più personalizzazioni (o no). Possono modificare un livello di livello inferiore (profili di dispositivo o la configurazione di base) o essere una richiesta completamente nuova che viene a più livelli rispetto alla configurazione standard.

Nella parte superiore sono presenti modifiche personalizzate, ad esempio dettagli di rete o applicazioni. Un dispositivo può avere un numero qualsiasi di queste modifiche, che non sono gestite o bloccate da Microsoft Managed Desktop.


## <a name="device-profile-details"></a>Dettagli profilo dispositivo

Nella tabella seguente vengono riepilogate le impostazioni e i relativi valori predefiniti per ogni impostazione configurata dai profili di dispositivo. Queste impostazioni sono configurate con OMA-URIs profili di configurazione personalizzati in Microsoft Endpoint Manager.

| Funzionalità | Dati sensibili | Power User | Standard |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **Blocca archiviazione esterna**                                                                                                                               | Sì                       | Sì                   | No                   |
| **[Livello blocco cloud](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | Alta                      | Alta                  | Alta                 |
| **Disabilitare gli account Microsoft**                                                                                                                           | Sì                       | Sì                   | No                   |
| **Disabilitare OneDrive personale**                                                                                                                            | Sì                       | Sì                   | No                   |
| **Passare al desktop sicuro per l'elevazione**                                                                                                               | No                        | Sì                   | No                   |
| **Tag dispositivo Microsoft Defender per endpoint**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **Amministratore nel dispositivo?**                                                                                                                                 | No                        | Sì                   | No                   |
| **Profilo Autopilot**                                                                                                                                     | MMD Standard               | MMD Power User         | MMD Standard          |
| **AppLocker**                                                                                                                                            | Sì                       | No                    | No                   |
| **Blocca archivio pubblico**                                                                                                                                   | Sì                       | Sì                   | No                   |

Ogni profilo del dispositivo include anche questi elementi:

- Un gruppo di dispositivi Azure Active Directory (AAD) di appartenenza dinamica
- Un gruppo di dispositivi AAD di appartenenza statica
- Profilo di configurazione di Microsoft Endpoint Manager

> [!IMPORTANT]
> Non modificare direttamente l'appartenenza a questi gruppi. Utilizzare l'interfaccia come descritto in [Riassegnare profili](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitazioni

Puoi richiedere eccezioni ai profili di dispositivo e ai relativi dettagli come farei con qualsiasi altro criterio. Tenere presente che è possibile avere solo uno di ogni profilo di dispositivo nell'organizzazione di Azure Active Directory ("tenant"). Ad esempio, non puoi richiedere che il profilo del dispositivo dati sensibili disabiliti AppLocker solo per alcuni utenti. Tutti i dispositivi con il profilo dati sensibili devono avere la stessa configurazione.

Ogni dispositivo può avere un solo profilo. Se un determinato dispositivo viene usato da più utenti, tutti gli utenti di tale dispositivo avranno la stessa configurazione.
