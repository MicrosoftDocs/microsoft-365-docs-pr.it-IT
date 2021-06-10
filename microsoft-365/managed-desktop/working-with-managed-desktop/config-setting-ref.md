---
title: Informazioni di riferimento per le impostazioni configurabili per Microsoft Managed Desktop
description: Impostazione delle categorie per le impostazioni configurabili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917705"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Informazioni di riferimento per le impostazioni configurabili - Microsoft Managed Desktop

In questo argomento vengono elencate le categorie di impostazioni che i clienti possono configurare con Microsoft Managed Desktop. Ogni categoria di impostazioni include informazioni sui requisiti, sulle procedure consigliate e su come personalizzare la categoria di impostazioni. 

## <a name="desktop-background-picture"></a>Immagine di sfondo del desktop
È possibile personalizzare l'immagine di sfondo del desktop Microsoft Managed Desktop dispositivi dell'organizzazione. Puoi usarlo per applicare un marchio aziendale o un materiale di marketing. 

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per un'immagine di sfondo del desktop:
- Formato di file immagine .jpg, jpeg o .png
- Percorso file - Host in un percorso http (https) sicuro attendibile. 
- Non consentito: i percorsi http e di condivisione file (unc) non sono supportati. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizzare e distribuire l'immagine di sfondo del desktop

**Per aggiungere un'immagine di sfondo del desktop personalizzata**
1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. In **Impostazioni** di lavoro selezionare **Immagine di sfondo del desktop.** 
4. Immettere il percorso dell'immagine che si desidera utilizzare. 
5. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test. 

## <a name="browser-start-pages"></a>Pagine iniziale del browser
Le pagine iniziale del browser vengono aperte in singole schede quando gli utenti Microsoft Edge. Se si desidera semplificare agli utenti l'apertura di un set di siti utilizzati di frequente, aggiungere una pagina iniziale del browser per ogni sito. 

### <a name="requirements"></a>Requisiti

È necessario specificare il nome di dominio completo (FQDN) per i siti Intranet o Internet per le pagine iniziale del browser. Se i siti interni sono configurati, in modo che gli utenti sappiano che l'accesso a tali siti è consentito solo quando si è connessi alla rete interna quando si è in ufficio o quando si è connessi con una connessione VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizzare e distribuire le pagine iniziale del browser

**Per aggiungere una pagina iniziale del browser**
1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. Nell Impostazioni area di lavoro selezionare **Pagine iniziale del browser**.  
4. Selezionare **Aggiungi pagina iniziale.**
5. In **Aggiungi pagina iniziale del browser** immettere l'URL del sito che si desidera utilizzare e quindi selezionare Aggiungi pagina **iniziale.** 
6. Ripetere i passaggi da 1 a 5 per altre pagine di avvio del browser. 
7. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="enterprise-mode-site-list-location"></a>Enterprise di elenco siti in modalità avanzata

Se hai siti Web e app specifici che conosci hanno problemi di compatibilità con Microsoft Edge, puoi usare l'elenco dei siti in modalità Enterprise in modo che i siti Web si affortino automaticamente con Internet Explorer 11. Inoltre, se sai che i siti Intranet non funzioneranno correttamente con Microsoft Edge, puoi impostare tutti i siti Intranet in modo che vengano aperti automaticamente con Internet Explorer 11. L'Enterprise significa che puoi continuare a usare Microsoft Edge come browser predefinito, garantendo al contempo che le tue app continuino a funzionare su Internet Explorer 11. Per ulteriori informazioni sugli elenchi di siti in modalità [Enterprise,](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)vedere Enterprise Mode and Enterprise Mode Site Lists . 

