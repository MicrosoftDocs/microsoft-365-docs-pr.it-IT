---
title: Distribuire siti di SharePoint Online per tre livelli di protezione
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Sintesi: creare e configurare siti del team di SharePoint Online per diversi livelli di protezione delle informazioni.'
ms.openlocfilehash: 4ff892d57d4fe6e707e4cbcb4f1562a3594fe70b
ms.sourcegitcommit: e4f2f06daa264b8b476813a2dfe80cffb59f968f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38708142"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>Distribuire siti di SharePoint Online per tre livelli di protezione

 **Sintesi**: creare e configurare siti del team di SharePoint Online per diversi livelli di protezione delle informazioni.
  
Usare i passaggi descritti in questo articolo per progettare e distribuire siti del team di SharePoint Online di base, sensibili e con riservatezza elevata. Per altre informazioni su questi tre livelli di protezione, vedere [Proteggere siti e file di SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).
  
## <a name="baseline-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online di base

La protezione di siti di base include siti del team pubblici e privati. I siti del team pubblici possono essere individuati e usati da qualsiasi persona dell'organizzazione. I siti privati possono essere individuati e usati solo dai membri del gruppo di Office 365 associato al sito del team. Entrambi questi tipi di siti del team consentono ai membri di condividere il sito con altri utenti.
  
### <a name="public"></a>Pubblico

Per creare un sito del team di SharePoint Online di base con accesso pubblico e autorizzazioni, seguire questa procedura:
  
1. Accedere all'interfaccia di amministrazione con un account che verrà usato anche per amministrare il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.
    
4. Nella pagina **Crea sito** fare clic su **Sito del team**.
    
5. In **Nome sito** digitare il nome del sito del team pubblico.
    
6. In **Team site description** (Descrizione sito del team) digitare una descrizione dello scopo del sito.
    
