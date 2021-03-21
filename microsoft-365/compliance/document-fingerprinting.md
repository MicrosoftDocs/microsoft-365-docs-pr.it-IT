---
title: Creazione impronta digitale documenti
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Gli Information Worker dell'organizzazione gestiscono molti tipi di informazioni riservate durante una giornata. La creazione impronta digitale documenti rende più semplice proteggere le informazioni identificando moduli standard utilizzati all'interno dell'organizzazione. In questo argomento vengono descritti i concetti alla base dell'impronta digitale dei documenti e come crearne uno tramite PowerShell.
ms.openlocfilehash: 1542b956d0a1f662e059ca59ea346a8afc439c83
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918502"
---
# <a name="document-fingerprinting"></a>Creazione impronta digitale documenti

Gli Information Worker dell'organizzazione gestiscono molti tipi di informazioni riservate durante una giornata. Nel Centro sicurezza e conformità, l'impronta digitale dei documenti semplifica la protezione di queste informazioni identificando i moduli standard utilizzati &amp; in tutta l'organizzazione. In questo argomento vengono descritti i concetti alla base dell'impronta digitale dei documenti e come crearne uno tramite PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Scenario di base per la creazione impronta digitale documenti

L'impronta digitale dei documenti è una funzionalità di prevenzione della perdita dei dati (DLP) che converte un modulo standard in un tipo di informazioni riservate, che è possibile utilizzare nelle regole dei criteri DLP. Ad esempio, è possibile creare l'impronta digitale di un documento basata su un modello di brevetto vuoto e creare quindi un criterio DLP che rileva e blocca tutti i modelli di brevetto in uscita contenenti dati sensibili. Facoltativamente, è possibile [](use-notifications-and-policy-tips.md) configurare suggerimenti per i criteri per informare i mittenti che potrebbero inviare informazioni riservate e il mittente deve verificare che i destinatari siano qualificati per ricevere i brevetti. Questo processo funziona con tutti i moduli basati su testo utilizzati nell'organizzazione. Ulteriori esempi di moduli che è possibile caricare includono:
  
- Moduli governativi
- Moduli di conformità Health Insurance Portability and Accountability Act (HIPAA)  
- Moduli di informazioni dei dipendenti per i reparti delle risorse umane
- Moduli personalizzati creati specificamente per l'organizzazione

In teoria, l'organizzazione possiede già una pratica aziendale stabilita relativa all'utilizzo di alcuni moduli per la trasmissione di dati sensibili. Dopo aver caricato un modulo vuoto da convertire in impronta digitale del documento e aver impostato un criterio corrispondente, dlp rileva tutti i documenti nella posta in uscita che corrispondono a tale impronta digitale.

## <a name="how-document-fingerprinting-works"></a>Funzionamento dell'impronta digitale del documento

Sarà già chiaro che i documenti non hanno impronte digitali nel verso senso della parola, ma il nome consente di spiegare la funzionalità. Come le impronti digitali di una persona presentano criteri univoci, così i documenti presentano modelli di parole univoci. Quando si carica un file, DLP identifica il modello di parola univoco nel documento, crea un'impronta digitale del documento basata su tale modello e utilizza l'impronta digitale del documento per rilevare i documenti in uscita contenenti lo stesso modello. Ecco perché il caricamento di un modulo o modello crea il tipo più efficace di impronta digitale del documento. Chiunque compila un modulo usa lo stesso set originale di parole e poi aggiunge proprie parole al documento. Se il documento in uscita non è protetto da password e contiene tutto il testo del modulo originale, DLP può determinare se il documento corrisponde all'impronta digitale del documento.

> [!IMPORTANT]
> Per il momento, DLP può utilizzare l'impronta digitale del documento come metodo di rilevamento solo in Exchange online.

Il seguente esempio mostra cosa accade si crea un'impronta digitale del documento in base al modello di brevetto. È comunque possibile usare qualsiasi modello per la creazione di un'impronta digitale del documento.
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>Esempio di un documento di brevetto corrispondente a un'impronta digitale del documento di un modello di brevetto

![Document-Fingerprinting-diagram.png](../media/Document-Fingerprinting-diagram.png)
  