Puoi specificare una posizione https:// o la posizione per una condivisione interna in cui hai ospitato l'elenco dei siti in modalità Enterprise. 

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per il file elenco siti in modalità Enterprise:
- Formato di file - File XML che soddisfa i [requisiti dei file](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Percorso file - File host in un percorso https interno. 
- Non consentito : l'hosting in una condivisione file interna, ad *esempio //sharename*, non è consentito

### <a name="best-practices"></a>Procedure consigliate

Queste procedure consigliate sono offerte per aiutare i clienti a prendere decisioni per modernizzare l'infrastruttura IT:
- **Scegliere un numero limitato** di siti: Microsoft Managed Desktop utilizza Microsoft Edge browser preferito per migliorare la sicurezza complessiva per l'organizzazione e l'usabilità per gli utenti. La maggior parte dei siti in questo elenco è per le app Web legacy che necessitano di una versione precedente di un browser che non includerà altre caratteristiche di sicurezza. 
- **Considera un'alternativa:** considera un sito o un'app Web diversa che non richiede un browser meno recente. In caso contrario, è consigliabile aggiornare il sito in modo che possa utilizzare browser più nuovi. I browser più recenti usano la tecnologia più recente e migliorano la sicurezza.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizzare e distribuire un Enterprise elenco modalità sito

**Per aggiungere un percorso elenco modalità sito enterprise**

1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. **Nell'Impostazioni** di lavoro selezionare **Enterprise percorso elenco siti in modalità predefinita.** 
4. Immettere il percorso https per l'elenco dei siti. 
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

1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. In **Impostazioni** di lavoro selezionare **Siti attendibili** e quindi Aggiungi sito **attendibile.** 
4. In **Aggiungi sito attendibile** immettere l'URL, scegliere un'area di sicurezza e quindi **selezionare Aggiungi sito attendibile.** 
5. Ripetere i passaggi da 1 a 4 per ogni sito attendibile che si desidera aggiungere. 
6. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

**Per rimuovere un sito attendibile**

1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. In **Impostazioni** di lavoro selezionare **Siti attendibili**. 
4. Selezionare il sito che si desidera eliminare e quindi selezionare **Elimina.** 
5. Ripetere i passaggi da 1 a 4 per ogni sito attendibile che si desidera eliminare. 
6. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="proxy"></a>Proxy
È possibile gestire le impostazioni del proxy di rete per l'organizzazione. Aggiungere il server proxy e il numero di porta, quindi aggiungere le eccezioni del sito proxy. Microsoft Managed Desktop include un set di eccezioni proxy predefinite necessarie per il funzionamento del servizio. L'elenco di esclusione predefinito può essere modificato solo dal servizio Microsoft Managed Desktop predefinito.  Per ulteriori informazioni, vedere [Configurazione di rete per Microsoft Managed Desktop](../get-ready/network.md). 

Le eccezioni del sito proxy aggiunte nel portale Microsoft Managed Desktop vengono aggiunte alle eccezioni proxy predefinite incluse nel Microsoft Managed Desktop servizio. 

> [!NOTE]
> L'aggiornamento dell'elenco di eccezioni proxy predefinito è sempre prioritario rispetto alle distribuzioni dei clienti. Ciò significa che la distribuzione a fasi verrà sospesa se è presente una distribuzione per l'elenco di eccezioni proxy predefinito.  

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per le eccezioni del server proxy e del sito proxy:
- Deve essere un indirizzo del server e un numero di porta validi
- Gli URL devono essere un sito http valido 

### <a name="customize-and-deploy-proxies"></a>Personalizzare e distribuire proxy

**Per aggiungere una singola eccezione del sito proxy**

1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. **Nell Impostazioni** workspace selezionare **Proxy.** 
4. Immettere indirizzo **e** **numero di porta** per il server proxy, quindi selezionare Aggiungi eccezione **proxy.** 
5. Immettere l'URL di un sito http valido e quindi selezionare **Aggiungi eccezione proxy.** 
6. Ripetere i passaggi da 1 a 5 per ogni sito attendibile che si desidera aggiungere. 
7. Selezionare **Distribuzione a fasi** per salvare le modifiche e distribuirle nel gruppo Test.

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni configurabili](config-setting-overview.md) 
- [Distribuire impostazioni configurabili](config-setting-deploy.md)