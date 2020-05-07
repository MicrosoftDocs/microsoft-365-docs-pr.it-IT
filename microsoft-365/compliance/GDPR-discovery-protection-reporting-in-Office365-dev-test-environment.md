---
title: Individuazione, protezione e creazione di report secondo il GDPR nell'ambiente di sviluppo/test di Microsoft 365
description: Informazioni su come configurare e dimostrare la gestione delle informazioni personali per il GDPR in un ambiente di sviluppo/test di Microsoft 365.
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b35db1a7be133e61cbde03f02af83baf9341d32e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034650"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-devtest-environment"></a>Individuazione, protezione e creazione di report secondo il GDPR nell'ambiente di sviluppo/test

 **Riepilogo:** dimostrazione delle funzionalità correlate al GDPR in Microsoft 365. 
  
In questo articolo viene descritto come configurare e dimostrare l'individuazione, la protezione e la creazione di report per le informazioni personali secondo il Regolamento generale sulla protezione dei dati (GDPR) in un ambiente di sviluppo/test di Microsoft 365.
  
## <a name="phase-1-create-and-configure-your-trial-microsoft-365-subscription"></a>Fase 1: creare e configurare la sottoscrizione di valutazione di Microsoft 365

Per prima cosa, attenersi alla procedura descritta nell'articolo [Fase 2 dell'ambiente di sviluppo/test di Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription).

Successivamente, seguire questa procedura per configurare il responsabile di eDiscovery:

1. Accedere al tenant di valutazione di Microsoft 365 con l'account di amministratore globale.
2. Dalla home page di Microsoft 365, fare clic su **Sicurezza e conformità**.
3. Nella nuova scheda Sicurezza e conformità, fare clic su **Autorizzazioni** > **Responsabile di eDiscovery**.
4. Fare clic su **Modifica** per il responsabile di eDiscovery, quindi fare clic su **Scegli responsabile di eDiscovery**.
5. Fare clic su **+ Aggiungi**, cercare il nome dell'account amministratore globale e aggiungere il proprio account amministratore globale come responsabile di eDiscovery.
6. Fare clic su **Fine** > **Salva** > **Chiudi**.
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a>Fase 2: aggiungere informazioni personali al tenant

In questa fase, viene creato un documento con le informazioni personali per una serie di IBAN di esempio; tale documento viene quindi archiviato su un sito di SharePoint Online nell'ambiente di sviluppo/test di Microsoft 365.

1. Nel computer locale, aprire Microsoft Word.
2. Incollare la tabella seguente nel file Word e salvarlo come "IBAN.docx" nel computer locale.
    
    Numero   |Paese  |Codice |IBAN  |
    |---------|---------|---------|---------|
    |1     |  Austria SEPA      | AT            |AT611904300234573201       |
    |2     |  Bulgaria SEPA       |BG    |BG80BNBG96611020345678      |
    |3     |  Danimarca SEPA      |   DK      |DK5000400440116243      |
    |4     |  Finlandia SEPA      |   FI      |FI2112345600000785         |
    |5     |  Francia SEPA       |   FR      |FR1420041010050500013M02606         |
    |6     |  Germania SEPA      |   DE      |DE89370400440532013000         |
    |7     |  Grecia SEPA       |   GR      |GR1601101250000000012300695         |
    |8     |  Italia SEPA       |    IT     |GR1601101250000000012300695         |
    |9     |  Paesi Bassi SEPA      |   NL      |    NL91ABNA0417164300     |
    |10     | Polonia SEPA       |  PL       | PL27114020040000300201355387        |

Nota:- questo esempio di set di dati deriva da informazioni pubblicamente disponibili e deve essere utilizzato solo a scopo di test.

3. In una nuova scheda del browser, digitare:  **https://**\<NomeTenant\>**.sharepoint.com**
4. Fare clic su **Documenti** per aprire la raccolta documenti di questo sito. Se viene richiesto di seguire una presentazione di nuovi elenchi, fare clic su **Avanti** fino al suo termine.
5.  Fare clic su **Carica** > **File** e selezionare il file IBAN.docx creato nella Fase 2.

  
## <a name="phase-3-demonstrate-data-discovery"></a>Fase 3: dimostrare l'individuazione dei dati

In questa fase, viene dimostrato come cercare il documento creato e archiviato nella Fase 2, in base agli IBAN che vi sono contenuti.

