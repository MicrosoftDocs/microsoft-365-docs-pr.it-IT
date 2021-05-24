---
title: Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determinare se il tenant e gli utenti soddisfano i requisiti, in modo da poter utilizzare la distribuzione centralizzata per distribuire Office componenti aggiuntivi.
ms.openlocfilehash: 25fe217a41274b6a239e4ee482ee105238465999
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635451"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione

La distribuzione centralizzata è il modo consigliato e più ricco di funzionalità per la maggior parte dei clienti per distribuire Office componenti aggiuntivi a utenti e gruppi all'interno dell'organizzazione. Se sei un amministratore, usa queste indicazioni per determinare se l'organizzazione e gli utenti soddisfano i requisiti in modo da poter usare la distribuzione centralizzata.

La distribuzione centralizzata offre i vantaggi seguenti:
  
- Un amministratore globale può assegnare un componente aggiuntivo direttamente a un utente, a più utenti tramite un gruppo o a tutti gli utenti dell'organizzazione.
    
- All'avvio dell Office appalto pertinente, il componente aggiuntivo viene scaricato automaticamente. Se il componente aggiuntivo supporta i comandi del componente aggiuntivo, il componente aggiuntivo verrà visualizzato automaticamente nella barra multifunzione all'interno dell Office applizione.
    
- I componenti aggiuntivi non vengono più visualizzati per gli utenti se l'amministratore disattiva o elimina il componente aggiuntivo o se l'utente viene rimosso da Azure Active Directory o da un gruppo a cui è assegnato il componente aggiuntivo.

La distribuzione centralizzata supporta tre piattaforme desktop Windows, Mac e Online Office app. La distribuzione centralizzata supporta anche iOS e Android (Outlook solo componenti aggiuntivi per dispositivi mobili).

La visualizzazione di un componente aggiuntivo per tutti gli utenti può richiedere fino a 24 ore.
  
## <a name="before-you-begin"></a>Prima di iniziare

La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino SKU Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium (e hanno eseguito l'accesso a Office usando l'ID dell'organizzazione) e disporre di cassette postali Exchange Online e Exchange Online attive. La directory di sottoscrizione deve essere in o federata per Azure Active Directory.
È possibile visualizzare i requisiti specifici per Office e Exchange di seguito oppure usare Verifica compatibilità [distribuzione centralizzata.](#centralized-deployment-compatibility-checker)

La distribuzione centralizzata non supporta quanto segue:
  
- Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013 
- Servizio di directory locale
- Distribuzione di componenti aggiuntivi in una Exchange locale
- Distribuzione di componenti aggiuntivi in SharePoint  
- Teams app
- Distribuzione di componenti aggiuntivi COM (Component Object Model) o Visual Studio Tools per Office (VSTO).
- Distribuzioni di Microsoft 365 che non includono Exchange Online ad esempio SKU: Microsoft 365 Apps for Business e Microsoft 365 Apps per Enterprise.

### <a name="office-requirements"></a>Office Requisiti

- Per Word, Excel e PowerPoint componenti aggiuntivi, gli utenti devono utilizzare uno dei componenti seguenti:
  - In un dispositivo Windows versione 1704 o successiva delle SKU di Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium.
  - In un Mac, versione 15.34 o successiva.

- Per Outlook, gli utenti devono utilizzare una delle opzioni seguenti: 
  - Versione 1701 o successiva delle SKU Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium.
  - Versione 1808 o successiva di Office Professional Plus 2019 o Office Standard 2019.
  - Versione 16.0.4494.1000 o successiva di Office Professional Plus 2016 (MSI) o Office Standard 2016 (MSI)\*
  - Versione 15.0.4937.1000 o successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*
  - Versione 16.0.9318.1000 o successiva di Office 2016 per Mac 
- Versione 2.75.0 o successiva di Outlook mobile per iOS 
- Versione 2.2.145 o successiva di Outlook mobile per Android 
    
    *Le versioni MSI Outlook i componenti aggiuntivi installati dall'amministratore nella barra multifunzione Outlook appropriata, non nella sezione "Componenti aggiuntivi".

### <a name="exchange-online-requirements"></a>Exchange Online requisiti

Microsoft Exchange i manifesti dei componenti aggiuntivi all'interno del tenant dell'organizzazione. L'amministratore che distribuisce i componenti aggiuntivi e gli utenti che ricevono tali componenti aggiuntivi devono essere in una versione di Exchange Online che supporti l'autenticazione OAuth.
  
Contattare l'amministratore di Exchange dell'organizzazione per sapere quale configurazione è in uso. La connettività OAuth per ogni utente può essere verificata usando il cmdlet di PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity). 


### <a name="centralized-deployment-compatibility-checker"></a>Verifica compatibilità distribuzione centralizzata

Utilizzando Verifica compatibilità distribuzione centralizzata, è possibile verificare se gli utenti del tenant sono impostati per l'utilizzo della distribuzione centralizzata per Word, Excel e PowerPoint. Verifica compatibilità non è necessario per il supporto di Outlook. Scaricare Verifica compatibilità [qui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Eseguire Verifica compatibilità
  
1. Avviare una finestra PowerShell.exe elevata.
    
2. Eseguire il comando riportato di seguito:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Eseguire il **comando Invoke-CompatabilityCheck:**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Questo comando richiede di specificare  *_TenantDomain,_* ad esempio *TailspinToysIncorporated.onmicrosoft. </span> com*)  *_e Le credenziali TenantAdmin_* (usare le credenziali di amministratore globale) e quindi richiede il consenso.
    
   > [!NOTE]
   > A seconda del numero di utenti nel tenant, la verifica potrebbe richiedere minuti o ore. 
  
