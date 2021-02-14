---
title: Informazioni di riferimento per le impostazioni configurabili per Microsoft Managed Desktop
description: Impostazione delle categorie per le impostazioni configurabili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c7c7d75fad58cab0cd6d19a16a97667ea3641a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104489"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Informazioni di riferimento per le impostazioni configurabili - Microsoft Managed Desktop

In questo argomento vengono elencate le categorie di impostazioni che i clienti possono configurare con Microsoft Managed Desktop. Ogni categoria di impostazione include informazioni sui requisiti, procedure consigliate e su come personalizzare la categoria di impostazioni. 

## <a name="desktop-background-picture"></a>Immagine di sfondo del desktop
È possibile personalizzare l'immagine di sfondo del desktop per i dispositivi Microsoft Managed Desktop nell'organizzazione. Puoi usare questa opzione per applicare un marchio aziendale o un materiale di marketing. 

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per un'immagine di sfondo del desktop:
- Formato di file immagine - jpg, jpeg o png
- Percorso file - Host in una posizione http (https) sicura attendibile. 
- Non consentito: i percorsi http e di condivisione file (unc) non sono supportati. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizzare e distribuire l'immagine di sfondo del desktop

**Per aggiungere un'immagine di sfondo personalizzata del desktop**
1. Accedi a [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) passa al menu **Dispositivi**
2. Cerca la sezione Microsoft Managed Desktop e seleziona **Impostazioni.**
3. **Nell'area di** lavoro Impostazioni selezionare **Immagine di sfondo del desktop.** 
4. Immettere la posizione dell'immagine che si desidera utilizzare. 
5. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test. 

## <a name="browser-start-pages"></a>Pagine di avvio del browser
Le pagine di avvio del browser si aprono in singole schede quando gli utenti avviano Microsoft Edge. Se si desidera consentire agli utenti di aprire facilmente un set di siti utilizzati di frequente, aggiungere una pagina iniziale del browser per ogni sito. 

### <a name="requirements"></a>Requisiti

È necessario specificare il nome di dominio completo (FQDN) per i siti Intranet o Internet per le pagine iniziale del browser. Se sono configurati siti interni, in modo che gli utenti sappiano che l'accesso a questi siti è consentito solo quando si è connessi alla rete interna quando si è in ufficio o quando si è connessi con una connessione VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizzare e distribuire le pagine di avvio del browser

**Per aggiungere una pagina iniziale del browser**
1. Accedi a [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) passa al menu **Dispositivi**
2. Cerca la sezione Microsoft Managed Desktop e seleziona **Impostazioni.**
3. **Nell'area di** lavoro Impostazioni selezionare **Pagine iniziale del browser.** 
4. Selezionare **Aggiungi pagina iniziale.**
5. Nella **pagina iniziale del browser aggiungi** immettere l'URL del sito che si desidera utilizzare e quindi selezionare Aggiungi pagina **iniziale.** 
6. Ripetere i passaggi da 1 a 5 per altre pagine di avvio del browser. 
7. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="enterprise-mode-site-list-location"></a>Posizione dell'elenco di siti in modalità Enterprise

Se hai siti Web e app specifici che sai avere problemi di compatibilità con Microsoft Edge, puoi usare l'elenco dei siti per la modalità Enterprise in modo che i siti Web si a aprino automaticamente con Internet Explorer 11. Inoltre, se sai che i siti Intranet non funzioneranno correttamente con Microsoft Edge, puoi impostare tutti i siti Intranet per l'apertura automatica con Internet Explorer 11. L'uso della modalità Enterprise significa che puoi continuare a usare Microsoft Edge come browser predefinito, garantendo al contempo che le tue app continuino a funzionare in Internet Explorer 11. Per altre informazioni sugli elenchi di siti per la modalità Enterprise, vedi Elenchi di siti per la modalità [Enterprise e per la modalità Enterprise.](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode) 

