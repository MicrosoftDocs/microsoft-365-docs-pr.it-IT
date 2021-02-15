---
title: Revocare la posta elettronica crittografata da Advanced Message Encryption
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
description: Come amministratore e come mittente del messaggio, è possibile revocare determinati messaggi di posta elettronica crittografati con Office 365 Advanced Message Encryption.
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105141"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revocare la posta elettronica crittografata da Advanced Message Encryption

La revoca della posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365. Office 365 Advanced Message Encryption è incluso in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Noprofit Staff Pricing), Office 365 Enterprise E5 (Noprofit Staff Pricing) e Office 365 Education A5. Se l'organizzazione ha un abbonamento che non include Office 365 Advanced Message Encryption, è possibile acquistarlo con il componente aggiuntivo SKU conformità Microsoft 365 E5 per Microsoft 365 E3, Microsoft 365 E3 (Prezzi per il personale no profit) o il componente aggiuntivo SKU Office 365 Advanced Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi per il personale no profit) o SKU di Office 365.

Questo articolo fa parte di una più ampia serie di articoli sulla crittografia dei messaggi di [Office 365.](ome.md)

Se un messaggio è stato crittografato con Office 365 Advanced Message Encryption e si è un amministratore di Microsoft 365 o si è il mittente del messaggio, è possibile revocare il messaggio in determinate condizioni. Gli amministratori revocano i messaggi tramite PowerShell. Come mittente, si revoca un messaggio inviato direttamente da Outlook sul Web. In questo articolo vengono descritte le circostanze in cui è possibile revocare e come farlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Messaggi di posta elettronica crittografati che è possibile revocare

Gli amministratori e i mittenti dei messaggi possono revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto un messaggio di posta elettronica crittografato personalizzato basato su collegamento. Se il destinatario ha ricevuto un'esperienza in linea nativa in un client Di Outlook supportato, non è possibile revocare il messaggio.

Il fatto che un destinatario riceva un'esperienza basata su collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: i destinatari dell'account Di Office 365 e Microsoft (ad esempio, gli utenti di outlook.com) ottengono un'esperienza in linea nei client Outlook supportati. Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail e Yahoo, ottengono un'esperienza basata su collegamenti.

Gli amministratori e i mittenti dei messaggi possono revocare i messaggi crittografati utilizzando la crittografia applicata direttamente da Outlook sul Web. Ad esempio, i messaggi crittografati con l'opzione Solo crittografia.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot showing Encrypt Only option in Outlook on the web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Esperienza del destinatario per i messaggi di posta elettronica crittografati revocati

Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "Il messaggio è stato revocato dal mittente".

![Screenshot che mostra un messaggio di posta elettronica crittografato revocato.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Come revocare un messaggio crittografato inviato

È possibile revocare un messaggio inviato a un singolo destinatario che utilizza un account di social gmail.com o yahoo.com. In altre parole, è possibile revocare un messaggio di posta elettronica inviato a un singolo destinatario che ha ricevuto l'esperienza basata su collegamento.

Non è possibile revocare un messaggio di posta elettronica inviato a un destinatario che usa un account aziendale o dell'istituto di istruzione da Office 365 o Microsoft 365 o un utente che usa un account Microsoft, ad esempio un account outlook.com. 

Per revocare un messaggio crittografato inviato, eseguire la procedura seguente

1. In Outlook sul Web, nella **cartella Posta** inviata, passare al messaggio che si desidera revocare.

   Se la posta è revocabile, nella parte superiore del messaggio verrà visualizzato il collegamento "Rimuovi accesso esterno".

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot showing encrypted mail that you want to revoke in Outlook on the web.":::

2. Fare **clic su Rimuovi accesso esterno** per revocare il messaggio.

   Il messaggio mostra che il suo stato è stato revocato.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot showing revoked encrypted message in Outlook on the web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Come revocare un messaggio crittografato come amministratore

Gli amministratori di Microsoft 365 seguono questi passaggi generali per revocare un messaggio di posta elettronica crittografato idoneo:

- Ottenere l'ID messaggio del messaggio di posta elettronica.
- Verificare che sia possibile revocare il messaggio.
- Revocare il messaggio di posta elettronica.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Passaggio 1. Ottenere l'ID messaggio del messaggio di posta elettronica

Prima di poter revocare un messaggio crittografato, raccogliere l'ID del messaggio. MessageId è in genere nel formato seguente:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Esistono diversi modi per trovare l'ID messaggio del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte due opzioni, ma è possibile utilizzare qualsiasi metodo che fornisce l'ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Per identificare l'ID messaggio del messaggio di posta elettronica che si desidera revocare utilizzando Traccia messaggio nel Centro &amp; sicurezza e conformità

1. Cercare il messaggio di posta elettronica in base al mittente o al destinatario usando Traccia nuovo [messaggio nel Centro sicurezza & conformità.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)

2. Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro dei dettagli **di Traccia messaggio.** Espandere **Ulteriori informazioni per** individuare l'ID messaggio.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Per identificare l'ID messaggio del messaggio di posta elettronica che si desidera revocare utilizzando i report di Crittografia messaggi di Office nel Centro &amp; sicurezza e conformità

1. Nel Centro sicurezza &amp; e conformità passare al report crittografia dei **messaggi.** Per informazioni su questo report, vedere Visualizzare i report [di sicurezza della posta elettronica nel Centro sicurezza e &amp; conformità.](../security/office-365-security/view-email-security-reports.md)

2. Scegliere la **tabella Visualizza dettagli** e identificare il messaggio che si desidera revocare.

3. Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID messaggio.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Passaggio 2. Verificare che la posta sia revocabile

Per verificare se è possibile revocare un messaggio, verificare se il campo  Stato revoca è visibile nel report Crittografia, nella tabella Dettagli del Centro &amp; sicurezza e conformità.

Per verificare se è possibile revocare un determinato messaggio di posta elettronica utilizzando Windows PowerShell, completare questi passaggi.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

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

Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare il messaggio di posta elettronica utilizzando il Centro sicurezza conformità o &amp; Windows PowerShell.

Per revocare il messaggio tramite il Centro &amp; sicurezza e conformità

1. Usando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi al Centro sicurezza & conformità.

2. Nel report **Crittografia,** nella **tabella Dettagli** per il messaggio, scegliere **Revoca messaggio.**

Per revocare un messaggio di posta elettronica Windows PowerShell, utilizzare il cmdlet Set-OMEMessageRevocation seguente.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://aka.ms/exopowershell)

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

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption - Scadenza della posta elettronica](ome-advanced-expiration.md)

- [Criteri dei messaggi e descrizione del servizio di conformità](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
