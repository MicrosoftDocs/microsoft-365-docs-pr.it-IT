---
title: API di risposta di Microsoft Defender for Endpoint supportate
description: Informazioni sulle specifiche chiamate API di Microsoft Defender for Endpoint correlate alla risposta.
keywords: api di risposta, api del grafico, api supportate, attore, avvisi, dispositivo, utente, dominio, ip, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933770"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>API di query di Microsoft Defender for Endpoint supportate 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

Informazioni sulle chiamate API correlate alla risposta supportate che puoi eseguire e dettagli quali le intestazioni di richiesta necessarie e la risposta prevista dalle chiamate.

## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
Raccogliere un pacchetto di indagini | Esegui questa API per raccogliere un pacchetto di indagine da un dispositivo.
Isola dispositivo | Esegui questa API per isolare un dispositivo dalla rete.
Dispositivo unisolate | Rimuovere un dispositivo dall'isolamento. 
Limitare l'esecuzione del codice | Esegui questa API per contenere un attacco arrestando processi dannosi. Puoi anche bloccare un dispositivo e impedire l'esecuzione di successivi tentativi di programmi potenzialmente dannosi.
Annullamento dell'esecuzione del codice | Esegui questa operazione per annullare i criteri di restrizione delle applicazioni dopo aver verificato che il dispositivo compromesso è stato corretti.
Eseguire ricerca del virus | Avviare in remoto un'analisi antivirus per identificare e correggere il malware che potrebbe essere presente in un dispositivo compromesso.
Arrestare e mettere in quarantena un file |  Eseguire questa chiamata per interrompere l'esecuzione di processi, file in quarantena ed eliminare la persistenza, ad esempio le chiavi del Registro di sistema.
Esempio di richiesta | Esegui questa chiamata per richiedere un esempio di file da un dispositivo specifico. Il file verrà raccolto dal dispositivo e caricato in un archivio sicuro.
Blocca file | Eseguire questa API per impedire l'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto. 
Sblocca file | Consentire l'esecuzione di un file nell'organizzazione usando Antivirus Microsoft Defender.
Ottenere l'URI di firma di accesso condiviso del pacchetto | Esegui questa API per ottenere un URI che consenta il download di un pacchetto di analisi.
Get MachineAction object | Esegui questa API per ottenere l'oggetto MachineAction.
Get MachineActions collection | Esegui questa operazione per ottenere la raccolta MachineAction.
Get FileActions collection | Esegui questa API per ottenere la raccolta FileActions.
Get FileMachineAction object | Esegui questa API per ottenere l'oggetto FileMachineAction.
Get FileMachineActions collection | Esegui questa API per ottenere la raccolta FileMachineAction.