7. In **Impostazioni privacy** selezionare **Public – anyone in the organization can access this site** (Pubblico: qualsiasi persona dell'organizzazione può accedere a questo sito) e quindi fare clic su **Avanti**.
    
8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.
    
Di seguito è riportata la configurazione risultante.
  
![Protezione di livello di base per un sito del team di SharePoint Online pubblico.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>Private

Per creare un sito del team di SharePoint Online di base con accesso privato e autorizzazioni, seguire questa procedura:
  
1. Accedere all'interfaccia di amministrazione con un account che verrà usato anche per amministrare il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.
    
4. Nella pagina **Crea sito** fare clic su **Sito del team**.
    
5. In **Nome sito** digitare il nome del sito del team privato.
    
6. In **Team site description** (Descrizione sito del team) digitare una descrizione dello scopo del sito.
    
7. In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.
    
8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) in **Aggiungi membri** digitare i nomi degli account utente che hanno accesso a questo sito del team privato.
    
9. Quando il set iniziale di membri è stato aggiunto al sito, fare clic su **Fine**.
    
Di seguito è riportata la configurazione risultante.
  
![Protezione di livello di base per un sito del team di SharePoint Online privato.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online sensibili

Un sito del team di SharePoint Online riservato è un sito del team isolato. Ciò significa che le autorizzazioni vengono controllate tramite l'appartenenza ai gruppi di SharePoint anziché tramite l’appartenenza al gruppo di Office 365 associato al sito del team.
  
Per creare un sito del team isolato, sono disponibili due passaggi principali.
  
### <a name="step-1-design-your-isolated-site"></a>Passaggio 1: Progettare un sito isolato

Per progettare un sito del team isolato è necessario stabilire:
  
- I gruppi di SharePoint e i livelli di autorizzazione.
    
- Il set di gruppi di accesso che saranno membri dei gruppi di SharePoint.
    
     Il set di gruppi di accesso consigliato è uno per i membri del sito, uno per i visualizzatori del sito e uno per gli amministratori del sito.
    
- Se verranno usati gruppi nidificati all'interno dei gruppi di accesso.
    
Ad esempio, la struttura dei gruppi e i livelli di autorizzazione consigliati sono simili ai seguenti:
  
|**Gruppo di SharePoint**|**Livello di autorizzazione**|**Gruppo di accesso (esempi)**|
|:-----|:-----|:-----|
|Membri di [nome sito]  <br/> |Modifica  <br/> |Membri di [nome sito]  <br/> |
|Visitatori di [nome sito]  <br/> |Lettura  <br/> |Visualizzatori di [nome sito]  <br/> |
|Proprietari di [nome sito]  <br/> |Controllo completo  <br/> |Amministratori di [nome sito]  <br/> |
   
Per un sito del team, i gruppi e i livelli di autorizzazione di SharePoint vengono creati per impostazione predefinita. È necessario stabilire i nomi dei gruppi di accesso.
  
Per i dettagli del processo di progettazione, vedere [Progettare un sito del team SharePoint Online isolato](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
### <a name="step-2-deploy-your-isolated-site"></a>Passaggio 2: Distribuire un sito isolato

Per distribuire un sito isolato è innanzitutto necessario:
  
- Stabilire gli account utente e i gruppi da aggiungere a ogni gruppo di accesso.
    
- Creare i gruppi di accesso e aggiungere i membri di tipo utente e gruppo.
    
Per istruzioni dettagliate, vedere la **Fase 1** di [Distribuire un sito del team di SharePoint Online isolato](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
Successivamente, creare il sito del team di SharePoint Online seguendo questi passaggi.
  
1. Accedere all'interfaccia di amministrazione con un account che verrà usato anche per amministrare il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella nuova **scheda SharePoint** del browser fare clic su **+ Crea sito**.
    
4. Nella pagina **Crea sito** fare clic su **Sito del team**.
    
5. In **Nome sito** digitare il nome del sito del team privato.
    
6. Nella descrizione **Sito del team** digitare una descrizione facoltativa.
    
7. In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.
    
8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.
    
Successivamente, dal nuovo sito del team di SharePoint Online configurare le autorizzazioni seguendo questi passaggi.
  
1. Determinare il Nome dell'entità utente (UPN) di cui l'amministratore IT o altra persona sarà responsabile per rispondere a e indirizzare le richieste di accesso al sito (un esempio di UPN è belindan@contoso.com). 
    
2. Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.
    
3. Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).
    
4. Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.
    
5. Nella finestra di dialogo **Impostazioni richieste di accesso**:
    
  - Deselezionare le caselle di controllo **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito**.
    
  - Digitare il nome dell'entità utente dell'amministratore IT al passaggio 1 in **Invia tutte le richieste di accesso**.
    
  - Fare clic su **OK**.
    
6. Nella scheda **Autorizzazioni** del browser fare clic su **Membri di [nome sito]** nell'elenco.
    
7. In **Utenti e gruppi** fare clic su **Nuovo**.
    
8. Nella finestra di dialogo **Condividi** digitare il nome del gruppo di accesso dei membri del sito per questo sito, selezionarlo e quindi fare clic su **Condividi**.
    
9. Fare clic sul pulsante Indietro del browser.
    
10. Fare clic su **Proprietari di <nome del sito>** nell'elenco.
    
11. In **Utenti e gruppi** fare clic su **Nuovo**.
    
12. Nella finestra di dialogo **Condividi** digitare il nome del gruppo di accesso degli amministratori del sito per questo sito, selezionarlo e quindi fare clic su **Condividi**.
    
13. Fare clic sul pulsante Indietro del browser.
    
14. Fare clic su **Visitatori di <nome del sito>** nell'elenco.
    
15. In **Utenti e gruppi** fare clic su **Nuovo**.
    
16. Nella finestra di dialogo **Condividi** digitare il nome del gruppo di accesso dei visualizzatori del sito per questo sito, selezionarlo e quindi fare clic su **Condividi**.
    
17. Chiudere la scheda **Autorizzazioni** del browser.
    
I risultati di queste impostazioni delle autorizzazioni sono i seguenti:
  
- Il gruppo di SharePoint **Proprietari di [nome sito]** contiene il gruppo di accesso degli amministratori del sito in cui tutti i membri hanno il livello di autorizzazione **Controllo completo**.
    
- Il gruppo di SharePoint **Membri di [nome sito]** contiene il gruppo di accesso dei membri del sito in cui tutti i membri hanno il livello di autorizzazione **Modifica**.
    
- Il gruppo di SharePoint **Visitatori di [nome sito]** contiene il gruppo di accesso dei visualizzatori del sito in cui tutti i membri hanno il livello di autorizzazione **Lettura**.
    
- La possibilità per i membri di invitare altri membri è disabilitata.
    
- La possibilità per gli utenti non membri di richiedere l'accesso è abilitata.
    
Di seguito è riportata la configurazione risultante.
  
![Protezione di livello riservato per un sito del team di SharePoint Online isolato.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online con riservatezza elevata

Un sito del team di SharePoint Online con riservatezza elevata è un sito del team isolato in cui le autorizzazioni sono controllate tramite l'appartenenza ai gruppi di SharePoint anziché l'appartenenza al gruppo di Office 365 associato al sito del team.
  
La creazione di un sito del team isolato per le informazioni e la collaborazione con riservatezza elevata richiede due passaggi principali.
  
### <a name="step-1-design-your-isolated-site"></a>Passaggio 1: Progettare un sito isolato

Per progettare un sito del team isolato è necessario stabilire:
  
- I gruppi di SharePoint e i livelli di autorizzazione.
    
- Il set di gruppi di accesso che saranno membri dei gruppi di SharePoint.
    
     Il set di gruppi di accesso consigliato è uno per i membri del sito, uno per i visualizzatori del sito e uno per gli amministratori del sito.
    
- Se verranno usati gruppi nidificati all'interno dei gruppi di accesso.
    
Ad esempio, la struttura dei gruppi e i livelli di autorizzazione consigliati sono simili ai seguenti:
  
|**Gruppo di SharePoint**|**Livello di autorizzazione**|**Gruppo di accesso (esempi)**|
|:-----|:-----|:-----|
|Membri di [nome sito]  <br/> |Modifica  <br/> |Membri di [nome sito]  <br/> |
|Visitatori di [nome sito]  <br/> |Lettura  <br/> |Visualizzatori di [nome sito]  <br/> |
|Proprietari di [nome sito]  <br/> |Controllo completo  <br/> |Amministratori di [nome sito]  <br/> |
   
Per un sito del team, i gruppi e i livelli di autorizzazione di SharePoint vengono creati per impostazione predefinita. È necessario stabilire i nomi dei gruppi di accesso.
  
Per i dettagli del processo di progettazione, vedere [Progettare un sito del team SharePoint Online isolato](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
### <a name="step-2-deploy-your-isolated-site"></a>Passaggio 2: Distribuire un sito isolato

Per distribuire un sito isolato è innanzitutto necessario:
  
- Determinare l’utente e i membri del gruppo di ciascun gruppo di accesso
    
- Creare gruppi di accesso e aggiungere l’utente e i membri dei gruppi
    
- Creare un sito del team isolato che utilizzi i gruppi di accesso
    
Per istruzioni dettagliate, vedere [Distribuire un sito del team di SharePoint Online isolato](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
I risultati di queste impostazioni delle autorizzazioni sono:
  
- Il gruppo di SharePoint **Proprietari di [nome sito]** contiene il gruppo di accesso degli amministratori del sito in cui tutti i membri hanno il livello di autorizzazione **Controllo completo**.
    
- Il gruppo di SharePoint **Membri di [nome sito]** contiene il gruppo di accesso dei membri del sito in cui tutti i membri hanno il livello di autorizzazione **Modifica**.
    
- Il gruppo di SharePoint **Visitatori di [nome sito]** contiene il gruppo di accesso dei visualizzatori del sito in cui tutti i membri hanno il livello di autorizzazione **Lettura**.
    
- La possibilità per i membri di invitare altri membri è disabilitata.
    
- La possibilità per gli utenti non membri di richiedere l'accesso è disabilitata.
    
Di seguito è riportata la configurazione risultante.
  
![Protezione di livello estremamente riservato per un team di SharePoint Online isolato.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.
  
## <a name="next-step"></a>Passaggio successivo

[Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>Vedere anche

[Protezione di file e siti di SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