Il modello di brevetto contiene i campi vuoti "Patent title", "Inventors" e "Description" e le descrizioni per ognuno di questi campi, ovvero il modello di parola. Quando carichi il modello di brevetto originale, è in uno dei tipi di file supportati e in testo normale. DLP converte questo modello di parola in un'impronta digitale del documento, ovvero un piccolo file XML Unicode contenente un valore hash univoco che rappresenta il testo originale e l'impronta digitale viene salvata come classificazione dei dati in Active Directory. Come misura di sicurezza, il documento originale non viene archiviato nel servizio, ma viene archiviato solo il valore hash e il documento originale non può essere ricostruito dal valore hash. L'impronta digitale del brevetto diventa quindi un tipo di informazioni riservate che è possibile associare a un criterio DLP. Dopo aver associato l'impronta digitale a un criterio DLP, DLP rileva eventuali messaggi di posta elettronica in uscita contenenti documenti che corrispondono all'impronta digitale del brevetto e li gestisce in base ai criteri dell'organizzazione. 

Ad esempio, è possibile impostare un criterio DLP che impedisca ai dipendenti regolari di inviare messaggi in uscita contenenti brevetti. DLP userà l'impronta digitale del brevetto per rilevare i brevetti e bloccare tali messaggi di posta elettronica. In alternativa, è consigliabile consentire all'ufficio legale di inviare brevetti ad altre organizzazioni perché è necessaria per l'azienda. È possibile consentire a reparti specifici di inviare informazioni riservate creando eccezioni per tali reparti nel criterio DLP oppure è possibile consentire loro di ignorare un suggerimento per i criteri con una giustificazione aziendale.
  
### <a name="supported-file-types"></a>Tipi di file supportati

L'impronta digitale dei documenti supporta gli stessi tipi di file supportati nelle regole del flusso di posta (note anche come regole di trasporto). Per un elenco dei tipi di file supportati, vedere Tipi di file supportati per l'ispezione del contenuto delle [regole del flusso di posta](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una breve nota sui tipi di file: né le regole del flusso di posta né l'impronta digitale del documento supportano il tipo di file dotx, che può creare confusione perché si tratta di un file modello in Word. Quando si vede la parola "modello" in questo e in altri argomenti relativi alla creazione dell'impronta digitale del documento, si fa riferimento a un documento definito dall'utente come modulo standard, non al tipo di file modello.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitazioni della creazione dell'impronta digitale del documento

L'impronta digitale del documento non rileva le informazioni riservate nei casi seguenti:
  
- File protetti da password
- File che contengono solo immagini
- Documenti che non contengono tutto il testo del modulo originale usato per la creazione dell'impronta digitale del documento

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Usare PowerShell per creare un pacchetto di regole di classificazione in base all'impronta digitale del documento

Si noti che attualmente è possibile creare un'impronta digitale del documento solo tramite PowerShell nel Centro &amp; sicurezza e conformità. Per connettersi, [vedere Connect to Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

DLP usa pacchetti di regole di classificazione per rilevare contenuto sensibile. Per creare un pacchetto di regole di classificazione basato su un'impronta digitale del documento, utilizzare i cmdlet **New-DlpFingerprint** e **New-DlpSensitiveInformationType.** Poiché i risultati di **New-DlpFingerprint** non vengono archiviati all'esterno della regola di classificazione dei dati, si eseguono sempre **New-DlpFingerprint** e **New-DlpSensitiveInformationType** o **Set-DlpSensitiveInformationType** nella stessa sessione di PowerShell. In questo esempio viene creata una nuova impronta digitale di documento in base al file C:\Documenti\Contoso Employee Template.docx. La nuova impronta digitale viene archiviata come variabile e potrà essere quindi utilizzata con il cmdlet **New-DlpSensitiveInformationType** nella stessa sessione di PowerShell.
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

A questo punto, passiamo alla creazione di una nuova regola di classificazione dati denominata "Contoso Employee Confidential" che utilizza l'impronta digitale del documento del file C:\Documenti\Contoso Customer Information Form.docx.
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

È ora possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** per trovare tutti i pacchetti di regole di classificazione dei dati DLP e in questo esempio "Contoso Customer Confidential" fa parte dell'elenco dei pacchetti delle regole di classificazione dei dati. 
  
Infine, aggiungere il pacchetto di regole di classificazione dei dati "Contoso Customer Confidential" a un criterio DLP nel Centro &amp; sicurezza e conformità. In questo esempio viene aggiunta una regola a un criterio DLP esistente denominato "ConfidentialPolicy".

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

È inoltre possibile utilizzare il pacchetto di regole di classificazione dei dati nelle regole del flusso di posta in Exchange Online, come illustrato nell'esempio seguente. Per eseguire questo comando, è innanzitutto necessario [connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell) Si noti inoltre che il pacchetto di regole richiede tempo per la sincronizzazione dal Centro sicurezza e conformità &amp; all'interfaccia di amministrazione di Exchange.
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP ora rileva i documenti che corrispondono all'impronta digitale del Form.docx cliente Contoso.
  
Per informazioni sulla sintassi e sui parametri, vedere:

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)