---
title: Guida introduttiva a Office 365 Content Delivery Network (CDN)
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
description: Guida introduttiva a Office 365 Content Delivery Network (CDN)
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921595"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Guida introduttiva a Office 365 Content Delivery Network (CDN)

È possibile utilizzare la rete **CDN (Content Delivery Network) di Office 365** incorporata per ospitare asset statici (immagini, JavaScript, fogli di stile, file WOFF) per garantire prestazioni migliori per le pagine di SharePoint Online. La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza. Inoltre, la rete CDN di Office 365 usa il protocollo HTTP/2 per migliorare la compressione e il pipelining HTTP. Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

Per informazioni più dettagliate, vedere [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

>[!NOTE]
>La rete CDN di Office 365 è disponibile solo per i tenant nel cloud di produzione (in tutto il mondo). I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente la rete CDN di Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Usare lo strumento Diagnostica pagine per SharePoint per identificare gli elementi non presenti nella rete CDN

È possibile utilizzare l'estensione del browser Strumenti di Diagnostica pagine per **SharePoint** per elencare facilmente gli asset nelle pagine di SharePoint Online che possono essere aggiunte a un'origine CDN.

Lo **strumento Diagnostica pagine per SharePoint** è un'estensione del browser per i nuovi browser Microsoft Edge e Chrome che analizza sia il portale moderno di SharePoint Online che le pagine classiche del sito di https://www.microsoft.com/edge) pubblicazione. Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni. Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](./page-diagnostics-for-spo.md).

Quando si esegue lo strumento Diagnostica pagine per SharePoint in una pagina di SharePoint Online, è possibile fare clic sulla scheda **Test** di diagnostica per visualizzare un elenco degli asset non ospitati dalla rete CDN. Questi asset verranno elencati sotto l'intestazione Controllo rete per la distribuzione di contenuti **(CDN),** come illustrato nello screenshot seguente.

![Diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.

## <a name="cdn-overview"></a>Panoramica della rete CDN

La rete CDN di Office 365 è progettata per ottimizzare le prestazioni per gli utenti distribuendo oggetti a cui si accede di frequente come immagini e file javascript su una rete globale ad alta velocità, riducendo i tempi di caricamento delle pagine e fornendo l'accesso agli oggetti ospitati il più vicino possibile all'utente. La rete CDN recupera gli asset da una posizione denominata _origine._ Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL.

La rete CDN di Office 365 è suddivisa in due tipi di base:

- **La rete CDN** pubblica è progettata per l'uso per JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) e per immagini non proprietarie come i logo aziendali.
- **La rete CDN** privata è progettata per essere utilizzata per le immagini (PNG, JPG, JPEG e così via).

È possibile scegliere di avere origini pubbliche o private per l'organizzazione. La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due. Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna ha attributi e vantaggi univoci. Per ulteriori informazioni sulle origini cdN pubbliche e private, vedere Scegliere se ogni origine [deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Come abilitare la rete CDN pubblica e privata con la configurazione predefinita
Prima di apportare modifiche alle impostazioni della rete CDN tenant, è necessario verificare che soddisfi i criteri di conformità, sicurezza e privacy dell'organizzazione.

Per impostazioni di configurazione più dettagliate o se la rete CDN è già stata abilitata e si desidera aggiungere ulteriori posizioni (origini), vedere la sezione Configurare e configurare la rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) tramite SharePoint Online Management Shell

Connettersi al tenant tramite SharePoint Online Management Shell:

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

[Serie di prestazioni di SharePoint - Serie video cdN di Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)