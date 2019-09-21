---
title: Creazione impronta digitale documenti
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Gli Information Worker dell'organizzazione gestiscono molti tipi di informazioni riservate durante una giornata. La creazione impronta digitale documenti rende più semplice proteggere le informazioni identificando moduli standard utilizzati all'interno dell'organizzazione. In questo argomento vengono descritti i concetti che stanno alla base dell'impronta digitale del documento e come crearne uno tramite PowerShell.
ms.openlocfilehash: 776410ec042e629e32fa6b03a2cb4fe0f2bacd2e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070116"
---
# <a name="document-fingerprinting"></a>Creazione impronta digitale documenti

Gli Information Worker dell'organizzazione gestiscono molti tipi di informazioni riservate durante una giornata. Nel centro sicurezza &amp; e conformità, le impronte digitali dei documenti facilitano la protezione delle informazioni identificando i moduli standard utilizzati nell'organizzazione. In questo argomento vengono descritti i concetti che stanno alla base dell'impronta digitale del documento e come crearne uno tramite PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Scenario di base per la creazione impronta digitale documenti

L'impronta digitale del documento è una funzionalità di prevenzione della perdita di dati (DLP) che converte un modulo standard in un tipo di informazioni riservate, che è possibile utilizzare nelle regole dei criteri DLP. Ad esempio, è possibile creare l'impronta digitale di un documento basata su un modello di brevetto vuoto e creare quindi un criterio DLP che rileva e blocca tutti i modelli di brevetto in uscita contenenti dati sensibili. Facoltativamente, è possibile impostare suggerimenti per i [criteri](use-notifications-and-policy-tips.md) per segnalare ai mittenti che potrebbero inviare informazioni riservate e il mittente deve verificare che i destinatari siano qualificati per la ricezione dei brevetti. Questo processo funziona con tutti i moduli basati su testo utilizzati nell'organizzazione. Ulteriori esempi di moduli che è possibile caricare includono: 
  
- Moduli governativi
    
- Moduli di conformità Health Insurance Portability and Accountability Act (HIPAA)
    
- Moduli di informazioni dei dipendenti per i reparti delle risorse umane
    
- Moduli personalizzati creati specificamente per l'organizzazione
    
In teoria, l'organizzazione possiede già una pratica aziendale stabilita relativa all'utilizzo di alcuni moduli per la trasmissione di dati sensibili. Dopo aver caricato una maschera vuota per essere convertita in un'impronta digitale del documento e aver configurato un criterio corrispondente, il DLP rileva tutti i documenti nella posta in uscita che corrispondono a tale impronta digitale.
  
## <a name="how-document-fingerprinting-works"></a>Funzionamento dell'impronta digitale del documento

Sarà già chiaro che i documenti non hanno impronte digitali nel verso senso della parola, ma il nome consente di spiegare la funzionalità. Come le impronti digitali di una persona presentano criteri univoci, così i documenti presentano modelli di parole univoci. Quando si carica un file, DLP identifica il modello di parola univoco nel documento, crea un'impronta digitale del documento in base a tale modello e utilizza tale impronta digitale per rilevare i documenti in uscita che contengono lo stesso modello. Ecco perché il caricamento di un modulo o modello crea il tipo più efficace di impronta digitale del documento. Chiunque compila un modulo usa lo stesso set originale di parole e poi aggiunge proprie parole al documento. Fintanto che il documento in uscita non è protetto da password e contiene tutto il testo del modulo originale, DLP è in grado di determinare se il documento corrisponde all'impronta digitale del documento.
  
Il seguente esempio mostra cosa accade si crea un'impronta digitale del documento in base al modello di brevetto. È comunque possibile usare qualsiasi modello per la creazione di un'impronta digitale del documento.
  
**Esempio di un documento di brevetto corrispondente a un'impronta digitale del documento di un modello di brevetto**

![Document-Fingerprinting-diagram. png](media/Document-Fingerprinting-diagram.png)
  
Il modello di brevetto contiene i campi vuoti "titolo brevetto", "inventori" e "Descrizione" e descrizioni per ognuno di questi campi, ovvero il modello di parola. Quando si carica il modello di brevetto originale, si trova in uno dei tipi di file supportati e in testo normale. DLP converte questo modello di parola in un'impronta digitale del documento, che è un piccolo file XML Unicode contenente un valore hash univoco che rappresenta il testo originale e l'impronta digitale viene salvata come classificazione dei dati in Active Directory. (Come misura di sicurezza, il documento originale non è archiviato nel servizio, solo il valore hash è archiviato e il documento originale non può essere ricostruito dal valore hash). L'impronta digitale del brevetto diventa quindi un tipo di informazioni riservate che è possibile associare a un criterio DLP. Dopo aver associato l'impronta digitale a un criterio DLP, DLP rileva eventuali messaggi di posta elettronica in uscita contenenti documenti che corrispondono all'impronta digitale del brevetto e li gestisce in base ai criteri dell'organizzazione. 

