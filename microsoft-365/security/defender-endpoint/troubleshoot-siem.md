---
title: Risolvere i problemi di integrazione degli strumenti SIEM in Microsoft Defender for Endpoint
description: Risolvere i problemi che possono verificarsi quando si usano gli strumenti SIEM con Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, siem, segreto client, segreto
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 9c4f3da57796903fc22314574f389bcdd92ca4b3
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311989"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Risolvere i problemi di integrazione degli strumenti SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Potrebbe essere necessario risolvere i problemi durante il pull dei rilevamenti negli strumenti SIEM.

In questa pagina vengono descritti i passaggi dettagliati per la risoluzione dei problemi che potrebbero verificarsi.


## <a name="learn-how-to-get-a-new-client-secret"></a>Informazioni su come ottenere un nuovo segreto client
Se il segreto client scade o se la copia fornita durante l'abilitazione dell'applicazione dello strumento SIEM è stata smarrita, sarà necessario ottenere un nuovo segreto.

1. Accedere al [portale di gestione di Azure](https://portal.azure.com).

2. Selezionare **Azure Active Directory**.

3. Selezionare il tenant.

4. Fare **clic su Registrazioni app**. Selezionare quindi l'applicazione nell'elenco delle applicazioni.

5. Seleziona **Certificati & segreti,** Fai clic su Nuovo segreto client, quindi fornisci una descrizione e specifica la durata della validità.

6. Fare clic su **Salva**. Viene visualizzato il valore della chiave.

7. Copiare il valore e salvarlo in un luogo sicuro.


## <a name="error-when-getting-a-refresh-access-token"></a>Errore durante il recupero di un token di accesso di aggiornamento
Se si verifica un errore durante il tentativo di ottenere un token di aggiornamento quando si usano l'API threat intelligence o gli strumenti SIEM, dovrai aggiungere l'URL di risposta per l'applicazione pertinente in Azure Active Directory.

1. Accedere al [portale di gestione di Azure](https://ms.portal.azure.com).

2. Selezionare **Azure Active Directory**.

3. Selezionare il tenant.

4. Fai **clic su Registrazioni app**. Selezionare quindi l'applicazione nell'elenco delle applicazioni.

5. Aggiungere l'URL seguente:
   - Per l'Unione europea: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Per il Regno Unito: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Per gli Stati Uniti:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .
 
6. Fare clic su **Salva**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Errore durante l'abilitazione dell'applicazione connettore SIEM
Se si verifica un errore durante il tentativo di abilitare l'applicazione connettore SIEM, controllare le impostazioni di blocco popup del browser. È possibile che la nuova finestra venga aperta quando si abilita la funzionalità.




>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Argomenti correlati
- [Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint](enable-siem-integration.md)
- [Configurare ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint](configure-arcsight.md)
- [Eseguire il pull dei rilevamenti agli strumenti SIEM](configure-siem.md)
- [Campi di Microsoft Defender per il rilevamento degli endpoint](api-portal-mapping.md)
- [Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST](pull-alerts-using-rest-api.md)
