---
title: Esempio di ricerca avanzata per Microsoft Defender per Office 365
description: Introduzione alla ricerca di minacce tramite posta elettronica tramite ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965145"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Esempio di ricerca avanzata per Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Iniziare a cercare le minacce tramite posta elettronica con la ricerca avanzata? Provare quanto segue:

La [guida introduttiva](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) dell'articolo [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) include blocchi di configurazione iniziali logici simili ai seguenti:

1. Configura tutto con "Anti" nel nome.
   - Antimalware
   - Anti-phishing
   - Protezione da posta indesiderata
2. Configura tutto con "Safe" nel nome.
   - Collegamenti sicuri
   - Allegati sicuri
3. Difendere i carichi di lavoro (ad esempio SharePoint Online, OneDrive e Teams).
4. Proteggi con eliminazione automatica a zero ore.

Oltre a un [collegamento](../office-365-security/protect-against-threats.md) per iniziare subito a eseguire la configurazione il primo giorno.

L'ultimo passaggio in **guida introduttiva** consiste nella protezione degli utenti con la **Zero-Hour Auto Purge**, anche nota come ZAP. Sapere se i provvedimenti per rimuovere con ZAP un messaggio sospetto o pericoloso dopo il recapito hanno avuto successo è molto importante.

Il passaggio rapido al linguaggio di query Kusto per rilevare problemi è un vantaggio derivante dalla convergenza di questi due centri sicurezza. I team di sicurezza possono monitorare i mancati problemi zap facendo i loro passi successivi [qui,](https://security.microsoft.com/advanced-hunting)sotto **Ricerca** \> **avanzata**.

1. Nella pagina Ricerca avanzata fare clic su **Query.**
1. Copiare la query seguente nella finestra Query.
1. Selezionare **Esegui query**.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="La pagina Ricerca avanzata (in Ricerca) con query selezionata nella parte superiore del pannello di query ed esecuzione di una query Kusto per acquisire le azioni ZAP negli ultimi 7 giorni.":::

I dati di questa query verranno visualizzati nel pannello Risultati sotto la query stessa. I risultati includono informazioni come 'DeviceName', 'AccountDisplayName' e 'ZapTime' in un set di risultati personalizzabile. È anche possibile esportare i risultati per i record. Se la query è di nuovo necessaria, selezionare **Salva** > **Salva con nome** e aggiungere la query all'elenco di query, condivise o della community.

## <a name="related-information"></a>Informazioni correlate
- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Panoramica - Ricerca avanzata](advanced-hunting-overview.md)
