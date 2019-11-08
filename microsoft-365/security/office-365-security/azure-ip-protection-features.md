---
title: Funzionalità di protezione in Azure Information Protection in uscita per i tenant di Office 365 esistenti
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: Per facilitare il passaggio iniziale della protezione delle informazioni, a partire da luglio 2018 tutti i tenant idonei per la protezione delle informazioni di Azure disporranno delle funzionalità di protezione in Azure Information Protection attivate per impostazione predefinita. Le funzionalità di protezione di Azure Information Protection in precedenza erano note in Office 365 come Rights Management o Azure RMS. Se l'organizzazione dispone di un piano di servizio di Office E3 o di un piano di servizio superiore, è possibile iniziare a proteggere le informazioni tramite Azure Information Protection quando vengono implementate queste funzionalità.
ms.openlocfilehash: da10cdf9db7c17b2b9c9faadbcfbe953c7b625b2
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "38039125"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Funzionalità di protezione in Azure Information Protection in uscita per i tenant di Office 365 esistenti

Per facilitare il passaggio iniziale della protezione delle informazioni, a partire da luglio 2018 tutti i tenant idonei per la protezione delle informazioni di Azure disporranno delle funzionalità di protezione in Azure Information Protection attivate per impostazione predefinita. Le funzionalità di protezione di Azure Information Protection in precedenza erano note in Office 365 come Rights Management o Azure RMS. Se l'organizzazione dispone di un piano di servizio di Office E3 o di un piano di servizio superiore, è possibile iniziare a proteggere le informazioni tramite Azure Information Protection quando vengono implementate queste funzionalità.
  
## <a name="changes-beginning-july-1-2018"></a>Modifiche all'inizio del 1 ° luglio 2018

A partire dal 1 ° luglio 2018, Microsoft consentirà la funzionalità di protezione in Azure Information Protection per tutti i tenant di Office 365 che dispongono di uno dei seguenti piani di sottoscrizione:
  
- La crittografia dei messaggi di Office 365 è disponibile come parte di Office 365 E3 e E5, Microsoft E3 e E5, Office 365 a1, a3 e a5 e Office 365 G3 e G5. Non sono necessarie licenze aggiuntive per ricevere le nuove funzionalità di protezione alimentate da Azure Information Protection. 

- È inoltre possibile aggiungere Azure Information Protection Plan 1 ai piani seguenti per ricevere le nuove funzionalità di crittografia dei messaggi di Office 365: Exchange Online piano 1, Exchange Online piano 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium o Office 365 Enterprise E1.

- Tutti gli utenti che usufruiscono della crittografia dei messaggi di Office 365 devono essere concessi in licenza per essere coperti dalla caratteristica.

- Per l'elenco completo, vedere le [descrizioni dei servizi di Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) per la crittografia dei messaggi di Office 365. 

Gli amministratori tenant possono controllare lo stato di protezione nel portale di amministrazione di Office 365.
  
![Schermata che indica che Rights Management in Office 365 è attivato.](../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>Perché si sta facendo questo cambiamento?

La crittografia dei messaggi di Office 365 utilizza le funzionalità di protezione di Azure Information Protection. Al centro del recente miglioramento della crittografia dei messaggi di Office 365 e degli investimenti più ampi per la protezione delle informazioni in Microsoft 365, è più facile per le organizzazioni attivarsi e utilizzare le funzionalità di protezione, come storicamente, la crittografia le tecnologie sono state difficili da configurare. Attivando le funzionalità di protezione di Azure Information Protection per impostazione predefinita, è possibile iniziare rapidamente a proteggere i dati riservati.
  
## <a name="does-this-impact-me"></a>Questo ha un impatto su di me?

Se l'organizzazione di Office 365 ha acquistato una licenza di Office 365 idonea, il tenant avrà un impatto su questa modifica.
  
 **IMPORTANTE!** Se si utilizza Active Directory Rights Management Services (AD RMS) nell'ambiente locale, è necessario disattivarlo immediatamente o passare a Azure Information Protection prima di eseguire questa modifica entro i 30 giorni successivi. Per informazioni su come rifiutare l'opt-out, vedere "utilizzo di AD RMS, come è possibile escludere?" più avanti in questo articolo. Se si preferisce eseguire la migrazione, vedere [migrazione da ad RMS a Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>È possibile utilizzare Azure Information Protection con Active Directory Rights Management Services (AD RMS)?

No. Non si tratta di uno scenario di distribuzione supportato. Senza eseguire i passaggi aggiuntivi di disattivazione, alcuni computer potrebbero iniziare automaticamente a utilizzare il servizio Azure Rights Management e connettersi al cluster AD RMS. Questo scenario non è supportato e ha risultati inaffidabili, quindi è importante escludere questa modifica entro i 30 giorni successivi prima di eseguire queste nuove funzionalità. Per informazioni su come rifiutare l'opt-out, vedere "utilizzo di AD RMS, come è possibile escludere?" più avanti in questo articolo. Se si preferisce eseguire la migrazione, vedere [migrazione da ad RMS a Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>Come si fa a sapere se si utilizza AD RMS?

Utilizzare queste istruzioni per [preparare l'ambiente per Azure Rights Management quando si dispone anche di Active Directory Rights Management Services (ad RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) per verificare se è stata distribuita ad RMS: 
  
1. Anche se facoltativo, la maggior parte delle distribuzioni AD RMS pubblica il punto di connessione del servizio (SCP) in Active Directory in modo che i computer del dominio possano individuare il cluster AD RMS. 
  
Utilizzare ADSI Edit per verificare se è presente un SCP pubblicato in Active Directory: CN = Configuration [nome server], CN = Services, CN = RightsManagementServices, CN = SCP

2. Se non si utilizza un SCP, i computer Windows che si connettono a un cluster AD RMS devono essere configurati per l'individuazione del servizio sul server o il reindirizzamento delle licenze tramite il registro di sistema di Windows: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MSIPC\ServiceLocation o HKEY_ LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation
  
Per ulteriori informazioni su queste configurazioni del registro di sistema, vedere [Abilitazione dell'individuazione del servizio sul retro del client tramite il registro di sistema di Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) e [Reindirizzamento del traffico del server di gestione delle licenze](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Utilizzo di AD RMS, come si sceglie di escludere?

Per disattivare la modifica imminente, eseguire la procedura seguente:
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Eseguire il cmdlet Set-IRMConfiguration utilizzando la sintassi seguente:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Cosa è possibile aspettarsi dopo che è stata apportata questa modifica?

Una volta abilitata, se non è stata selezionata l'operazione, è possibile iniziare a usare la nuova versione della crittografia dei messaggi di Office 365 che è stata annunciata su [Microsoft ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) e utilizza le funzionalità di crittografia e protezione di Azure Information Protection.
  
![Schermata che visualizza un messaggio protetto da OME in Outlook sul Web.](../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
Per ulteriori informazioni sui nuovi miglioramenti, vedere crittografia dei [messaggi di Office 365](../../compliance/ome.md).
