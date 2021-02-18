---
title: Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come utilizzare un criterio di prevenzione della perdita dei dati (DLP) per proteggere i documenti con proprietà da un sistema di terze parti.
ms.openlocfilehash: cf026e447ad1f0da3486a36dd5e36c52c09998cb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288229"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Creare criteri di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà

I criteri di prevenzione della perdita dei dati (DLP) di Microsoft 365 possono utilizzare le proprietà di classificazione o le proprietà degli elementi per identificare gli elementi sensibili. Ad esempio, è possibile utilizzare:

- Proprietà FCI (File Classification Infrastructure) di Windows Server
- Proprietà dei documenti di SharePoint
- proprietà dei documenti di sistema di terze parti

![Diagramma con Office 365 e il sistema di classificazione esterno](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

Ad esempio, l'organizzazione potrebbe utilizzare Windows Server FCI per identificare gli elementi con dati personali, ad esempio i numeri di previdenza sociale, e quindi classificare il documento impostando la proprietà **Informazioni** personali su **Alta,** **Moderata,**  **Bassa,** Pubblica o Non PIÙ **in** base al tipo e al numero di occorrenze dei dati personali trovati nel documento.

In Microsoft 365, è possibile creare un criterio DLP che identifichi i documenti la cui proprietà è impostata su valori specifici, ad esempio Alto e **Medio,** e quindi eseguire un'azione come il blocco dell'accesso a tali file.  Lo stesso criterio può disporre di un'altra regola che consente di eseguire un'azione diversa se la proprietà è impostata su **Bassa**, come l'invio di una notifica tramite posta elettronica. In questo modo, DLP si integra con FCI di Windows Server e consente di proteggere i documenti di Office caricati o condivisi in Microsoft 365 da file server basati su Windows Server.

Un criterio DLP cerca semplicemente una coppia di nome/valore di proprietà specifiche. È possibile utilizzare qualsiasi proprietà del documento, purché la proprietà disponga di una proprietà gestita corrispondente per la ricerca in SharePoint. Ad esempio, una raccolta siti di SharePoint potrebbe utilizzare un tipo di contenuto denominato **Report di andata e ritorno** con un campo obbligatorio denominato **Cliente**. Ogni volta che un utente crea un report di questo tipo, è necessario immettere il nome del cliente. Questa coppia nome/valore della proprietà può essere utilizzata anche in un criterio DLP, ad esempio  se si desidera una regola che blocchi l'accesso al documento per gli utenti guest quando il campo Cliente contiene **Contoso.**

Se si desidera applicare il criterio DLP al contenuto con etichette di Microsoft 365 specifiche, non seguire i passaggi qui descritti. Informazioni su come utilizzare [un'etichetta di conservazione come condizione in un criterio DLP.](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

## <a name="before-you-create-the-dlp-policy"></a>Prima di creare il criterio DLP

Prima di utilizzare una proprietà di FCI di Windows Server o un'altra proprietà in un criterio DLP, è necessario creare una proprietà gestita nell'interfaccia di amministrazione di SharePoint. Ecco perché.

Esempi

> [!NOTE]
> Assicurarsi di utilizzare un nome di proprietà gestita e non un nome di proprietà sottoposta a ricerca per indicizzazione durante la creazione di regole DLP utilizzando la `ContentPropertyContainsWords` condizione.

Questo è importante perché DLP utilizza il crawler di ricerca per identificare e classificare le informazioni riservate nei siti e quindi archiviare tali informazioni riservate in una parte sicura dell'indice di ricerca. Quando si carica un documento in Office 365, SharePoint crea automaticamente le proprietà sottoposte a ricerca per indicizzazione in base alle proprietà del documento. Tuttavia, per utilizzare una proprietà di FCI o di altro tipo in un criterio DLP, la proprietà sottoposta a ricerca per indicizzazione deve essere mappata a una proprietà gestita in modo che il contenuto con tale proprietà venga mantenuto nell'indice.

Per ulteriori informazioni sulla ricerca e sulle proprietà gestite, vedere [Gestire lo schema di ricerca in SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=627454)

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Passaggio 1: Caricare un documento con la proprietà necessaria in Office 365

Prima di tutto, è necessario caricare un documento con la proprietà cui si desidera fare riferimento nel criterio DLP. Microsoft 365 rileverà la proprietà e creerà automaticamente una proprietà sottoposta a ricerca per indicizzazione da essa. Nel passaggio successivo verrà creata una proprietà gestita e quindi la proprietà gestita verrà mappata a questa proprietà sottoposta a ricerca per indicizzazione.

### <a name="step-2-create-a-managed-property"></a>Passaggio 2: Creare una proprietà gestita

1. Accedere all'interfaccia di amministrazione di Microsoft 365.

2. Nel riquadro di spostamento sinistro scegliere **Interfaccia di amministrazione di** \> **SharePoint.** Ci si trova ora nell'interfaccia di amministrazione di SharePoint.

3. Nel riquadro di spostamento sinistro scegliere **ricerca nella** pagina di \> amministrazione **della** ricerca Gestisci schema \> **di ricerca.**

   ![pagina di amministrazione della ricerca nell'interfaccia di amministrazione di SharePoint](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. Nella pagina **Proprietà gestite** nuova \> **proprietà gestita.**

   ![Pagina Proprietà gestite con il pulsante Nuova proprietà gestita evidenziato](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. Immettere un nome e una descrizione per la proprietà. Questo nome è ciò che apparirà nei criteri DLP.

6. Per **Tipo**, selezionare **Testo**.

7. In **Caratteristiche principali**, selezionare **Disponibile per query** e **Recuperabile**.

8. In **Mapping alle proprietà sottoposte a ricerca per indicizzazione** aggiungere un \> **mapping.**

9. Nella **finestra** di dialogo di selezione delle proprietà sottoposte a ricerca per indicizzazione individuare e selezionare la proprietà sottoposta a ricerca per indicizzazione corrispondente alla proprietà FCI di Windows Server o a un'altra proprietà che verrà utilizzata nel criterio \> DLP \> **OK.**

   ![finestra di dialogo per la selezione di proprietà sottoposte a ricerca per indicizzazione](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. Nella parte inferiore della pagina \> **OK.**

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Creare un criterio DLP che utilizza una proprietà FCI o un'altra proprietà

In questo esempio, un'organizzazione usa FCI nei file server basati su Windows Server; in particolare, usano la proprietà di classificazione FCI denominata **Informazioni** personali con i possibili valori **High,** **Moderate,** **Low,** **Public** e **Not PII.** Ora vogliono usare la classificazione FCI esistente nei criteri DLP in Office 365.

Prima di tutto, eseguire la procedura precedente per creare una proprietà gestita in SharePoint Online, che consente di eseguire il mapping alla proprietà sottoposta a ricerca per indicizzazione creata automaticamente dalla proprietà FCI.

Successivamente, creano un criterio DLP con due regole che utilizzano entrambe la condizione Le proprietà del **documento contengono uno di questi valori:**

- **Contenuto FCI PII - Alto, Moderato** La prima regola limita l'accesso al documento se la proprietà di classificazione FCI **Informazioni** personali è uguale a **Alta** o **Moderata** e il documento viene condiviso con persone esterne all'organizzazione.

- **Contenuto FCI PII - Basso** La seconda regola invia una notifica al proprietario del documento se la proprietà di classificazione FCI **Informazioni** personali è uguale a **Bassa** e il documento viene condiviso con persone esterne all'organizzazione.

### <a name="create-the-dlp-policy-by-using-powershell"></a>Creare il criterio DLP tramite PowerShell

La condizione Le proprietà del **documento** contengono uno di questi valori temporaneamente non disponibili nell'interfaccia utente del Centro sicurezza e conformità, ma è comunque possibile usare questa condizione &amp; tramite PowerShell. È possibile utilizzare i cmdlet per utilizzare un criterio DLP e utilizzare i cmdlet con il parametro per aggiungere la condizione Le proprietà del documento contengono `New\Set\Get-DlpCompliancePolicy` `New\Set\Get-DlpComplianceRule` uno di questi `ContentPropertyContainsWords` **valori.**

Per ulteriori informazioni su questi cmdlet, vedere Cmdlet [del Centro sicurezza e &amp; conformità.](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)

1. [Connettersi al Centro &amp; sicurezza e conformità tramite Remote PowerShell](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. Creare il criterio utilizzando  `New-DlpCompliancePolicy` .

Questo PowerShell crea un criterio DLP che si applica a tutte le posizioni.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. Creare le due regole descritte in precedenza utilizzando , dove una regola è per il valore Basso e un'altra regola per i valori `New-DlpComplianceRule` **Alto** **e Moderato.** 

   Ecco un esempio di PowerShell che crea queste due regole. Le coppie nome/valore della proprietà sono racchiuse tra virgolette e un nome di proprietà può specificare più valori separati da virgole senza spazi, ad esempio  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   FCI di Windows Server include molte proprietà predefinite, tra cui **informazioni** personali utilizzate in questo esempio. I valori possibili per ogni proprietà possono essere diversi per ogni organizzazione. I **valori High,** **Moderate** **e Low** utilizzati qui sono solo un esempio. Per l'organizzazione, è possibile visualizzare le proprietà di classificazione FCI di Windows Server con i relativi valori possibili in Gestione risorse file server nel file server basato su Windows Server. Per ulteriori informazioni, vedere [Creare una proprietà di classificazione.](https://go.microsoft.com/fwlink/p/?LinkID=627456)

Al termine, i criteri dovrebbero avere due nuove regole che usano entrambe le proprietà del documento **contenenti una di queste condizioni di** valori. Questa condizione non verrà visualizzata nell'interfaccia utente, anche se verranno visualizzate altre condizioni, azioni e impostazioni.

Una regola blocca l'accesso al contenuto dove la proprietà **Informazioni personali** è uguale a **Elevata** o **Moderata**. Una seconda regola invia una notifica sul contenuto dove la proprietà **Informazioni personali** è uguale a **Bassa**.

![Nuova finestra di dialogo dei criteri DLP con due regole appena create](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>Dopo aver creato il criterio DLP

Eseguendo i passaggi descritti nelle sezioni precedenti verrà creato un criterio DLP che rileverà rapidamente il contenuto con tale proprietà, ma solo se il contenuto è stato appena caricato (in modo che il contenuto sia indicizzato) o se il contenuto è precedente ma è stato appena modificato (in modo che il contenuto sia stato indicizzato nuovamente).

Per rilevare il contenuto con tale proprietà ovunque, è possibile richiedere manualmente che la raccolta, il sito o una raccolta siti vengano reindicizzati in modo che il criterio DLP sia a conoscenza di tutto il contenuto con tale proprietà. In SharePoint Online, il contenuto viene automaticamente sottoposto a ricerca per indicizzazione in base a una pianificazione definita. Il crawler rileva il contenuto modificato dall'ultima ricerca per indicizzazione e aggiorna l'indice. Se è necessario che il criterio DLP protegga il contenuto prima della prossima ricerca per indicizzazione pianificata, è possibile eseguire questi passaggi.

> [!CAUTION]
> [!ATTENZIONE]  La reindicizzazione di un sito può provocare un carico eccessivo nel sistema di ricerca. Non re-indicizzare il sito a meno che lo scenario non lo richieda assolutamente.

Per altre informazioni, vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, di una raccolta o di un elenco](https://go.microsoft.com/fwlink/p/?LinkID=627457).

### <a name="reindex-a-site-optional"></a>Reindicizzare un sito (facoltativo)

1. Nel sito scegliere Impostazioni **(icona** a forma di ingranaggio in alto a destra) \> **Impostazioni sito.**

2. In **Ricerca** scegliere **Ricerca e disponibilità offline** \> **Reindicizza sito.**

## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)

- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)

- [Inviare notifiche e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)

- [Elementi inclusi nei modelli dei criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)

- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
