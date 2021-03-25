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
ms.openlocfilehash: 0196148c9dbf3ec769594d714524a3fd9e4d18fd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185958"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Creare indicatori per IP e URL/domini 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender for Endpoint può bloccare ciò che Microsoft ritiene ip/URL dannosi, tramite Windows Defender SmartScreen per i browser Microsoft e tramite Protezione di rete per browser non Microsoft o chiamate effettuate all'esterno di un browser.

Il set di dati di intelligence per le minacce per questo è stato gestito da Microsoft.

Creando indicatori per INDIRIZZI IP e URL o domini, ora puoi consentire o bloccare INDIRIZZI IP, URL o domini in base alla tua intelligence sulle minacce. È possibile eseguire questa operazione tramite la pagina delle impostazioni o i gruppi di computer se si ritiene che alcuni gruppi siano più o meno a rischio di altri.

> [!NOTE]
> La notazione CIDR (Classless Inter-Domain Routing) per gli indirizzi IP non è supportata. 

### <a name="before-you-begin"></a>Prima di iniziare
È importante comprendere i prerequisiti seguenti prima di creare indicatori per IPS, URL o domini:
- L'url/ip consentiti e il blocco si basa su Defender per l'attivazione di Network Protection del componente endpoint in modalità blocco. Per ulteriori informazioni su Protezione di rete e istruzioni di configurazione, vedere [Enable network protection](enable-network-protection.md).
- La versione del client Antimalware deve essere 4.18.1906.x o successiva. 
- Supportato nei computer con Windows 10 versione 1709 o successiva. 
- Assicurati che **gli indicatori di rete personalizzati** siano abilitati in Microsoft Defender Security Center > impostazioni > funzionalità **avanzate.** Per ulteriori informazioni, vedere [Funzionalità avanzate.](advanced-features.md)
- Per il supporto degli indicatori in iOS, vedi [Configurare indicatori personalizzati.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)


> [!IMPORTANT]
> Solo gli INDIRIZZI IP esterni possono essere aggiunti all'elenco degli indicatori. Non è possibile creare indicatori per gli IP interni.
> Per gli scenari di protezione Web, è consigliabile usare le funzionalità incorporate in Microsoft Edge. Microsoft Edge sfrutta Protezione di [rete per](network-protection.md) controllare il traffico di rete e consente blocchi per TCP, HTTP e HTTPS (TLS). Per tutti gli altri processi, gli scenari di protezione Web sfruttano Protezione di rete per l'ispezione e l'applicazione: <br>
> NOTA:
> - IP è supportato per tutti e tre i protocolli
> - Sono supportati solo indirizzi IP singoli (nessun blocco CIDR o intervalli IP)
> - Gli URL crittografati (percorso completo) possono essere bloccati solo nei browser di prima parte (Internet Explorer, Edge)
> - Gli URL crittografati (solo FQDN) possono essere bloccati all'esterno dei browser di prima parte (Internet Explorer, Edge)
> - I blocchi di percorso URL completo possono essere applicati a livello di dominio e tutti gli URL non crittografati
 
> [!NOTE]
> Possono essere presenti fino a 2 ore di latenza (in genere meno) tra il momento in cui viene eseguita l'azione e l'URL e l'IP bloccati. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Creare un indicatore per IP, URL o domini dalla pagina delle impostazioni

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.  

2. Selezionare la **scheda Indirizzi IP o URL/Domini.**

3. Selezionare **Aggiungi elemento**.

4. Specificare i dettagli seguenti:
   - Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.
   - Azione: specificare l'azione da eseguire e fornire una descrizione.
   - Ambito: definire l'ambito del gruppo di computer.

5. Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**

## <a name="related-topics"></a>Argomenti correlati
- [Creare indicatori](manage-indicators.md)
- [Creare indicatori per i file](indicator-file.md)
- [Creare indicatori in base ai certificati](indicator-certificates.md)
- [Gestire gli indicatori](indicator-manage.md)
