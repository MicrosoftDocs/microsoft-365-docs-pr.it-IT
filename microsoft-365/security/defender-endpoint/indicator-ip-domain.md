---
title: Creare indicatori per IP e URL/domini
ms.reviewer: ''
description: Creare indicatori per IP e URL/domini che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: ip, url, dominio, gestire, consentito, bloccato, bloccare, pulire, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841067"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Creare indicatori per IP e URL/domini 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender for Endpoint può bloccare ciò che Microsoft ritiene ip/URL dannosi, tramite Windows Defender SmartScreen per i browser Microsoft e tramite Protezione di rete per i browser non Microsoft o le chiamate effettuate all'esterno di un browser.

Il set di dati di intelligence per le minacce per questo è stato gestito da Microsoft.

Creando indicatori per INDIRIZZI IP e URL o domini, ora puoi consentire o bloccare INDIRIZZI IP, URL o domini in base alla tua intelligence sulle minacce. È possibile eseguire questa operazione tramite la pagina delle impostazioni o i gruppi di computer se si ritiene che alcuni gruppi siano più o meno a rischio di altri.

> [!NOTE]
> La notazione CIDR (Classless Inter-Domain Routing) per gli indirizzi IP non è supportata. 

### <a name="before-you-begin"></a>Prima di iniziare
È importante comprendere i prerequisiti seguenti prima di creare indicatori per IPS, URL o domini:
- L'url/ip consentiti e il blocco si basa su Defender per l'attivazione di Network Protection del componente endpoint in modalità blocco. Per ulteriori informazioni su Protezione di rete e istruzioni di configurazione, vedere [Enable network protection](enable-network-protection.md).
- La versione del client Antimalware deve essere 4.18.1906.x o successiva. 
- Supportato nei computer Windows 10 versione 1709 o successiva. 
- Verificare che **gli indicatori di rete personalizzati** siano abilitati Microsoft Defender Security Center > Impostazioni > funzionalità **avanzate.** Per ulteriori informazioni, vedere [Funzionalità avanzate.](advanced-features.md)
- Per il supporto degli indicatori in iOS, vedi [Configurare indicatori personalizzati.](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)


> [!IMPORTANT]
> Solo gli INDIRIZZI IP esterni possono essere aggiunti all'elenco degli indicatori. Non è possibile creare indicatori per gli IP interni.
> Per gli scenari di protezione Web, è consigliabile usare le funzionalità incorporate in Microsoft Edge. Microsoft Edge si avvale [di Protezione di rete](network-protection.md) per esaminare il traffico di rete e consente blocchi per TCP, HTTP e HTTPS (TLS). Se sono presenti criteri indicatore URL in conflitto, viene applicato il percorso più lungo. Ad esempio, il criterio indicatore URL `https:\\support.microsoft.com/en-us/office` ha la precedenza sul criterio indicatore URL `https:\\support.microsoft.com` .

> [!NOTE]
> Per tutti gli altri processi, gli scenari di protezione Web sfruttano Protezione di rete per l'ispezione e l'applicazione: 
> - IP è supportato per tutti e tre i protocolli
> - Sono supportati solo indirizzi IP singoli (nessun blocco CIDR o intervalli IP)
> - Gli URL crittografati (percorso completo) possono essere bloccati solo nei browser di prima parte (Internet Explorer, Edge)
> - Gli URL crittografati (solo FQDN) possono essere bloccati all'esterno dei browser di prima parte (Internet Explorer, Edge)
> - I blocchi di percorso URL completo possono essere applicati a livello di dominio e tutti gli URL non crittografati
 
> [!NOTE]
> Possono essere presenti fino a 2 ore di latenza (in genere meno) tra il momento in cui viene eseguita l'azione e l'URL e l'IP bloccati. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Creare un indicatore per IP, URL o domini dalla pagina delle impostazioni

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **indicatori**.  

2. Selezionare la **scheda Indirizzi IP o URL/Domini.**

3. Selezionare **Aggiungi elemento**.

4. Specificare i dettagli seguenti:
   - Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.
   - Azione: specificare l'azione da eseguire e fornire una descrizione.
   - Ambito: definire l'ambito del gruppo di computer.

5. Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**

## <a name="related-topics"></a>Argomenti correlati
- [Creare indicatori](manage-indicators.md)
- [Creare indicatori per file](indicator-file.md).
- [Creare indicatori in base ai certificati](indicator-certificates.md)
- [Gestire indicatori](indicator-manage.md)
