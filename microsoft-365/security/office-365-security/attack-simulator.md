---
title: Simulatore di attacchi in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: In qualità di amministratore globale di Office 365, è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale colpisca la propria azienda.
ms.openlocfilehash: e5f304a7c706875216c58330b1225d341b2b59df
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971934"
---
# <a name="attack-simulator-in-office-365"></a>Simulatore di attacchi in Office 365

**Riepilogo** Se si è un amministratore globale di Office 365 o un amministratore della sicurezza e l'organizzazione dispone di Office 365 Advanced Threat Protection Plan 2, che include le [funzionalità di analisi e di risposta alle minacce](office-365-ti.md), è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base. Leggere questo articolo per ulteriori informazioni.

## <a name="the-attacks"></a>Gli attacchi

Sono attualmente disponibili tre tipi di simulazioni di attacco:

- [Nome visualizzato Spear-attacco di phishing](#display-name-spear-phishing-attack)

- [Attacco spray per la password](#password-spray-attack)

- [Attacco per la password con forza bruta](#brute-force-password-attack)

Affinché l'avvio di un attacco venga eseguito correttamente, verificare che l'account utilizzato per eseguire gli attacchi simulati utilizzi l'autenticazione a più fattori. Inoltre, è necessario essere un amministratore globale di Office 365 o un amministratore della sicurezza. Per ulteriori informazioni sui ruoli e le autorizzazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

Per accedere a simulatore di attacco, &amp; nel centro sicurezza e conformità scegliere **Threat Management** \> **Attack Simulator**.

## <a name="before-you-begin"></a>Prima di iniziare...

Assicurarsi che l'utente e l'organizzazione soddisfino i seguenti requisiti per il simulatore di attacco:

- La posta elettronica dell'organizzazione è ospitata in Exchange Online. (Attack Simulator non è disponibile per i server di posta elettronica locali.)

- Si è un amministratore globale o un amministratore di sicurezza di Office 365

- L'autenticazione a più fattori e l' [accesso condizionale](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) sono attivati, almeno per l'account di amministratore globale di Office 365 e gli amministratori della sicurezza che utilizzeranno simulatore di attacco. (Idealmente, l'autenticazione a più fattori e l'accesso condizionale sono attivati per tutti gli utenti dell'organizzazione.)

- L'organizzazione dispone [di Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), con simulatore di attacco visibile &amp; nel centro sicurezza e conformità (andare a **Threat Management** \> **Attack Simulator**)

    ![Threat Management-simulatore d'attacco](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a>Nome visualizzato Spear-attacco di phishing

Il phishing è un termine generico per una vasta serie di attacchi classificati come un attacco stile di social engineering. Questo attacco è concentrato sul phishing Spear, un attacco più mirato che si rivolge a un gruppo specifico di persone o di un'organizzazione. In genere, un attacco personalizzato con alcuni ricognizione eseguito e utilizzando un nome visualizzato che genererà la fiducia nel destinatario, ad esempio un messaggio di posta elettronica che sembra provenire da un dirigente all'interno dell'organizzazione.

Questo attacco è incentrato sull'eventualità di modificare il messaggio a cui sembra abbia avuto origine cambiando il nome visualizzato e l'indirizzo di origine. Quando gli attacchi Spear-phishing hanno esito positivo, cyberattackers accedere alle credenziali degli utenti.

### <a name="to-simulate-a-spear-phishing-attack"></a>Per simulare un attacco di Spear-phishing

![Comporre il corpo della posta elettronica](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

È possibile creare l'editor HTML RTF direttamente nel campo **corpo del messaggio di posta elettronica** o collaborare con l'origine HTML.

1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.

2. Specificare un nome di campagna significativo per l'attacco o selezionare un modello.

   ![Pagina iniziale di phishing](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. Specificare i destinatari di destinazione. Può trattarsi di singoli o gruppi nell'organizzazione. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.

   ![Selezione destinatario](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. Configurare i dettagli di posta elettronica di phishing.

   ![Configurare i dettagli della posta elettronica](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   La formattazione HTML può essere complessa o di base come necessario per la campagna. Poiché il formato del messaggio di posta elettronica è HTML, è possibile inserire immagini e testo per migliorare la credibilità. È possibile controllare l'aspetto del messaggio ricevuto nel client di posta elettronica di ricezione.

5. Specificare il testo per il campo **from (Name)** . Si tratta del campo che viene visualizzato nel **nome visualizzato** nel client di posta elettronica di ricezione.

6. Specificare il testo o il campo **da** . Si tratta del campo che viene visualizzato come indirizzo di posta elettronica del mittente nel client di posta elettronica di ricezione.

   È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo l'indirizzo di posta elettronica viene effettivamente risolto nel client di ricezione, facilitando un modello di attendibilità molto elevato) oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere effettivamente, ma è necessario seguire il formato di un indirizzo SMTP valido, ad esempio `user@domainname.extension`.

7. Usando il selettore a discesa, selezionare un URL del server di accesso di phishing che rispecchi il tipo di contenuto che si avrà all'interno dell'attacco. È possibile scegliere tra diversi URL a tema, ad esempio recapito dei documenti, tecnico, retribuzione e così via. Questo è effettivamente l'URL a cui gli utenti designati devono fare clic.

8. Specificare un URL della pagina di destinazione personalizzata. In questo modo gli utenti verranno reindirizzati a un URL specificato al termine di un attacco con esito positivo. Se si dispone di un training di sensibilizzazione interno, ad esempio, è possibile specificarlo qui.

9. Specificare il testo per il campo **Subject** . Si tratta del campo che viene visualizzato come **nome del soggetto** nel client di posta elettronica di ricezione.

10. Comporre il **corpo del messaggio di posta elettronica** che riceverà il destinatario.

    `${username}`inserisce il nome della destinazione nel corpo della posta elettronica.

    `${loginserverurl}`inserisce l'URL in cui si desidera che gli utenti di destinazione clicchino

11. Fare clic su **Avanti,** quindi su **fine** per avviare l'attacco. Il messaggio di posta elettronica di phishing Spear viene recapitato alle cassette postali dei destinatari.

## <a name="password-spray-attack"></a>Attacco spray per la password

Un attacco di spruzzatura della password in un'organizzazione viene in genere utilizzato dopo che un attore cattivo ha acquisito un elenco di utenti validi dal tenant. L'attore cattivo conosce le password comuni utilizzate dalle persone. Si tratta di un attacco ampiamente utilizzato, poiché si tratta di un attacco a basso costo da eseguire e più difficile da rilevare rispetto alla forza bruta.

Questo attacco consente di specificare una password comune rispetto a una base di utenti di grandi dimensioni.

### <a name="to-simulate-a-password-spray-attack"></a>Per simulare un attacco spray per la password

1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.

2. Specificare il nome di una campagna significativa per l'attacco.

3. Specificare i destinatari di destinazione. Può trattarsi di singoli o gruppi nell'organizzazione. Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.

4. Specificare una password da utilizzare per l'attacco. Ad esempio, una password comune e pertinente che è possibile `Summer2019`provare è. Un altro potrebbe `Fall2019`essere, `Password1`o.

5. Scegliere **fine** per avviare l'attacco.

## <a name="brute-force-password-attack"></a>Attacco per la password con forza bruta

Un attacco di password con forza bruta nei confronti di un'organizzazione viene in genere utilizzato dopo che un attore non valido ha acquisito un elenco di utenti chiave dal tenant. Questo attacco si concentra sul tentativo di un set di password su un singolo account utente.

### <a name="to-simulate-a-brute-force-password-attack"></a>Per simulare un attacco di password con forza bruta

1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.

2. Specificare il nome di una campagna significativa per l'attacco.

3. Specificare il destinatario di destinazione. Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.

4. Specificare un set di password da utilizzare per l'attacco. A tale scopo, è possibile utilizzare un file di testo (con estensione txt) per l'elenco delle password. Il file di testo non può superare i 10 MB nelle dimensioni dei file. Utilizzare una password per riga e assicurarsi di includere un ritorno a capo dopo l'ultima password dell'elenco.

5. Scegliere **fine** per avviare l'attacco.

## <a name="new-features-in-attack-simulator"></a>Nuove funzionalità in Attack Simulator

Nuove funzionalità sono state aggiunte di recente a Attack Simulator. Ad esempio:

- Funzionalità di creazione di report avanzate. La possibilità di visualizzare dati quali il tempo più rapido (o più lento) per aprire un messaggio di posta elettronica di simulazione di attacco, il tempo più rapido (o più lento) per fare clic su un collegamento nel messaggio e altre visualizzazioni.

- Editor modelli di posta elettronica. La possibilità di creare un modello di posta elettronica personalizzato e riutilizzabile che è possibile utilizzare per simulazioni di attacco future.

- Importazione del destinatario CSV. La possibilità di utilizzare un file. csv per importare l'elenco dei destinatari di destinazione invece di usare lo strumento di selezione Rubrica.

Altre nuove caratteristiche stanno per essere attaccate al simulatore d'attacco. Ad esempio:

- Simulazione di phishing del payload degli allegati. La possibilità di utilizzare un allegato come payload per la simulazione di phishing al posto di un URL.

Visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per vedere cosa c'è in sviluppo, cosa è in uscita e cosa è già stato avviato.

## <a name="see-also"></a>Vedere anche

[Descrizione del servizio Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Office 365 Advanced Threat Protection](office-365-atp.md)
