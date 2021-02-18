---
title: Funzionalità di protezione in Azure Information Protection in distribuzione nei tenant esistenti
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Questo articolo illustra le modifiche da implementare alle funzionalità di protezione in Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe85a46e3f20cda62cd8a52bd5df92257f8fee57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286670"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Funzionalità di protezione in Azure Information Protection in distribuzione nei tenant esistenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Per facilitare il passaggio iniziale per la protezione delle informazioni, a partire da luglio 2018 tutti i tenant idonei per Azure Information Protection avranno le funzionalità di protezione di Azure Information Protection attivate per impostazione predefinita. Le funzionalità di protezione in Azure Information Protection in precedenza erano note in Office 365 come Rights Management o Azure RMS. Se l'organizzazione ha un piano di servizio di Office E3 o un piano di servizio superiore, è ora possibile iniziare a proteggere le informazioni tramite Azure Information Protection quando queste funzionalità vengono implementazioni.

## <a name="changes-beginning-july-1-2018"></a>Modifiche a partire dal 1° luglio 2018

A partire dal 1° luglio 2018, Microsoft abiliterà la funzionalità di protezione in Azure Information Protection per tutte le organizzazioni con uno dei seguenti piani di sottoscrizione:

- La crittografia dei messaggi di Office 365 è disponibile come parte di Office 365 E3 ed E5, Microsoft E3 ed E5, Office 365 A1, A3 e A5 e Office 365 G3 e G5. Non sono necessarie licenze aggiuntive per ricevere le nuove funzionalità di protezione basate su Azure Information Protection.

- È inoltre possibile aggiungere Azure Information Protection Piano 1 ai piani seguenti per ricevere le nuove funzionalità di crittografia dei messaggi di Office 365: Exchange Online Piano 1, Exchange Online Piano 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard o Office 365 Enterprise E1.

- Ogni utente che trae vantaggio dalla crittografia dei messaggi di Office 365 deve essere concesso in licenza per essere coperto dalla funzionalità.

- Per l'elenco completo, vedere le descrizioni del [servizio Exchange Online per](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) la crittografia dei messaggi di Office 365.

Gli amministratori tenant possono controllare lo stato di protezione nel portale di amministrazione di Office 365.

![Screenshot che mostra che la gestione dei diritti in Office 365 è attivata.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Perché stiamo apportando questa modifica?

La crittografia dei messaggi di Office 365 sfrutta le funzionalità di protezione in Azure Information Protection. Alla base dei recenti miglioramenti apportati alla crittografia dei messaggi di Office 365 e dei nostri investimenti più ampi per la protezione delle informazioni in Microsoft 365, stiamo rendendo più semplice per le organizzazioni attivare e usare le funzionalità di protezione, come in passato, le tecnologie di crittografia sono state difficili da configurare. Attivando le funzionalità di protezione in Azure Information Protection per impostazione predefinita, è possibile iniziare rapidamente a proteggere i dati sensibili.

## <a name="does-this-impact-me"></a>Questo influisce su di me?

Se l'organizzazione ha acquistato una licenza di Office 365 idonea, il tenant sarà intasato da questa modifica.

> [!IMPORTANT]
> Se si utilizza Active Directory Rights Management Services (AD RMS) nell'ambiente locale, è necessario rifiutare esplicitamente questa modifica o eseguire la migrazione ad Azure Information Protection prima di implementare questa modifica entro i 30 giorni successivi. Per informazioni su come rifiutare esplicitamente, vedere "Utilizzo AD RMS, come si rifiuta esplicitamente?" più avanti in questo articolo. Se si preferisce eseguire la migrazione, vedere [Migrazione da AD RMS ad Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>È possibile usare Azure Information Protection con Active Directory Rights Management Services (AD RMS)?

No. Non si tratta di uno scenario di distribuzione supportato. Senza eseguire i passaggi aggiuntivi di rifiuto esplicito, è possibile che alcuni computer inizino automaticamente a usare il servizio Azure Rights Management e si connettano anche al cluster AD RMS. Questo scenario non è supportato e ha risultati inaffidabili, quindi è importante rifiutare esplicitamente questa modifica entro i prossimi 30 giorni prima di implementare queste nuove funzionalità. Per informazioni su come rifiutare esplicitamente, vedere "Utilizzo AD RMS, come si rifiuta esplicitamente?" più avanti in questo articolo. Se si preferisce eseguire la migrazione, vedere [Migrazione da AD RMS ad Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Come è possibile sapere se si utilizza AD RMS?

Seguire queste istruzioni da Preparazione dell'ambiente per Azure Rights Management quando si dispone anche di [Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) per verificare se è stato distribuito AD RMS:

1. Sebbene facoltativa, la maggior parte delle distribuzioni AD RMS pubblica il punto di connessione del servizio (SCP) in Active Directory in modo che i computer di dominio possano individuare il cluster AD RMS.

   Utilizzare ADSI Edit per verificare se si dispone di un SCP pubblicato in Active Directory: CN=Configuration [nome server], CN=Services, CN=RightsManagementServices, CN=SCP

2. Se non si utilizza un SCP, i computer Windows che si connettono a un cluster AD RMS devono essere configurati per l'individuazione dei servizi sul lato client o il reindirizzamento delle licenze utilizzando il Registro di sistema di Windows: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .

Per ulteriori informazioni su queste configurazioni del Registro di sistema, vedere [Abilitazione](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) dell'individuazione dei servizi sul lato client tramite il Registro di sistema di Windows e [Reindirizzamento del traffico del server licenze.](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Utilizzo AD RMS, come posso rifiutare esplicitamente?

Per rifiutare esplicitamente la modifica imminente, completa questi passaggi:

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-IRMConfiguration utilizzando la sintassi seguente:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Cosa posso aspettarmi dopo che questa modifica è stata apportata?

Una volta abilitata, purché non sia stata rifiutata esplicitamente, è possibile iniziare a usare la nuova versione di Crittografia messaggi di Office 365, annunciata in [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) e che sfrutta le funzionalità di crittografia e protezione di Azure Information Protection.

![Screenshot that shows an OME protected message in Outlook on the web.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Per ulteriori informazioni sui nuovi miglioramenti, vedere Crittografia messaggi di [Office 365.](../../compliance/ome.md)
