---
title: Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Molte organizzazioni dispongono già di un processo per identificare e classificare le informazioni riservate mediante le proprietà di classificazione nell'Infrastruttura di classificazione file (FCI) di Windows Server, le proprietà dei documenti in SharePoint o le proprietà dei documenti applicate da un sistema di terze parti. Se è il caso della propria organizzazione, è possibile creare un criterio DLP in Office 365 che riconosce le proprietà che sono state applicate ai documenti da FCI di Windows Server o da un altro sistema, in modo che il criterio DLP possa essere applicato a documenti di Office con FCI specifica o altri valori di proprietà.
ms.openlocfilehash: 5f464c2918d7ea91fa5c65b28bc477ee7cc768e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084413"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Creare criteri di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà

In Office 365, è possibile utilizzare un criterio di prevenzione della perdita di dati (DLP) per identificare, controllare e proteggere le informazioni riservate. Molte organizzazioni dispongono già di un processo per identificare e classificare le informazioni riservate mediante le proprietà di classificazione nell'Infrastruttura di classificazione file (FCI) di Windows Server, le proprietà dei documenti in SharePoint o le proprietà dei documenti applicate da un sistema di terze parti. Se è il caso della propria organizzazione, è possibile creare un criterio DLP in Office 365 che riconosce le proprietà che sono state applicate ai documenti da FCI di Windows Server o da un altro sistema, in modo che il criterio DLP possa essere applicato a documenti di Office con FCI specifica o altri valori di proprietà.
  
