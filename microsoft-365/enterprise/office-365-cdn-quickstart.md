---
title: Guida introduttiva di rete per la distribuzione di contenuti (CDN) di Office 365
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
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Guida introduttiva di rete per la distribuzione di contenuti (CDN) di Office 365
ms.openlocfilehash: 8a8152c749306ed5247e92d4bc2c6a58e7a1c6cd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696056"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Guida introduttiva di rete per la distribuzione di contenuti (CDN) di Office 365

È possibile utilizzare la **rete di distribuzione dei contenuti (CDN) di Office 365** per ospitare risorse statiche (immagini, JavaScript, fogli di stile, file di WOFF) per offrire prestazioni migliori per le pagine di SharePoint Online. La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza. Inoltre, la rete CDN di Office 365 utilizza il protocollo HTTP/2 per migliorare la compressione e il pipelining HTTP. Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

Per informazioni più dettagliate, vedere [use the Office 365 Content Delivery Network (CDN) con SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>La rete CDN di Office 365 è disponibile solo per i tenant nel cloud di produzione (tutto il mondo). Gli inquilini del governo degli Stati Uniti, le nuvole cinesi e tedesche attualmente non supportano la rete CDN di Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Utilizzare lo strumento page Diagnostics for SharePoint per identificare gli elementi non presenti nella rete CDN

È possibile utilizzare l'estensione del browser di **diagnostica pagine per SharePoint Tool** per elencare facilmente le risorse nelle pagine di SharePoint Online che è possibile aggiungere a un'origine CDN.

Lo **strumento page Diagnostics for SharePoint** è un'estensione del browser per il nuovo Microsoft Edge ( https://www.microsoft.com/edge) e i browser Chrome che analizzano sia il portale moderno di SharePoint Online che le pagine del sito di pubblicazione classiche. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](https://aka.ms/perftool).

Quando si esegue lo strumento page Diagnostics for SharePoint in una pagina di SharePoint Online, è possibile fare clic sulla scheda **test diagnostici** per visualizzare un elenco di risorse che non sono ospitate dalla rete CDN. Tali risorse verranno elencate sotto la casella di **controllo della rete di distribuzione del contenuto (CDN)** , come illustrato nella schermata seguente.

![Diagnostica pagina](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

## <a name="cdn-overview"></a>Panoramica della rete CDN

La rete CDN di Office 365 è progettata per ottimizzare le prestazioni per gli utenti distribuendo oggetti spesso accessibili, come immagini e file JavaScript, in un network globale ad alta velocità, riducendo il tempo di caricamento delle pagine e consentendo l'accesso agli oggetti ospitati il più vicino possibile all'utente. La rete CDN recupera le risorse da una posizione denominata _Origin_. Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL.

La rete CDN di Office 365 è suddivisa in due tipi di base:

- La rete **CDN pubblica** è progettata per essere utilizzata per JS (JavaScript), CSS (Stylesheets), file dei tipi di carattere Web (WOFF, WOFF2) e immagini non proprietarie come loghi dell'azienda.
- La rete **CDN privata** è progettata per essere utilizzata per le immagini (PNG, jpg, JPEG e così via).

È possibile scegliere di avere origini sia pubbliche che private per la propria organizzazione. La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due. Entrambe le opzioni pubblico e privato offrono guadagni di prestazioni simili, ma ognuno ha attributi e vantaggi univoci. Per ulteriori informazioni sulle origini della rete CDN pubblica e privata, vedere [scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Come abilitare la rete CDN pubblica e privata con la configurazione predefinita
Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario verificare che soddisfi i criteri di conformità, sicurezza e privacy dell'organizzazione.

Per le impostazioni di configurazione più dettagliate oppure se è già stata abilitata la rete CDN e si desidera aggiungere altre posizioni (Origins), vedere la sezione configurare [e configurare la rete CDN di Office 365 tramite SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Connettersi al tenant tramite SharePoint Online Management Shell:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Per consentire all'organizzazione di utilizzare le origini pubbliche e private con la configurazione predefinita, digitare il comando seguente:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

L'output di questi cmdlet dovrebbe essere simile al seguente:

![Output di set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Vedere anche

[Utilizzare lo strumento di diagnostica delle pagine per SharePoint Online](https://aka.ms/perftool)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Reti per la distribuzione di contenuti](https://aka.ms/o365cdns)

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune)

[Serie di prestazioni di SharePoint-serie di video della rete CDN di Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
