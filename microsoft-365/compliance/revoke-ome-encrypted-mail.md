---
title: Revocare la posta elettronica crittografata dalla crittografia avanzata dei messaggi
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Come amministratore e come mittente del messaggio, puoi revocare determinati messaggi di posta elettronica crittografati con Office 365 Advanced Message Encryption.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051718"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revocare la posta elettronica crittografata dalla crittografia avanzata dei messaggi

La revoca della posta elettronica viene offerta come parte di Office 365 Advanced Message Encryption. Office 365 Advanced Message Encryption è incluso in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Noprofit Staff Pricing), Office 365 Enterprise E5 (Noprofit Staff Pricing) e Office 365 Education A5. Se l'organizzazione dispone di una sottoscrizione che non include Office 365 Advanced Message Encryption, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale nonprofit) o con il componente aggiuntivo SKU Office 365 Advanced Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale nonprofit) o SKU Office 365.

Questo articolo fa parte di una serie più ampia di [articoli su Office 365 Message Encryption](ome.md).

Se un messaggio è stato crittografato utilizzando Office 365 Advanced Message Encryption e si è un amministratore di Microsoft 365 o si è il mittente del messaggio, è possibile revocare il messaggio in determinate condizioni. Gli amministratori revocano i messaggi tramite PowerShell. Come mittente, si revoca un messaggio inviato direttamente da Outlook sul Web. In questo articolo vengono descritte le circostanze in cui la revoca è possibile e come farlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Messaggi di posta elettronica crittografati che è possibile revocare

Gli amministratori e i mittenti dei messaggi possono revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto un messaggio di posta elettronica crittografato basato su collegamento e personalizzato. Se il destinatario ha ricevuto un'esperienza nativa in linea in un client Outlook supportato, non è possibile revocare il messaggio.

Il fatto che un destinatario riceva un'esperienza basata su collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: i destinatari dell'account Office 365 e Microsoft (ad esempio, gli utenti di outlook.com) ottengono un'esperienza in linea nei client Outlook supportati. Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail e Yahoo, ottengono un'esperienza basata sui collegamenti.

Gli amministratori e i mittenti dei messaggi possono revocare i messaggi crittografati utilizzando la crittografia applicata direttamente Outlook sul Web. Ad esempio, i messaggi crittografati con l'opzione Solo crittografia.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot che mostra l'opzione Solo crittografia Outlook sul Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Esperienza del destinatario per i messaggi di posta elettronica crittografati revocati

Dopo la revoca di un messaggio di posta elettronica, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di Office 365 Message Encryption: "Il messaggio è stato revocato dal mittente".

![Screenshot che mostra un messaggio di posta elettronica crittografato revocato.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Come revocare un messaggio crittografato inviato

È possibile revocare un messaggio inviato a un singolo destinatario che utilizza un account di social gmail.com o yahoo.com. In altre parole, è possibile revocare un messaggio di posta elettronica inviato a un singolo destinatario che ha ricevuto l'esperienza basata su collegamento.

Non è possibile revocare un messaggio inviato a un destinatario che utilizza un account aziendale o dell'istituto di istruzione da Office 365 o Microsoft 365 o da un utente che utilizza un account Microsoft, ad esempio un account outlook.com. 

Per revocare un messaggio crittografato inviato, eseguire la procedura seguente

1. In Outlook sul Web, nella **cartella Posta** inviata passare al messaggio che si desidera revocare.

   Se la posta è revocabile, nella parte superiore del messaggio verrà visualizzato il collegamento "Rimuovi accesso esterno".

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot che mostra la posta crittografata che si desidera revocare Outlook sul Web.":::

2. Fare **clic su Rimuovi accesso esterno** per revocare il messaggio.

   Il messaggio indica che il relativo stato è stato revocato.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot che mostra il messaggio crittografato revocato Outlook sul Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Come revocare un messaggio crittografato come amministratore

Microsoft 365 gli amministratori seguono questi passaggi generali per revocare un messaggio di posta elettronica crittografato idoneo:

- Ottenere l'ID del messaggio di posta elettronica.
- Verificare che sia possibile revocare il messaggio.
- Revocare la posta.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Passaggio 1. Ottenere l'ID messaggio del messaggio di posta elettronica

Prima di poter revocare un messaggio crittografato, raccogliere l'ID del messaggio. MessageId è in genere nel formato seguente:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Esistono diversi modi per trovare l'ID messaggio del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte due opzioni, ma è possibile utilizzare qualsiasi metodo che fornisce l'ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando Traccia messaggi nel Centro &amp; sicurezza e conformità

1. Cercare il messaggio di posta elettronica in base al mittente o al destinatario usando Nuova traccia dei messaggi [nel Centro sicurezza & conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **dei dettagli di Traccia** messaggio. Espandere **Altre informazioni per** individuare l'ID messaggio.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando Office di crittografia dei messaggi nel Centro sicurezza &amp; e conformità

1. Nel Centro &amp; sicurezza e conformità passare al report Crittografia **messaggi**. Per informazioni su questo report, vedere [View email security reports in the Security Compliance &amp; Center.](../security/defender-365-security/view-email-security-reports.md)

2. Scegliere la **tabella Visualizza** dettagli e identificare il messaggio che si desidera revocare.

3. Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID messaggio.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Passaggio 2. Verificare che la posta sia revocabile

Per verificare se è possibile revocare un messaggio, verificare se il campo  Stato revoca è visibile nel report Crittografia nella tabella Dettagli del Centro &amp; sicurezza e conformità.

Per verificare se è possibile revocare un determinato messaggio di posta elettronica utilizzando Windows PowerShell, completare questi passaggi.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Get-OMEMessageStatus seguente:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Questo comando restituisce l'oggetto del messaggio e indica se il messaggio è revocabile. Ad esempio,

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Passaggio 3. Revocare la posta

Una volta che si conosce l'ID messaggio del messaggio di posta elettronica che si desidera revocare e si è verificato che il messaggio è revocabile, è possibile revocare il messaggio utilizzando il Centro sicurezza e conformità o &amp; Windows PowerShell.

Per revocare il messaggio tramite il Centro &amp; sicurezza e conformità

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi al Centro sicurezza & conformità.

2. Nel report **Crittografia,** nella **tabella Dettagli** per il messaggio, scegliere **Revoca messaggio**.

Per revocare un messaggio di posta elettronica Windows PowerShell, utilizzare il cmdlet Set-OMEMessageRevocation.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, Connessione [per Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-OMEMessageRevocation seguente:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus seguente:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni su Office 365 Advanced Message Encryption

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption - Scadenza della posta elettronica](ome-advanced-expiration.md)

- [Criteri dei messaggi e descrizione del servizio di conformità](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)