Puoi specificare una posizione https:// o la posizione per una condivisione interna in cui hai ospitato l'elenco dei siti per la modalità Enterprise. 

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per il file dell'elenco dei siti in modalità Enterprise:
- Formato di file - File XML che soddisfa i [requisiti dei file](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Percorso file - File host in un percorso https interno. 
- Non consentito: l'hosting in una condivisione file interna, ad *esempio //sharename,* non è consentito

### <a name="best-practices"></a>Procedure consigliate

Queste procedure consigliate sono offerte per aiutare i clienti a prendere decisioni per modernizzare l'infrastruttura IT:
- **Scegliere un numero limitato di** siti: Microsoft Managed Desktop usa Microsoft Edge come browser preferito per migliorare la sicurezza complessiva dell'organizzazione e l'usabilità per gli utenti. La maggior parte dei siti in questo elenco è per le app Web legacy che necessitano di una versione precedente di un browser che non includerà il maggior numero di funzionalità di sicurezza. 
- **Considerare un'alternativa:** considerare un sito o un'app Web diversa che non richiede un browser meno recente. In caso contrario, è consigliabile aggiornare il sito in modo che possa utilizzare browser più aggiornati. I browser più recenti usano la tecnologia più recente e migliorano la sicurezza.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizzare e distribuire il percorso dell'elenco modalità sito Enterprise

**Per aggiungere un percorso elenco modalità sito enterprise**

1. Accedi a [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) passa al menu **Dispositivi**
2. Cerca la sezione Microsoft Managed Desktop e seleziona **Impostazioni.**
3. **Nell'area di** lavoro Impostazioni selezionare **il percorso dell'elenco di siti in modalità Enterprise.** 
4. Immettere il percorso https per l'elenco di siti. 
5. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="trusted-sites"></a>Siti attendibili

I siti attendibili consentono di personalizzare le aree di sicurezza o la posizione in cui è possibile utilizzare un sito per siti diversi. Le aree di sicurezza includono: 
- Area 1 - Area Intranet locale
- Area 2 - Area siti attendibili
- Area 3 - Area Internet
- Area 4 - Area siti con restrizioni

### <a name="requirements"></a>Requisiti

Specificare il nome di dominio completo (FQDN) per i siti Intranet o Internet per ogni sito attendibile. 

### <a name="customize-and-deploy-trusted-sites"></a>Personalizzare e distribuire siti attendibili

**Per aggiungere un sito attendibile**

1. Accedi a [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) passa al menu **Dispositivi**
2. Cerca la sezione Microsoft Managed Desktop e seleziona **Impostazioni.**
3. **Nell'area** di lavoro Impostazioni selezionare **Siti attendibili** e quindi Aggiungi **sito attendibile.** 
4. In **Aggiungi sito attendibile** immettere l'URL, scegliere un'area di sicurezza e quindi **selezionare Aggiungi sito attendibile.** 
5. Ripetere i passaggi da 1 a 4 per ogni sito attendibile che si desidera aggiungere. 
6. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

**Per rimuovere un sito attendibile**

1. Accedi a [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) passa al menu **Dispositivi**
2. Cerca la sezione Microsoft Managed Desktop e seleziona **Impostazioni.**
3. **Nell'area di** lavoro Impostazioni selezionare **Siti attendibili.** 
4. Selezionare il sito che si desidera eliminare e quindi scegliere **Elimina.** 
5. Ripetere i passaggi da 1 a 4 per ogni sito attendibile che si desidera eliminare. 
6. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="proxy"></a>Proxy
È possibile gestire le impostazioni del proxy di rete per l'organizzazione. Aggiungere il server proxy e il numero di porta, quindi aggiungere le eccezioni del sito proxy. Microsoft Managed Desktop include un set di eccezioni proxy predefinite necessarie per il funzionamento del servizio. L'elenco di esclusione predefinito può essere modificato solo dal servizio Microsoft Managed Desktop.  Per ulteriori informazioni, vedere [Configurazione di rete per Microsoft Managed Desktop.](../get-ready/network.md) 

Le eccezioni del sito proxy aggiunte nel portale Microsoft Managed Desktop vengono aggiunte alle eccezioni proxy predefinite incluse nel servizio Microsoft Managed Desktop. 

> [!NOTE]
> L'aggiornamento dell'elenco di eccezioni proxy predefinito è sempre prioritario rispetto alle distribuzioni dei clienti. Ciò significa che la distribuzione a fasi verrà sospesa se è presente una distribuzione per l'elenco di eccezioni proxy predefinito.  

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per le eccezioni del server proxy e del sito proxy:
- Deve essere un indirizzo server e un numero di porta validi
- Gli URL devono essere un sito http valido 

### <a name="customize-and-deploy-proxies"></a>Personalizzare e distribuire proxy

**Per aggiungere una singola eccezione del sito proxy**

1. Accedi a [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) passa al menu **Dispositivi**
2. Cerca la sezione Microsoft Managed Desktop e seleziona **Impostazioni.**
3. **Nell'area di** lavoro Impostazioni selezionare **Proxy.** 
4. Immetti **l'indirizzo** **e il numero di porta** per il server proxy e quindi seleziona Aggiungi eccezione **proxy.** 
5. Immettere l'URL di un sito http valido e quindi selezionare **Aggiungi eccezione proxy.** 
6. Ripetere i passaggi da 1 a 5 per ogni sito attendibile che si desidera aggiungere. 
7. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni configurabili](config-setting-overview.md) 
- [Distribuire impostazioni configurabili](config-setting-deploy.md)