Al termine dell'esecuzione dello strumento, viene generato un file di output in formato CSV (valori separati da virgola). Il file viene salvato in **C:\windows\system32** per impostazione predefinita. Il file di output contiene le informazioni seguenti:
  
- Nome utente
    
- ID utente (indirizzo di posta elettronica dell'utente)
    
- Distribuzione centralizzata pronta: se gli elementi rimanenti sono veri
    
- Office piano - Piano di Office per cui sono concessi in licenza
    
- Office attivato: se Office è stato attivato
    
- Cassetta postale supportata: se la cassetta postale è abilitata per OAuth

> [!NOTE]
> L'autenticazione a più fattori non è supportata quando si utilizza il modulo PowerShell per la distribuzione centrale.
  
## <a name="user-and-group-assignments"></a>Assegnazioni di utenti e gruppi

La funzionalità distribuzione centralizzata attualmente supporta la maggior parte dei gruppi supportati da Azure Active Directory, inclusi Microsoft 365, liste di distribuzione e gruppi di sicurezza.
  
> [!NOTE]
> I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati. 
  
La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e a tutti gli utenti del tenant. La distribuzione centralizzata supporta gli utenti in gruppi di primo livello o in gruppi senza gruppi padre, ma non gli utenti in gruppi annidati o in gruppi con gruppi padre.
   
Esaminare l'esempio seguente, in cui Valeria, Pupetta e il gruppo Reparto vendite vengono assegnati a un componente aggiuntivo. Reparto vendite costa occidentale è un gruppo annidato, quindi Gianni e Albertino non sono assegnati a un componente aggiuntivo.
  
![Diagramma del reparto vendite](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Scoprire se un gruppo contiene gruppi annidati

Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook. Se si immette il nome del gruppo nel campo **A** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi annidati. Nell'esempio seguente la scheda **Membri** della scheda contatto di Outlook per il gruppo di test non visualizza utenti e contiene solo due sottogruppi. 
  
![Scheda Membri della Outlook contatto](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
È possibile eseguire la query opposta risolvendo il gruppo per vedere se è un membro di un gruppo. Nell'esempio seguente nella scheda **Appartenenza** della scheda contatto di Outlook si vede che il sottogruppo 1 è un membro del gruppo di test. 
  
![Scheda Appartenenza della scheda Outlook contatto](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
In alternativa, è possibile usare l'API di Azure Active Directory Graph per eseguire query per trovare l'elenco dei gruppi all'interno di un gruppo. Per altre informazioni, vedere [Operazioni su gruppi | Riferimento API Graph](/previous-versions/azure/ad/graph/api/groups-operations).
  
### <a name="contacting-microsoft-for-support"></a>Contattare Microsoft per assistenza

Se l'utente o gli utenti riscontrano problemi durante il caricamento del componente aggiuntivo durante l'utilizzo di app Office per il Web (Word, Excel e così via), distribuite centralmente, potrebbe essere necessario contattare il supporto Tecnico Microsoft ([informazioni](../../business-video/get-help-support.md)su come ). Fornire le informazioni seguenti sull'ambiente Microsoft 365 nel ticket di supporto.
  
|**Piattaforma**|**Informazioni di debug**|
|:-----|:-----|
|Office  <br/> | Log di Charles/Fiddler  <br/>  ID tenant ( [informazioni](/onedrive/find-your-office-365-tenant-id.md))  <br/>  CorrelationID. Visualizzare l'origine di una delle pagine di Office e cercare il valore id correlazione e inviarlo al supporto:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Rich client (Windows, Mac)  <br/> | Log di Charles/Fiddler  <br/>  Numeri di build dell'app client (preferibilmente come screenshot da **File/Account)**  <br/> |

## <a name="related-content"></a>Contenuto correlato

[Distribuire componenti aggiuntivi nell'interfaccia di amministrazione](../manage/manage-deployment-of-add-ins.md) (articolo)\
[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](manage-addins-in-the-admin-center.md) (articolo)\
[Domande frequenti sulla distribuzione centralizzata](../manage/centralized-deployment-faq.md) (articolo)\
[Aggiornare il Microsoft 365 per gli utenti aziendali al client Office](../setup/upgrade-users-to-latest-office-client.md) più recente (articolo)
 