![Diagramma con Office 365 e il sistema di classificazione esterno](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
Ad esempio, l'organizzazione potrebbe utilizzare FCI di Windows Server per identificare i documenti con le informazioni di identificazione personale (PII), come i numeri di previdenza sociale, e quindi classificare il documento impostando la proprietà **Informazioni di identificazione personale** su **Elevata**, **Moderata**, **Bassa**, **Pubblica** o **Non PII** in base al tipo e al numero di occorrenze di informazioni personali rilevate nel documento. In Office 365, è possibile creare un criterio DLP che identifica i documenti con tale proprietà impostata su valori specifici, come **Elevata** e **Media**, ed esegue un'azione, ad esempio un blocco dell'accesso ai file. Lo stesso criterio può disporre di un'altra regola che consente di eseguire un'azione diversa se la proprietà è impostata su **Bassa**, come l'invio di una notifica tramite posta elettronica. In questo modo, DLP in Office 365 si integra con Windows Server FCI e può contribuire alla protezione dei documenti di Office caricati o condivisi in Office 365 da file server basati su Windows Server.
  
Un criterio DLP cerca semplicemente una coppia di nome/valore di proprietà specifiche. È possibile utilizzare qualsiasi proprietà del documento, purché la proprietà disponga di una proprietà gestita corrispondente per la ricerca in SharePoint. Ad esempio, una raccolta siti di SharePoint potrebbe utilizzare un tipo di contenuto denominato **Report di andata e ritorno** con un campo obbligatorio denominato **Cliente**. Ogni volta che un utente crea un report di questo tipo, è necessario immettere il nome del cliente. Questa coppia di nome/valore della proprietà può essere utilizzata anche in un criterio DLP; ad esempio, se si desidera che una regola blocchi l'accesso al documento per gli utenti esterni quando il campo **Cliente** contiene **Contoso**.
  
Si noti che se si desidera applicare il criterio DLP al contenuto con specifiche etichette di Office 365, non è necessario eseguire la procedura seguente. In alternativa, viene illustrato come [utilizzare un'etichetta come condizione in un criterio DLP](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).
  
## <a name="before-you-create-the-dlp-policy"></a>Prima di creare il criterio DLP

Prima di utilizzare una proprietà di FCI di Windows Server o un'altra proprietà in un criterio DLP, è necessario creare una proprietà gestita nell'interfaccia di amministrazione di SharePoint. Ecco perché.
  
Esempi
  
Questo è importante perché la prevenzione della perdita di dati in Office 365 utilizza il crawler di ricerca per identificare e classificare le informazioni riservate nei siti e quindi archiviare tali informazioni in una parte sicura dell'indice di ricerca. Quando si carica un documento in Office 365, SharePoint crea automaticamente le proprietà sottoposte a ricerca per indicizzazione in base alle proprietà del documento. Tuttavia, per utilizzare una proprietà di FCI o di altro tipo in un criterio DLP, la proprietà sottoposta a ricerca per indicizzazione deve essere mappata a una proprietà gestita in modo che il contenuto con tale proprietà venga mantenuto nell'indice.
  
Per ulteriori informazioni sulla ricerca e sulle proprietà gestite, vedere [gestire lo schema di ricerca in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Passaggio 1: Caricare un documento con la proprietà necessaria in Office 365

Prima di tutto, è necessario caricare un documento con la proprietà cui si desidera fare riferimento nel criterio DLP. Office 365 rileva la proprietà e crea automaticamente la relativa proprietà sottoposta a ricerca per indicizzazione. Nel passaggio successivo è possibile creare una proprietà gestita e quindi eseguire il mapping della proprietà gestita a questa proprietà sottoposta a ricerca per indicizzazione.
  
### <a name="step-2-create-a-managed-property"></a>Passaggio 2: Creare una proprietà gestita

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
    
2. Nel riquadro di spostamento a sinistra, scegliere interfaccia di **Amministrazione** \> di **SharePoint**. Ci si trova ora nell'interfaccia di amministrazione di SharePoint.
    
3. Nella barra di spostamento a sinistra, scegliere **ricerca** \> nella pagina \> **Amministrazione ricerca** **gestire lo schema di ricerca**.
    
    ![pagina di amministrazione della ricerca nell'interfaccia di amministrazione di SharePoint](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. Nella \> pagina **proprietà gestite** **nuova proprietà gestita**.
    
    ![Pagina Proprietà gestite con il pulsante Nuova proprietà gestita evidenziato](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. Immettere un nome e una descrizione per la proprietà. Questo nome è ciò che apparirà nei criteri DLP.
    
6. Per **Tipo**, selezionare **Testo**. 
    
7. In **Caratteristiche principali**, selezionare **Disponibile per query** e **Recuperabile**.
    
8. \> In **mapping a proprietà sottoposte a ricerca per indicizzazione** **aggiungere un mapping**.
    
9. Nella finestra di dialogo Selezione proprietà sottoposta a **ricerca per indicizzazione** \> trovare e selezionare la proprietà \> **sottoposto**a ricerca per indicizzazione corrispondente alla proprietà di Windows Server FCI o ad altre proprietà che verranno utilizzate nel criterio DLP OK.
    
    ![finestra di dialogo per la selezione di proprietà sottoposte a ricerca per indicizzazione](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. Nella parte inferiore della pagina \> **OK**.
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Creare un criterio DLP che utilizza una proprietà FCI o un'altra proprietà

In questo esempio un'organizzazione utilizza FCI nei file server basati su Windows Server. in particolare, si utilizza la proprietà di classificazione FCI **denominata informazioni di identificazione personale** con i possibili valori di **alto**, **moderato**, **basso**, **pubblico**e **non di pii**. Ora desiderano sfruttare la classificazione FCI esistente nei criteri DLP in Office 365.
  
Prima di tutto, eseguire la procedura precedente per creare una proprietà gestita in SharePoint Online, che consente di eseguire il mapping alla proprietà sottoposta a ricerca per indicizzazione creata automaticamente dalla proprietà FCI.
  
Successivamente, si crea un criterio DLP con due regole che entrambe utilizzano le **proprietà del documento Condition contengono uno dei valori seguenti**:
  
- **Contenuto delle informazioni personali FCI-alto, moderato** La prima regola limita l'accesso al documento se la proprietà di classificazione FCI **identificabile personalmente** è uguale **ad alta** o **moderata** e il documento viene condiviso con persone esterne all'organizzazione. 
    
- **Contenuto delle informazioni personali FCI-basso** La seconda regola invia una notifica al proprietario del documento se la proprietà di classificazione FCI **identifica le informazioni** personali è uguale a **bassa** e il documento viene condiviso con persone esterne all'organizzazione. 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>Creare il criterio DLP tramite PowerShell

Tenere presente che le **proprietà del documento Condition contengono uno qualsiasi di questi valori** non è temporaneamente disponibile nell'interfaccia utente &amp; del Centro sicurezza e conformità, ma è comunque possibile utilizzare questa condizione tramite PowerShell. È possibile utilizzare i `New\Set\Get-DlpCompliancePolicy` cmdlet per l'utilizzo di un criterio DLP e utilizzare i `New\Set\Get-DlpComplianceRule` cmdlet con il `ContentPropertyContainsWords` parametro per aggiungere le proprietà del documento condition che **contengono uno dei valori seguenti**.
  
Per ulteriori informazioni su questi cmdlet, vedere cmdlet per il [centro &amp; sicurezza e conformità di Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).
  
1. [Connettersi al Centro sicurezza e conformità Office 365 utilizzando sessione remota di PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409).
    
2. Creare il criterio utilizzando `New-DlpCompliancePolicy`.
    
    Di seguito è riportato un esempio di PowerShell che consente di creare un criterio DLP che si applica a tutte le posizioni.
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. Creare le due regole `New-DlpComplianceRule`sopra descritte utilizzando, in cui una regola è per il valore **basso** e un'altra regola per i valori **alto** e **medio** . 
    
    Di seguito è riportato un esempio di PowerShell che consente di creare queste due regole. Si noti che le coppie nome/valore della proprietà sono racchiuse tra virgolette e il nome di una proprietà può specificare più valori separati da virgole senza spazi, ad esempio`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    Si noti che Windows Server FCI include molte proprietà predefinite, incluse **le informazioni di identificazione personale** utilizzate in questo esempio. I valori possibili per ogni proprietà possono essere diversi per ogni organizzazione. I valori **alto**, **medio**e **basso** utilizzati qui sono solo un esempio. Per l'organizzazione, è possibile visualizzare le proprietà di classificazione FCI di Windows Server con i relativi valori possibili in Gestione risorse file server nel server file basato su Windows Server. Per ulteriori informazioni, vedere [Create a Classification Property](http://go.microsoft.com/fwlink/p/?LinkID=627456).
    
Al termine, i criteri devono disporre di due nuove regole che entrambe utilizzano le **proprietà del documento contengono una qualsiasi delle condizioni di questi valori** . Si noti che questa condizione non viene visualizzata nell'interfaccia utente, anche se vengono visualizzate le altre condizioni, azioni e impostazioni. 
  
Una regola blocca l'accesso al contenuto dove la proprietà **Informazioni personali** è uguale a **Elevata** o **Moderata**. Una seconda regola invia una notifica sul contenuto dove la proprietà **Informazioni personali** è uguale a **Bassa**.
  
![Nuova finestra di dialogo dei criteri DLP con due regole appena create](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>Dopo aver creato il criterio DLP

Se si esegue la procedura descritta nelle sezioni precedenti, verrà creato un criterio DLP che rileverà rapidamente il contenuto con tale proprietà, ma solo se il contenuto è stato appena caricato (in modo che il contenuto sia indicizzato) oppure se il contenuto è obsoleto, ma è stato modificato in modo che il contenuto venga reindicizzato. .
  
Per rilevare il contenuto con tale proprietà ovunque, è possibile richiedere manualmente che la raccolta, il sito o una raccolta siti vengano reindicizzati in modo che il criterio DLP sia a conoscenza di tutto il contenuto con tale proprietà. In SharePoint Online, il contenuto viene automaticamente sottoposto a ricerca per indicizzazione in base a una pianificazione definita. Il crawler rileva il contenuto modificato dall'ultima ricerca per indicizzazione e aggiorna l'indice. Se è necessario che il criterio DLP protegga il contenuto prima della prossima ricerca per indicizzazione pianificata, è possibile eseguire questi passaggi.
  
> [!CAUTION]
> [!ATTENZIONE]  La reindicizzazione di un sito può provocare un carico eccessivo nel sistema di ricerca. Non reindicizzare il sito, a meno che lo scenario non lo richieda assolutamente. 
  
Per ulteriori informazioni, vedere [ricerca per indicizzazione e reindicizzazione manuale di un sito, di una raccolta o di un elenco](http://go.microsoft.com/fwlink/p/?LinkID=627457).
  
### <a name="re-index-a-site-optional"></a>Reindicizzare un sito (facoltativo)

1. Nel sito scegliere **Impostazioni** (icona a ingranaggi in alto a destra) \> **impostazioni del sito**.
    
2. In **ricerca**, scegliere **ricerca e** \> **reindicizzazione**disponibilità offline sito.
    
## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)
    
- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Inventario di tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)
    