1. Nella scheda Sicurezza e conformità, fare clic su **Home**, quindi fare clic su **Ricerca e indagini** > **Ricerca di contenuto**.
2. Creare un nuovo elemento da cercare facendo clic su **+**.
3. In una nuova finestra, fornire le seguenti informazioni:  
    a. Nome: Ricerca IBAN  
    b. Indicare dove si desidera eseguire la ricerca: **scegliere siti specifici in cui eseguire la ricerca** (fare clic su **+**), and quindi immettere l'URL del sito: **https://**\<NomeTenant\>**.sharepoint.com/**  
    c. Fare clic su **Aggiungi** e quindi su **OK**. Se si visualizza un avviso, fare clic su **OK**.  
    d. Fare clic su **Avanti** in una finestra **Nuova ricerca**.  
    e. **Indicare cosa si desidera cercare**: **SensitiveType:"International Banking Account Number (IBAN)"**, quindi **Cerca**.

4. Assicurarsi che nei risultati di **Ricerca IBAN** sia presente almeno una voce.


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a>Fase 4: creare un tipo di informazione riservata personalizzato tramite PowerShell

In questa fase, viene creato un tipo di informazione riservata personalizzato per l'azienda fittizia Contoso Corporation tramite Microsoft PowerShell. Contoso si avvale di un Contoso Customer Number (CCN) per identificare ogni cliente nel proprio database dei clienti. Un CCN ha la struttura seguente:
- Due cifre che rappresentano l'anno in cui è stato creato il record.
    - Contoso è stata fondata nel 2002; di conseguenza, il primo valore utile sarebbe 02. 
- Tre cifre che rappresentano l'agenzia partner che ha creato il record.
    - I valori possibili per l'agenzia sono compresi tra 000 e 999. 
- Un carattere alfabetico che rappresenta la linea di business.
    - I valori possibili sono compresi tra a e z, senza distinzione tra maiuscole e minuscole.
- Un numero di serie di quattro cifre. 
    - I possibili valori per il numero di serie sono compresi tra 0000 e 9999.   

Contoso fa sempre riferimento ai clienti utilizzando un CCN nella corrispondenza interna/esterna, nei documenti e in altri moduli. Contoso ha bisogno di un tipo di elemento riservato personalizzato che rilevi l'uso di CCN nei contenuti di Microsoft 365 per poter applicare la protezione per l'utilizzo di questo modulo di informazioni personali.

1. Seguire le istruzioni in [Connettersi a PowerShell in Centro sicurezza e conformità di Office 365 mediante l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) e connettersi al Centro sicurezza e conformità con l'UPN del proprio account amministratore globale.
2. Eseguire i seguenti comandi PowerShell.

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. Eseguire i seguenti comandi PowerShell e copiare i GUID generati in un'istanza aperta di Blocco note sul computer in uso nell'ordine in cui vengono visualizzati.
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. Nel computer locale, aprire un'altra istanza di Blocco note e incollarla nel contenuto seguente:

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. Sostituire i valori di GUID1, GUID2 e GUID3 nel testo XML del passaggio 4 con i rispettivi valori del passaggio 3, quindi salvare i contenuti sul computer locale con il nome di ContosoCCN.xml.
6. Inserire il percorso al file ContosoCCN.xml ed eseguire i seguenti comandi.
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. Dalla scheda Sicurezza e conformità, fare clic su **Classificazioni** > **Tipi di informazioni riservate**. Il Contoso Customer Number (CCN) dovrebbe essere visualizzato nell'elenco.

## <a name="phase-5-demonstrate-data-protection"></a>Fase 5: dimostrare la protezione dei dati

La protezione delle informazioni personali di Microsoft 365 include l'uso delle funzionalità di prevenzione della perdita dei dati (DPL).  Con i criteri DPL, è possibile proteggere automaticamente le informazioni riservate in Microsoft 365.

Esistono molti modi per applicare la protezione. Investire nella formazione e nella sensibilizzazione in merito alla posizione in cui i dati degli utenti che risiedono nell'UE vengono memorizzati nell'ambiente e a come i dipendenti sono autorizzati a gestirli, rappresenta un livello di protezione delle informazioni tramite i criteri di prevenzione della perdita dei dati di Office 365.

In questa fase, viene creato un nuovo criterio DLP e viene dimostrato come applicarlo al file IBAN.docx archiviato in SharePoint Online nella Fase 2 e quando si tenta di inviare un'e-mail contenente IBAN.

