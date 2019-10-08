---
title: Funzionamento delle etichette di riservatezza nelle app di Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con le etichette di riservatezza è possibile classificare e proteggere il contenuto riservato senza ostacolare la produttività e la capacità di collaborare degli utenti. È possibile usare le etichette di riservatezza per applicare al contenuto etichettato le impostazioni di protezione, ad esempio crittografia o filigrane.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417565"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Funzionamento delle etichette di riservatezza nelle app di Office

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>Quali sono i prerequisiti per usare le etichette di riservatezza nelle applicazioni di Office?

### <a name="common-requirements"></a>Requisiti comuni 

- Occorre [configurare e pubblicare nel Centro sicurezza e conformità](https://aka.ms/managemip) etichette di riservatezza unificate
- Gli utenti devono avere effettuato l'accesso a Office con il proprio account aziendale.
- Gli utenti devono avere una licenza di Office 365 E3 o superiore.

### <a name="additional-requirements-for-office-for-windows"></a>Requisiti aggiuntivi per Office per Windows 

- Il client di Azure Information Protection non deve essere in esecuzione in Office. Vedere anche: [È possibile usare le etichette di riservatezza insieme al client di Azure Information Protection in Office per Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>Altri requisiti per Outlook in tutte le piattaforme 

- Nella configurazione dell'etichetta, se si attiva il contrassegno del contenuto, è necessario usare Exchange Online per inserire il contrassegno del contenuto in transito.

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>Quali funzionalità delle etichette di riservatezza sono attualmente supportate in Office? 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">Funzionalità<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">Applicare, cambiare o rimuovere manualmente l'etichetta<td><font size="-1"><b>Sì</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">2.21+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup><td><font size="-1">Presto disponibile<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Applicare un'etichetta predefinita</a>
<td><font size="-1"><b>Sì</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">2.21+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Richiedere una giustificazione per la modifica di un'etichetta</a><sup>1</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">2.21+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Fornire un collegamento a una pagina della Guida personalizzata</a>
<td><font size="-1"><b>Sì</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">2.21+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Contrassegnare il contenuto</a>
<td><font size="-1"><b>Sì</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">2.21+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Assegnare autorizzazioni predefinite</a>
<td><font size="-1"><b>Sì</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sì</b><br><font size="-1">2.21+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1"><b>Sì</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Presto disponibile<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Consentire agli utenti di assegnare autorizzazioni</a>
<td><font size="-1"><b>Sì</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sì</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">Da definire
<td><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Da definire<td
><font size="-1">Presto disponibile<sup>3</sup>
<td><font size="-1">Da definire
<td><font size="-1">Presto disponibile<sup>3</sup>

<tr><td><font size="-1">Inviare dati di <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">analisi delle etichette</a> per gli amministratori
<td><font size="-1">Da definire

<td><font size="-1">Da definire

<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti</a>
<td><font size="-1">Da definire

<td><font size="-1">Da definire

<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Applicare automaticamente un'etichetta di riservatezza al contenuto</a>
<td><font size="-1">Da definire

<td><font size="-1">Da definire

<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
<td><font size="-1">Da definire
</table>

<br><sup>1</sup>Se configurato, agli utenti viene chiesto di giustificare il downgrade delle etichette. Tuttavia, i dati relativi alla giustificazione non sono ancora resi disponibili agli amministratori. Diventeranno disponibili quando sarà supportata la funzionalità di invio dati di analisi delle etichette per gli amministratori.
<br><sup>2</sup>La funzionalità per consentire agli utenti di assegnare le autorizzazioni è attualmente disponibile solo in Outlook per Windows e per Mac. La disponibilità per Word, Excel e PowerPoint è da definire.
<br><sup>3</sup>Previsto per il quarto trimestre 2019.

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>Quando vengono applicati i contrassegni o la crittografia dopo l'assegnazione di un'etichetta di riservatezza al contenuto?

| Applicazione | Contrassegno contenuto | Crittografia
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo l'invio del messaggio di posta elettronica da Exchange Online | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo l'invio del messaggio di posta elettronica da Exchange Online | Dopo l'invio del messaggio di posta elettronica da Exchange Online |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>È possibile usare le etichette di riservatezza insieme al client di Azure Information Protection in Office per Windows?

No. Le etichette di riservatezza vengono disattivate se il client di Azure Information Protection viene caricato in Office per Windows.

Se è installato il client di Azure Information Protection, ma si vogliono usare invece le etichette di riservatezza, è possibile:

1. Configurare l'impostazione di Criteri di gruppo  **Utilizzo della funzionalità Riservatezza di Office per applicare e visualizzare le etichette di riservatezza**, disponibile in **Configurazione utente\Modelli amministrativi/Microsoft Office 2016/Impostazioni di sicurezza**.

  >Nota: questa impostazione può essere distribuita tramite i meccanismi tradizionali di distribuzione di Criteri di gruppo oppure dal [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). 
 
  In alternativa, è possibile disinstallare o  [disabilitare](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) il client di Azure Information Protection. 

2. Riavviare tutte le applicazioni di Office.

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Le etichette di riservatezza verranno supportate nelle versioni di Office non in abbonamento, come Office 2016 o Office 2019?

No. Le etichette di riservatezza verranno supportate solo nell'abbonamento a Office 365 e non saranno supportate in alcuna versione non in abbonamento. Tuttavia, nelle versioni di Office non in abbonamento è possibile usare il  client di etichettatura unificata di Azure Information Protection. 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>In precedenza, prima di configurare le etichette di riservatezza. sono stati distribuiti modelli di protezione. Dove sono finiti?

Quando sono abilitate le etichette di riservatezza, i [modelli di protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definiti dall'amministratore sono nascosti dall'esperienza utente di Office in quanto ridondanti, visto che le etichette di riservatezza hanno la crittografia abilitata. 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>Un file o un indirizzo di posta elettronica può avere più di una classificazione?

No. Gli utenti possono selezionare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>Quando si etichetta un messaggio di posta elettronica, gli allegati ottengono automaticamente la stessa etichetta?

No. Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati non ereditano la stessa etichetta. Gli allegati restano senza etichetta o conservano un'eventuale etichetta applicata separatamente. Tuttavia, se l'etichetta del messaggio di posta elettronica applica la protezione, la protezione viene applicata agli allegati di Office.

## <a name="additional-resources"></a>Altre risorse

[Domande frequenti sulla classificazione e l'etichettatura in Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
