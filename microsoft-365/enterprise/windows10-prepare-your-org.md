---
title: Preparare l'organizzazione per Windows 10 Enterprise
description: Fornisce una guida di alto livello sui passaggi necessari per distribuire Windows 10 Enterprise sui PC come parte di Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, distribuzione
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 5deae85ae614079c23a373d4ecae7ce81aeb3fcd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071775"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Passaggio 1: preparare l'organizzazione per Windows 10 Enterprise

*Questo articolo si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Prima di aggiornare i dispositivi a Windows 10 Enterprise, prendere in considerazione quanto segue:

- **I domini devono essere aggiunti e verificati** <br>
  Con un abbonamento a Microsoft 365, viene visualizzato un nome di dominio predefinito che termina con onmicrosoft.com (ad esempio, contoso.onmicrosoft.com). La maggior parte delle organizzazioni preferisce utilizzare uno o più domini propri in modo che gli indirizzi di posta elettronica finiscano con il proprio nome di dominio (come username@contoso.com). Per utilizzare il proprio dominio, è necessario aggiungerlo a Microsoft 365 e verificare di possederlo. Si consiglia di aggiungere e verificare i domini ora in modo che siano pronti a partire ogni volta che si configurano i servizi di Microsoft 365, come la posta elettronica e Skype for business.
- **Non è necessario aggiungere gli utenti in questo momento** <br>
  Per utilizzare Microsoft 365 Services o installare prodotti Microsoft 365, gli utenti hanno bisogno di account in Microsoft 365 e hanno bisogno di licenze di prodotto. Il modo in cui si aggiungono utenti a Microsoft 365 dipende dal numero di utenti e dal fatto che si disponga attualmente di Active Directory locale. Se non si dispone di Active Directory (o si dispone di Active Directory, ma non si desidera sincronizzarlo con Microsoft 365), è possibile aggiungere gli utenti direttamente a Microsoft 365 e assegnare licenze, singolarmente o in blocco. <br>
  Se si dispone di Active Directory locale, è possibile [sincronizzarlo con microsoft 365](identity-add-user-accounts.md#identity-sync) per creare account utente in Azure ad, la directory cloud utilizzata da Microsoft 365. Con questo metodo, è possibile creare account per gli utenti e per i gruppi di sicurezza utilizzati per gestire le autorizzazioni per le risorse (come i documenti o le raccolte siti di SharePoint Online). La sincronizzazione di Active Directory con Microsoft 365 non consentirà di assegnare licenze agli utenti.
- **Non è necessario autorizzare gli utenti in questo momento** <br>
  Prima che gli utenti possano utilizzare Microsoft 365 Services o installare software dal portale Microsoft 365, sono necessarie licenze di prodotto. In qualità di amministratore globale o di gestione utenti, è possibile assegnare direttamente licenze di prodotti in Microsoft 365 singolarmente o in blocco. È inoltre possibile utilizzare le [licenze basate su gruppo](identity-use-group-management.md#identity-group-license) per assegnare automaticamente le licenze quando gli utenti vengono aggiunti a un gruppo specifico. 
- **È possibile installare Office 365 ProPlus separatamente** <br>
  L'ottenimento di una licenza di Microsoft 365 non installa automaticamente Office 365 ProPlus nei computer client. Per ulteriori informazioni, vedere la [fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) . 

## <a name="set-windows-diagnostics-data-level"></a>Impostare il livello di dati di diagnostica di Windows

Microsoft utilizza i dati di diagnostica per garantire la protezione dei dispositivi Windows identificando le tendenze di malware e altre minacce e per migliorare la qualità dei servizi di Windows e Microsoft. È necessario assicurarsi che il servizio di diagnostica sia abilitato a un livello minimo di base in tutti gli endpoint dell'organizzazione. *Per impostazione predefinita, questo servizio è abilitato e impostato sul livello avanzato.* Tuttavia, è buona norma controllare e verificare che ricevano dati dei sensori. L'impostazione di livelli tramite criteri sostituisce le impostazioni a livello di dispositivo. 

**Livelli di dati diagnostici del sistema operativo Windows 10**

È possibile configurare le impostazioni dei dati di diagnostica del sistema operativo utilizzando gli strumenti di gestione già in uso, ad esempio criteri di gruppo, MDM o provisioning di Windows. È anche possibile modificare manualmente le impostazioni utilizzando l'editor del registro di sistema. L'impostazione dei livelli di dati di diagnostica tramite un criterio di gestione sostituisce tutte le impostazioni a livello di dispositivo.

Utilizzare il valore appropriato nella tabella seguente quando si configurano i criteri di gestione.

| Level | Dati raccolti | Valore |
|:--- |:--- |:--- |
| Sicurezza | Solo dati di sicurezza. | 0 |
| Di base | Dati di sicurezza e dati di sistema e qualità di base. | 1 |
| Avanzato | Dati di sicurezza, dati di sistema di base e di qualità, nonché informazioni avanzate e dati di affidabilità avanzati. | 2 |
| Full | Dati di sicurezza, dati di sistema e qualità di base, approfondimenti e dati di affidabilità avanzati e dati di diagnostica completi. | 3 |

È possibile abilitare i dati di diagnostica tramite uno dei seguenti metodi:

* **Microsoft Intune** -se si prevede di utilizzare Intune per gestire i dispositivi, è possibile creare un criterio di configurazione per abilitare i dati di diagnostica configurando i criteri di sistema di <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> . Per ulteriori informazioni su come configurare i criteri di configurazione, vedere [gestire le impostazioni e le funzionalità nei propri dispositivi con i criteri di Microsoft Intune](https://aka.ms/intuneconfigpolicies).
* **Editor del registro** di sistema: è possibile utilizzare l'editor del registro di sistema per abilitare manualmente i dati di diagnostica su ogni dispositivo dell'organizzazione. In alternativa, è possibile scrivere uno script per modificare il registro di sistema. Se esiste già un criterio di gestione, ad esempio criteri di gruppo o MDM, questa impostazione del registro di sistema verrà ignorata.
* **Criteri di gruppo** : se non si prevede di registrare i dispositivi in Intune, è possibile utilizzare un oggetto Criteri di gruppo per impostare il livello di dati diagnostici dell'organizzazione.
* **Prompt dei comandi** : è possibile impostare i dati e il servizio di diagnostica di Windows 10 per iniziare automaticamente con il prompt dei comandi. Questo metodo è consigliabile se si sta testando il servizio solo in alcuni dispositivi. Se si Abilita l'avvio automatico del servizio con questo comando, non verrà configurato il livello di dati diagnostici. Se non è stato configurato un livello di dati di diagnostica tramite gli strumenti di gestione, il servizio opererà con il livello avanzato predefinito.

Per ulteriori informazioni sui dati di diagnostica di Windows, vedere [configurare i dati di diagnostica di Windows nell'organizzazione](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) , in base al metodo scelto.

Come checkpoint provvisorio, vedere i [criteri di completamento](windows10-exit-criteria.md#crit-windows10-step1) relativi a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Distribuire Windows 10 Enterprise per i dispositivi esistenti come aggiornamento sul posto](windows10-deploy-inplaceupgrade.md) |