Ad esempio, potrebbe essere necessario configurare un criterio DLP che impedisca ai dipendenti regolari di inviare messaggi in uscita contenenti brevetti. DLP utilizzerà l'impronta digitale del brevetto per rilevare i brevetti e bloccare tali messaggi di posta elettronica. In alternativa, è possibile lasciare che il proprio reparto legale sia in grado di inviare brevetti ad altre organizzazioni perché ha bisogno di questo tipo di attività. È possibile consentire a determinati reparti di inviare informazioni riservate creando eccezioni per i reparti del criterio DLP oppure è possibile consentire loro di ignorare un suggerimento per i criteri con una giustificazione aziendale.
  
### <a name="supported-file-types"></a>Tipi di file supportati

L'impronta digitale del documento supporta gli stessi tipi di file supportati nelle regole del flusso di posta (note anche come regole di trasporto). Per un elenco dei tipi di file supportati, vedere [tipi di file supportati per l'ispezione del contenuto delle regole del flusso di posta](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una breve nota sui tipi di file: né le regole del flusso di posta né le impronte digitali del documento supportano il tipo di file. dotx, che può essere confusionario perché si tratta di un file modello in Word. Quando si vede la parola "modello" in questo e in altri argomenti relativi alla creazione dell'impronta digitale del documento, si fa riferimento a un documento definito dall'utente come modulo standard, non al tipo di file modello.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitazioni della creazione dell'impronta digitale del documento

L'impronta digitale del documento non rileva informazioni riservate nei casi seguenti:
  
- File protetti da password
    
- File che contengono solo immagini
    
- Documenti che non contengono tutto il testo del modulo originale usato per la creazione dell'impronta digitale del documento
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Utilizzo di PowerShell per creare un pacchetto di regole di classificazione basato sull'impronta digitale dei documenti

Si noti che è possibile creare un'impronta digitale del documento solo tramite PowerShell nel centro &amp; sicurezza e conformità. Per eseguire la connessione, vedere [PowerShell to Connect to Security & Compliance Center](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

DLP utilizza pacchetti di regole di classificazione per rilevare contenuti sensibili. Per creare un pacchetto di regole di classificazione in base a un'impronta digitale del documento, utilizzare i cmdlet **New-DlpFingerprint** e **New-DlpSensitiveInformationType** . Poiché i risultati di **New-DlpFingerprint** non sono archiviati all'esterno della regola di classificazione dei dati, vengono sempre eseguiti **New-DlpFingerprint** e **New-DlpSensitiveInformationType** o **set-DlpSensitiveInformationType** nello stesso Sessione di PowerShell. In questo esempio viene creata una nuova impronta digitale di documento in base al file C:\Documenti\Contoso Employee Template.docx. La nuova impronta digitale viene archiviata come variabile e potrà essere quindi utilizzata con il cmdlet **New-DlpSensitiveInformationType** nella stessa sessione di PowerShell. 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

A questo punto, passiamo alla creazione di una nuova regola di classificazione dati denominata "Contoso Employee Confidential" che utilizza l'impronta digitale del documento del file C:\Documenti\Contoso Customer Information Form.docx.
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

È ora possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** per trovare tutti i pacchetti di regole di classificazione dei dati DLP e, in questo esempio, "contoso Customer Confidential" fa parte dell'elenco dei pacchetti di regole di classificazione dei dati. 
  
Infine, aggiungere il pacchetto di regole di classificazione dei dati "contoso Customer Confidential" a un criterio DLP &amp; nel centro sicurezza e conformità. In questo esempio viene aggiunta una regola a un criterio DLP esistente denominato "ConfidentialPolicy".

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

È inoltre possibile utilizzare il pacchetto di regole di classificazione dei dati nelle regola del flusso di posta in Exchange Online, come illustrato nell'esempio seguente. Per eseguire questo comando, è innanzitutto necessario [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Si noti inoltre che richiede tempo affinché il pacchetto di regole venga sincronizzato dal &amp; centro conformità di sicurezza all'interfaccia di amministrazione di Exchange.
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP rileva ora i documenti che corrispondono all'impronta digitale del documento contoso Customer form. docx.
  
Per informazioni sulla sintassi e sui parametri, vedere:

- [New-DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
