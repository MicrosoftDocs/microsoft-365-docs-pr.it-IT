---
title: guida introduttiva Office 365 rete per la distribuzione di contenuti (rete CDN)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: guida introduttiva Office 365 rete per la distribuzione di contenuti (rete CDN)
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921595"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>guida introduttiva Office 365 rete per la distribuzione di contenuti (rete CDN)

Puoi usare il Office 365 rete per la distribuzione di contenuti **(rete CDN)** incorporato per ospitare asset statici (immagini, JavaScript, fogli di stile, file WOFF) per garantire prestazioni migliori per le pagine di SharePoint Online. La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza. Inoltre, il Office 365 rete CDN utilizza il protocollo HTTP/2 per migliorare la compressione e il pipelining HTTP. Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

Per informazioni più dettagliate, vedere [Use the Office 365 rete per la distribuzione di contenuti (rete CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>Il Office 365 rete CDN è disponibile solo per i tenant nel cloud di produzione (in tutto il mondo). I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente il Office 365 rete CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Usare lo strumento Diagnostica pagine per SharePoint per identificare gli elementi non rete CDN

Puoi usare Diagnostica pagine per l'estensione del **browser** degli strumenti di SharePoint per elencare facilmente le risorse nelle pagine di SharePoint Online che possono essere aggiunte a un'origine rete CDN pagina.

Lo **strumento Diagnostica pagine per SharePoint** è un'estensione del browser per il nuovo Microsoft Edge ( e i browser Chrome che analizzano sia il portale moderno di SharePoint Online che le pagine classiche del sito di https://www.microsoft.com/edge) pubblicazione. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](./page-diagnostics-for-spo.md).

Quando si esegue lo strumento Diagnostica pagine per SharePoint in una pagina di SharePoint Online, è possibile fare clic sulla scheda **Test** di diagnostica per visualizzare un elenco degli asset non ospitati dal rete CDN. Questi asset verranno elencati sotto l'intestazione **rete per la distribuzione di contenuti (rete CDN)** come illustrato nella schermata seguente.

![Diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

## <a name="cdn-overview"></a>rete CDN Panoramica

Il Office 365 rete CDN è progettato per ottimizzare le prestazioni per gli utenti distribuendo oggetti a cui si accede frequentemente come immagini e file javascript su una rete globale ad alta velocità, riducendo i tempi di caricamento delle pagine e fornendo l'accesso agli oggetti ospitati il più vicino possibile all'utente. Il rete CDN recupera gli asset da una posizione denominata _origine._ Un'origine può essere un SharePoint, una raccolta documenti o una cartella accessibile da un URL.

Il Office 365 rete CDN è separato in due tipi di base:

- **La rete CDN** pubblica è progettata per essere usata per JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) e per immagini non proprietarie come i loghi aziendali.
- **La rete CDN** privata è progettata per essere utilizzata per le immagini (PNG, JPG, JPEG e così via).

È possibile scegliere di avere origini pubbliche o private per l'organizzazione. La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due. Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna ha attributi e vantaggi univoci. Per ulteriori informazioni sulle origini di rete CDN pubbliche e private, vedere Scegliere se ogni origine [deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Come abilitare i servizi pubblici e privati rete CDN con la configurazione predefinita
Prima di apportare modifiche alle impostazioni rete CDN tenant, è necessario verificare che soddisfi i criteri di conformità, sicurezza e privacy dell'organizzazione.

Per impostazioni di configurazione più dettagliate o se è già stato abilitato rete CDN e si desidera aggiungere ulteriori posizioni (origini), vedere la sezione Configurare e configurare il Office 365 rete CDN utilizzando [SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Connessione al tenant tramite SharePoint Online Management Shell:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Per consentire all'organizzazione di utilizzare sia origini pubbliche che private con la configurazione predefinita, digitare il comando seguente:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

L'output di questi cmdlet dovrebbe essere simile al seguente:

![Output di Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Vedere anche

[Usare lo strumento Diagnostica pagine per SharePoint Online](./page-diagnostics-for-spo.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Reti per la distribuzione di contenuti](./content-delivery-networks.md)

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](./network-planning-and-performance.md)

[SharePoint Serie di prestazioni - Office 365 rete CDN video](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)