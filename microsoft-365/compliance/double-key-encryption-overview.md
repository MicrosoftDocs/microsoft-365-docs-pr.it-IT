---
title: Panoramica e domande frequenti sulla crittografia a chiave doppia
description: Domande frequenti sulla crittografia a chiave doppia per Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663061"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Domande frequenti sulla crittografia a chiave doppia

Hai una domanda sul funzionamento della crittografia a chiave doppia? Verificare la disponibilità di una risposta qui.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Che cos'è la crittografia a chiave doppia per Microsoft 365 (DKE)?

La crittografia a chiave doppia per Microsoft 365 consente ai clienti di proteggere i dati altamente sensibili per soddisfare requisiti specializzati. Consente ai clienti di mantenere il controllo completo delle chiavi di crittografia. Usa due chiavi per proteggere i dati; una chiave nel controllo e una seconda chiave archiviata in modo sicuro in Microsoft Azure. La visualizzazione dei dati protetti con la crittografia a chiave doppia richiede l'accesso a entrambe le chiavi. Poiché Microsoft può accedere solo a una di queste chiavi, i dati protetti rimangono inaccessibili a Microsoft, garantendo il controllo completo sulla privacy e la sicurezza dei dati.  

È possibile ospitare il servizio di crittografia a chiave doppia utilizzato per richiedere la chiave, in un percorso di propria scelta (server di gestione delle chiavi locale o nel cloud). Il servizio viene mantenuto come qualsiasi altra applicazione. La crittografia a chiave doppia consente di controllare l'accesso al servizio di crittografia a chiave doppia. È possibile archiviare i dati altamente sensibili in locale o spostali nel cloud. Puoi essere certo di impedire l'accesso a terze parti perché manteni il controllo completo della chiave. La crittografia a chiave doppia consente di archiviare i dati e la chiave nella stessa posizione.

DKE consente di soddisfare i requisiti normativi in diverse normative e standard, come il Regolamento generale sulla protezione dei dati (GDPR), l'Health Insurance Portability and Accountability Act (HIPAA), il Gramm-Leach-Bliley Act (GLBA), la legge sulla localizzazione dei dati in Russia – Legge federale n. 242-FZ, Federal Privacy Act 1988 in Australia e New Zealand's Privacy Act 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Posso usare la crittografia a chiave doppia Microsoft Office'etichettatura di riservatezza predefinita?

Dovrai usare il client di etichettatura unificata di Azure Information Protection per proteggere i documenti con la crittografia a chiave doppia. Attualmente, non è possibile usare l'Microsoft Office di riservatezza predefinita.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Quali app di Microsoft 365 posso usare con DKE?

È possibile utilizzare le etichette DKE per proteggere i documenti utilizzando le versioni desktop di Word, Excel e PowerPoint in Windows. Assicurarsi di usare *.12711 o versione successiva (versioni desktop di Word, PowerPoint ed Excel) in Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>In che modo la crittografia a chiave doppia è diversa dalla soluzione HYOK (Hold Your Own Key) esistente?

La crittografia a chiave doppia crittografa i dati con due chiavi. La chiave di crittografia è in tuo controllo e la seconda chiave è archiviata in Microsoft Azure, consentendoti di spostare i dati crittografati nel cloud. HYOK protegge il contenuto con una sola chiave e la chiave è sempre locale.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>I documenti crittografati a chiave doppia possono essere condivisi esternamente?

È possibile condividere documenti crittografati a chiave doppia con gli utenti in un tenant separato, purché tali utenti:

- Disporre dell'autorizzazione necessaria per accedere alla chiave nel servizio di crittografia a chiave doppia.

- Disporre dell'autorizzazione necessaria per accedere alla chiave in Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>Cosa succede ai documenti protetti con HYOK?

La distribuzione della crittografia a chiave doppia non influirà sulla configurazione HYOK esistente. Tuttavia, è consigliabile iniziare a usare la crittografia a chiave doppia in parallelo con HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>È possibile eseguire la crittografia a chiave doppia nell'ambiente non Microsoft air-gapped?

DKE non supporta questi ambienti perché il servizio richiede l'accesso a Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Dove è possibile archiviare i documenti crittografati a chiave doppia?

È possibile archiviare documenti crittografati a chiave doppia in locale o nel cloud. Nel cloud, è possibile spostare il contenuto crittografato in SharePoint Online e OneDrive for Business. Poiché Microsoft non ha accesso alla chiave privata, i dati crittografati rimangono opachi per Microsoft. Ciò significa anche che non è possibile visualizzare i documenti crittografati online in Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>In quali aree geografiche e lingue è disponibile la crittografia a chiave doppia? La crittografia a chiave doppia è disponibile in tutto il mondo?

Le etichette DKE vengono localizzate nelle stesse lingue delle altre etichette di riservatezza in Microsoft Information Protection. La crittografia a chiave doppia è disponibile in tutto il mondo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Posso convertire un'etichetta non DKE in un'etichetta DKE?

No. Non è possibile aggiungere DKE a un'etichetta dopo la sua creazione. Al contrario, è necessario scegliere **Usa** crittografia a chiave doppia e fornire l'URL del servizio di crittografia a chiave doppia quando si crea l'etichetta.

## <a name="how-do-i-roll-my-dke-keys"></a>Come posso eseguire il roll-to-roll delle chiavi DKE?

Per istruzioni su come rotolare (detta anche rotazione o ridenominazione della chiave) la chiave archiviata in Azure, vedere Operazioni per la chiave tenant di [Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)

Per [informazioni sulla creazione](double-key-encryption.md#tenant-and-key-settings) di una nuova chiave per il servizio DKE, vedere Impostazioni del tenant e delle chiavi.

Quando si crea una chiave, vengono impostati un nome e un GUID. Se quindi si ruota una chiave, si mantiene il record precedente con il nome e il GUID, ma si aggiunge un nuovo record con lo stesso nome ma guid diverso. La nuova chiave viene impostata come attiva in modo che l'API della chiave pubblica inizi a restituirla per la nuova crittografia. Entrambe le chiavi sono disponibili per la decrittografia, in modo che sia possibile decrittografare nuovo contenuto e contenuto precedente.