1. Dalla scheda Sicurezza e conformità del browser fare clic su **Home**.
2. Fare clic su **Prevenzione della perdita dei dati** > **Criteri**.
3. Fare clic su **+ Crea un criterio**.
4. In **Inizia da un modello o Crea criteri personalizzati** fare clic su **Personalizzato** > **Criteri personalizzati** > **Avanti**.
5. In **Denomina il criterio** fornire i seguenti dettagli e quindi fare clic su **Avanti**:  a. Nome: **Criterio informazioni personali cittadino UE** b. Descrizione: **Proteggere le informazioni personali dei cittadini europei**
6. In **Seleziona posizioni**, scegliere **Tutte le posizioni in Microsoft 365**. Ciò include i contenuti nella posta di Exchange e nei documenti di OneDrive e SharePoint. Infine, fare clic su **Avanti**.
7. In **Personalizza il tipo di contenuti d proteggere** fare clic su **Trova contenuti che includono:** e quindi fare clic su **Modifica**.
8. In **Scegli il tipo di contenuti da proteggere** fare clic su **Aggiungi** > **Tipi di informazioni riservate**.
9. In **Tipi di informazioni riservate** fare clic su **+ Aggiungi**.
10. In **Tipi di informazioni riservate** cercare **IBAN**, selezionare la casella di controllo per **International Banking Account Number (IBAN)** e infine fare clic su **Aggiungi**.
11. Verificare che il tipo di informazione riservata **International Banking Account Number (IBAN)** sia stato aggiunto, quindi fare clic su **Fine**.
12. In **I contenuti includono** verificare che i tipi di informazioni riservate siano stati aggiunti e quindi fare clic su **Salva**.
13. In **Personalizza il tipo di contenuti d proteggere**, verificare che **Trova contenuti che includono:** contenga **International Banking Account Number (IBAN)**, quindi fare clic su **Avanti**.
14. In **Rileva quando i contenuti condivisi includono:**, modificare il valore da **10** a **1** e quindi fare clic su **Avanti**.
15. In **Abilitare il criterio o eseguire prima un test?**, scegliere le impostazioni seguenti, quindi fare clic su **Avanti**.  
    a. Selezionare l'opzione per **Eseguire prima un test**  
    b. Selezionare la casella di controllo per **Mostra i suggerimenti per i criteri in modalità di test** 
16. In **Verifica impostazioni** fare clic su **Crea** dopo aver controllato le impostazioni. NOTA: dopo aver creato un nuovo criterio DLP, sarà necessario attendere un po' di tempo prima che la modifica diventi effettiva.
17. Nel computer locale, aprire un'istanza privata del browser.
18. Nella barra degli indirizzi, digitare **https://**\<NomeTenant\>**.sharepoint.com** e accedere con il proprio account amministratore globale.
19. Fare clic su **Documenti**.
20. Fare clic sul file denominato "IBAN.docx". Dovrebbe essere visualizzato "Suggerimento per i criteri per IBAN.docx". Il file IBAN.docx è stato condiviso con destinatari esterni, cosa che viola il criterio DLP. 
21. Nella barra degli indirizzi digitare: `https://outlook.office365.com`
22. Fare clic su **Nuovo** - **Messaggio di posta elettronica** e fornire quanto segue:  
    - **A:** \<un indirizzo e-mail personale\>  
    - **Oggetto:** Test GDPR  
    - **Corpo:** copiare la tabella dei valori riportata di seguito.
  
        |Numero  |Paese  |Codice |IBAN  |
        |---------|---------|---------|---------|
        |1     |  Austria SEPA      | AT            |AT611904300234573201       |
        |2     |  Bulgaria SEPA       |BG    |BG80BNBG96611020345678      |
        |3     |  Danimarca SEPA      |   DK      |DK5000400440116243      |
        |4     |  Finlandia SEPA      |   FI      |FI2112345600000785         |
        |5     |  Francia SEPA       |   FR      |FR1420041010050500013M02606         |
        |6     |  Germania SEPA      |   DE      |DE89370400440532013000         |
        |7     |  Grecia SEPA       |   GR      |GR1601101250000000012300695         |
        |8     |  Italia SEPA       |    IT     |GR1601101250000000012300695         |
        |9     |  Paesi Bassi SEPA      |   NL      |   NL91ABNA0417164300      |
        |10     | Polonia SEPA       |  PL       | PL27114020040000300201355387        |

Nota:- questo esempio di set di dati deriva da informazioni pubblicamente disponibili e deve essere utilizzato solo a scopo di test.

23. Si noterà che il criterio DLP ha riconosciuto che il corpo dell'e-mail include IBAN e fornisce un suggerimento per i criteri nella parte superiore della finestra del messaggio.
24. Chiudere l'istanza privata del browser.


## <a name="phase-6-demonstrate-reporting"></a>Fase 6: dimostrare la creazione di report
 
In questa fase, viene dimostrata la creazione di report di Microsoft 365 in base al criterio DLP configurato nella Fase 5.

   1. Dalla scheda Sicurezza e conformità del browser fare clic su **Home**.
   2. Fare clic su **Report** > **Dashboard** > **Risultati dei criteri di prevenzione della perdita dei dati**.
   3. I criteri DLP consentono di identificare e proteggere le informazioni riservate dell'organizzazione. Ad esempio, nel report verrà visualizzato che i criteri hanno identificato il documento che include IBAN archiviati in SharePoint Online.
  
## <a name="see-also"></a>Vedere anche

[Information Protection di Office 365 per GDPR](office-365-information-protection-for-gdpr.md)

[GDPR per Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
