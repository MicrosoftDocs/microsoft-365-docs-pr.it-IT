---
title: Aumentare la protezione dalle minacce per Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
description: Configurare Office 365 Advanced Threat Protection e proteggere i dati sensibili da tentativi di phishing, malware e altre minacce.
ms.openlocfilehash: 748868b07ac8759a66bac3c6b4165509270426a6
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224472"
---
# <a name="increase-threat-protection"></a>Protezione avanzata dalle minacce

In questo articolo vengono fornite informazioni utili per aumentare la protezione dell'abbonamento a Microsoft 365 per proteggersi da tentativi di phishing, malware e altre minacce. Tali raccomandazioni sono appropriate per le organizzazioni con un maggiore bisogno di sicurezza, come gli uffici legali e le cliniche sanitarie.

Prima di iniziare, controllare il Punteggio di Office 365 Secure score. Office 365 Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza e assegna un punteggio. Iniziare prendendo nota del punteggio corrente. Per aumentare il punteggio, completare le azioni consigliate in questo articolo. L'obiettivo non è quello di raggiungere il punteggio massimo, ma di essere a conoscenza delle opportunità di protezione dell'ambiente che non influiscono negativamente sulla produttività per gli utenti. 

Per ulteriori informazioni, vedere [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentare il livello di protezione da malware nella posta elettronica

L'ambiente Office 365 o Microsoft 365 include la protezione da malware. È possibile aumentare questa protezione bloccando gli allegati con i tipi di file comunemente utilizzati per il malware. Per aumentare la protezione antimalware nei messaggi di posta elettronica:
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali dell'account di amministratore. 
    
2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri** antimalware in **gestione minacce** \> **Anti-Malware**.
    
3. Fare doppio clic sul criterio predefinito per modificare il criterio a livello di società.
    
4. Selezionare **Impostazioni**.
    
5. In **filtro tipi di allegati comuni**selezionare **On**attivato. I tipi di file bloccati sono elencati nella finestra direttamente sotto questo controllo. Assicurarsi di aggiungere questi tipi di file:
   - Ade, ADP, Ani, Bas, bat, chm, cmd, com, cpl, CRT, HLP, HT, HTA, inf, ins, ISP, job, js, JSE, lnk, MDA, mdb, MDE, MDZ, MSC, MSI, msp, MST (PCD), reg, SCR, SCT, SHS, URL, VB, VBE, vbs, WSC, wsf, WSH, exe, PIF  <br/> 
   
   Se necessario, è possibile aggiungere o eliminare i tipi di file in un secondo momento.
    
6. Selezionare **Salva.**
    
Per ulteriori informazioni, vedere [anti-malware Protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Proteggere l'ambiente da ransomware

Ransomware limita l'accesso ai dati crittografando i file o bloccando gli schermi del computer. Tenta quindi di estorcere denaro dalle vittime chiedendo "riscatto", di solito in forma di cryptocurrencies come Bitcoin, in Exchange per l'accesso ai dati. 
  
Per proteggersi da ransomware, creare una o più regole del flusso di posta per bloccare le estensioni di file comunemente utilizzate per il ransomware. (Sono state aggiunte queste regole per [aumentare il livello di protezione contro il malware nel passaggio di posta elettronica](#raise-the-level-of-protection-against-malware-in-mail) ). È inoltre possibile avvisare gli utenti che ricevono questi allegati tramite posta elettronica.

Oltre ai file bloccati nel passaggio precedente, è consigliabile creare una regola per avvisare gli utenti prima di aprire gli allegati di file di Office che includono macro. Ransomware può essere nascosto all'interno delle macro, quindi avvisa gli utenti di non aprire questi file da persone che non conoscono.

Per creare una regola di trasporto della posta:
  
1. Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> e scegliere interfaccia di **Amministrazione** di \> **Exchange**.
    
2. Nella categoria **flusso di posta** , selezionare **regole**.
    
3. Selezionare **+** , quindi selezionare **Crea una nuova regola**.
    
4. Selezionare **altre opzioni** nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni. 
    
5. Applicare le impostazioni nella tabella seguente per la regola. Utilizzare i valori predefiniti per le altre impostazioni, a meno che non si desideri modificarli.
    
6. Selezionare **Salva**.
    
|**Impostazione**|**Avvisare gli utenti prima di aprire gli allegati dei file di Office**||
|:-----|:-----|:-----|
|Nome  <br/> |Regola anti-ransomware: avvisa gli utenti  <br/>  |
|Applica questa regola se. . .  <br/> |Qualsiasi allegato. . . l'estensione del file corrisponde. . .  <br/> |
|Specificare parole o frasi  <br/> |Aggiungere questi tipi di file:  <br/> dotm, docm, xlsm, sltm, xla, xlam, XLL, pptm, potm, ppam, ppsm, sldm  <br/>|
|Eseguire le operazioni seguenti. . .  <br/> |Invia una notifica al destinatario tramite messaggio  <br/> |
|Fornire il testo del messaggio  <br/> |Non aprire questi tipi di file da utenti che non si conoscono perché potrebbero contenere macro con codice dannoso.  <br/> |
   
Per altre informazioni, vedere:
  
- [Come gestire ransomware](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [Ripristinare il OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Interrompere l'inoltro automatico per la posta elettronica

Gli hacker che accedono alla cassetta postale di un utente possono rubare la posta impostando la cassetta postale in modo da inoltrare automaticamente la posta elettronica. Ciò può verificarsi anche senza la consapevolezza dell'utente. Per evitare che ciò accada, configurare una regola del flusso di posta. 
  
Per creare una regola di trasporto della posta, guardare [questo breve video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) o eseguire la procedura seguente:
  
1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare interfaccia di **Amministrazione** di \> **Exchange**.
    
2. Nella categoria **flusso di posta** , selezionare **regole**.
    
3. Selezionare **+** , quindi selezionare **Crea una nuova regola**.
    
4. Per visualizzare tutte le opzioni, selezionare **altre opzioni** nella parte inferiore della finestra di dialogo. 
    
5. Applicare le impostazioni nella tabella seguente. Utilizzare i valori predefiniti per le altre impostazioni, a meno che non si desideri modificarli.
    
6. Selezionare **Salva**.
    
|**Impostazione**|**Avvisare gli utenti prima di aprire gli allegati dei file di Office**|
|:-----|:-----|
|Nome  <br/> |Impedire l'inoltro automatico dei messaggi di posta elettronica ai domini esterni  <br/> |
|Applica questa regola se...  <br/> |Il mittente. . . è esterno/interno. . . All'interno dell'organizzazione  <br/> |
|Aggiungi condizione  <br/> |Le proprietà del messaggio. . . includere il tipo di messaggio. . . Inoltro automatico  <br/> |
|Eseguire le operazioni seguenti:  <br/> |Blocca il messaggio. . . rifiuta il messaggio e Includi una spiegazione.  <br/> |
|Fornire il testo del messaggio  <br/> |L'inoltro automatico della posta elettronica all'esterno dell'organizzazione è impedito per motivi di sicurezza.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Proteggere la posta elettronica da attacchi di phishing

Se sono stati configurati uno o più domini personalizzati per l'ambiente Office 365 o Microsoft 365, è possibile configurare la protezione anti-phishing mirata. La protezione anti-phishing ATP, parte di Office 365 Advanced Threat Protection, può aiutare a proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri attacchi di phishing. Se non è stato configurato un dominio personalizzato, non è necessario eseguire questa operazione.
  
Si consiglia di iniziare a utilizzare questa protezione creando un criterio per proteggere gli utenti più importanti e il dominio personalizzato. 

Per creare un criterio di anti-phishing ATP, guardare [questo breve video di formazione](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)o completare i passaggi seguenti:
  
1. Passare a [https://protection.office.com](https://protection.office.com). 
    
2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri**in **gestione minacce**.
    
3. Nella pagina **criterio** scegliere **ATP anti-phishing**.
    
4. Nella pagina **anti-phishing** selezionare **+ Crea**. Viene avviata una procedura guidata che consente di definire i criteri di anti-phishing.
    
5. Specificare il nome, la descrizione e le impostazioni del criterio come consigliato nella tabella seguente. Per ulteriori informazioni, vedere informazioni [sulle opzioni dei criteri di anti-phishing ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options). 
    
6. Dopo aver esaminato le impostazioni, fare clic su **crea questo criterio** o su **Salva**, a seconda dei casi.
    

|**Impostazione o opzione**<br/>|**Impostazione consigliata** <br/>|
|:-----|:-----|
|Nome  <br/> |Domain e la maggior parte del personale prezioso della campagna  <br/> |
|Descrizione  <br/> |Garantire che la maggior parte del personale importante e del nostro dominio non siano rappresentati.  <br/> |
|Aggiungere gli utenti da proteggere  <br/> |Seleziona **+ Aggiungi una condizione, il destinatario è**. Digitare i nomi utente oppure immettere l'indirizzo di posta elettronica del candidato, del responsabile della campagna e di altri membri del personale importanti. È possibile aggiungere fino a 20 indirizzi interni ed esterni che si desidera proteggere dalla rappresentazione.  <br/> |
|Aggiungere i domini da proteggere  <br/> |Selezionare **+ Aggiungi una condizione, il dominio del destinatario è**. Se ne è stata definita una, immettere il dominio personalizzato associato all'abbonamento a Microsoft 365. È possibile immettere più di un dominio.  <br/> |
|Scegli azioni  <br/> |Se la posta elettronica viene inviata da un utente rappresentato: scegliere **reindirizza messaggio a un altro indirizzo di posta elettronica**e quindi digitare l'indirizzo di posta elettronica dell'amministratore della sicurezza. ad esempio, *Alice <span> <span> @contoso. com*. Se i messaggi di posta elettronica vengono inviati da un dominio imitato: scegliere di mettere il **messaggio in quarantena**.  <br/> |
|Intelligence della cassetta postale  <br/> |Per impostazione predefinita, la funzione di intelligence della cassetta postale è selezionata quando si creano nuovi criteri anti-phishing. Per ottenere risultati ottimali, lasciare l’opzione **attiva**.  <br/> |
|Aggiungere mittenti e domini attendibili  <br/> |Qui è possibile aggiungere il proprio dominio o altri domini attendibili.  <br/> |
|Applicato a  <br/> |Selezionare **Il dominio del destinatario è**. In **Uno dei seguenti**, selezionare **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome del dominio, ad esempio *contoso. <span> <span> com*, nell'elenco, quindi selezionare **Aggiungi**. Scegliere **Fine**.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Protezione da allegati e file dannosi con gli allegati sicuri di ATP

Gli utenti inviano, ricevono e condividono regolarmente gli allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso solo guardando un messaggio di posta elettronica. La protezione avanzata dalle minacce di Office 365 include la protezione degli allegati sicuri di ATP, ma questa protezione non è attivata per impostazione predefinita. Si consiglia di creare una nuova regola per iniziare a usare questa protezione. Questa protezione si estende ai file in SharePoint, OneDrive e Microsoft teams.
  
Per creare un criterio degli allegati sicuri di ATP, guardare [questo breve video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o completare i passaggi seguenti:
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di amministratore. 
    
2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri**in **gestione minacce**.
    
3. Nella pagina criterio, scegliere **allegati sicuri ATP**.
    
4. Nella pagina allegati sicuri, applicare questa protezione in generale selezionando la casella di controllo **attiva ATP per SharePoint, OneDrive e Microsoft teams** . 
    
5. Selezionare questa **+** impostazione per creare un nuovo criterio. 
    
6. Applicare le impostazioni nella tabella seguente. 
    
7. Dopo aver esaminato le impostazioni, fare clic su **crea questo criterio** o su **Salva**, a seconda dei casi.
    

|**Impostazione o opzione**|**Impostazione consigliata** <br/>|
|:-----|:-----|
|Nome  <br/> |Blocca i messaggi di posta elettronica correnti e futuri con malware rilevato.  <br/> |
|Descrizione  <br/> |Blocca i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato.  <br/> |
|Save Attachments Unknown Malware Response  <br/> |Selezionare **blocca-blocca i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato**.  <br/> |
|Reindirizza l'allegato sul rilevamento  <br/> |Attiva reindirizzamento (selezionare questa casella) immettere l'account di amministratore o la configurazione di una cassetta postale per la quarantena.          Applicare la selezione precedente se la ricerca di malware per gli allegati non è stata eseguita o si verifica un errore (selezionare questa casella).  <br/> |
|Applicato a  <br/> |Il dominio del destinatario è. . . Selezionare il dominio.  <br/> |
   
Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing ATP di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).
  
## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Protezione da attacchi di phishing con collegamenti sicuri di ATP

A volte gli hacker nascondono siti Web dannosi nei collegamenti nei messaggi di posta elettronica o in altri file. Office 365 ATP Safe Links (ATP Safe Links), parte di Office 365 Advanced Threat Protection, può aiutare a proteggere l'organizzazione fornendo la verifica del tempo di clic degli indirizzi Web (URL) nei messaggi di posta elettronica e nei documenti di Office. La protezione è definita tramite i criteri collegamenti sicuri di ATP.
  
È consigliabile eseguire le operazioni seguenti:
  
- Modificare il criterio predefinito per aumentare la protezione.
    
- Aggiungere un nuovo criterio indirizzato a tutti i destinatari del dominio.
    
Per configurare i collegamenti sicuri di ATP, guardare [questo breve video di formazione](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)o completare i passaggi seguenti:
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di amministratore. 
    
2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri**in **gestione minacce**.
    
3. Nella pagina criterio, scegliere **collegamenti sicuri ATP**.
    
Per modificare il criterio predefinito:
  
1. Nella pagina collegamenti sicuri, in **criteri che si applicano all'intera organizzazione**, selezionare il criterio **predefinito** . 
    
2. In **impostazioni che si applicano al contenuto tranne che alla posta elettronica**, selezionare **Microsoft 365 Apps for Enterprise, Office per iOS e Android**.
    
3. Selezionare **Salva**. 
    
Per creare un nuovo criterio mirato a tutti i destinatari nel dominio:
  
1. Nella pagina collegamenti sicuri, in **criteri che si applicano all'intera organizzazione**, selezionare **+** per creare un nuovo criterio. 
    
2. Applicare le impostazioni elencate nella tabella seguente.
    
3. Selezionare **Salva**. 

|**Impostazione o opzione**|**Impostazione consigliata** <br/>|
|:-----|:-----|
|Nome  <br/> |Criteri dei collegamenti sicuri per tutti i destinatari del dominio  <br/> |
|Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi  <br/> |Selezionare **su URL verrà riscritto e controllato in base a un elenco di collegamenti dannosi noti quando l'utente fa clic sul collegamento**.  <br/> |
|Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile  <br/> |Selezionare questa casella.  <br/> |
|Applicato a  <br/> |Il dominio del destinatario è. . . Selezionare il dominio.  <br/> |
   
Per ulteriori informazioni, vedere [collegamenti sicuri ATP di Office 365](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Accedere all'interfaccia di amministrazione di Intune

1. Accedere al [portale di Azure](https://portal.azure.com/).

2. Selezionare **tutti i servizi** e digitare *Intune* nella **casella di ricerca**.

3. Dopo la visualizzazione dei risultati, selezionare l'inizio accanto a **Microsoft Intune** per renderlo preferito e facile da trovare in un secondo momento.

Oltre all'interfaccia di amministrazione, è possibile utilizzare Intune per registrare e gestire i dispositivi dell'organizzazione. Per ulteriori informazioni, vedere [capabilities by metodo di registrazione per i dispositivi di Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) e le [Opzioni di registrazione per i dispositivi gestiti da Intune](https://docs.microsoft.com/intune/enrollment-options).
