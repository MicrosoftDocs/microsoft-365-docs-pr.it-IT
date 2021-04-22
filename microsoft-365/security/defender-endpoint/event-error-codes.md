---
title: Esaminare eventi ed errori tramite il Visualizzatore eventi
description: Ottenere descrizioni e ulteriori passaggi per la risoluzione dei problemi (se necessario) per tutti gli eventi segnalati dal servizio Microsoft Defender for Endpoint.
keywords: risoluzione dei problemi, visualizzatore eventi, riepilogo del registro, codice di errore, non riuscito, Servizio Microsoft Defender per endpoint, non può essere avviato, interrotto, non può essere avviato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933842"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Esaminare eventi ed errori tramite il Visualizzatore eventi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- Visualizzatore eventi
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Puoi esaminare gli ID evento nel [Visualizzatore eventi](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) nei singoli dispositivi.

Ad esempio, se i dispositivi non vengono visualizzati nell'elenco **Dispositivi,** potrebbe essere necessario cercare gli ID evento nei dispositivi. È quindi possibile utilizzare questa tabella per determinare ulteriori passaggi per la risoluzione dei problemi.

**Aprire il Visualizzatore eventi e trovare il registro eventi del servizio Microsoft Defender for Endpoint:**

1. Scegliere **Start** dal menu Windows, digitare **Visualizzatore eventi** e premere **INVIO.**

2. Nell'elenco dei registri, in **Log Summary**, scorrere fino a visualizzare **Microsoft-Windows-SENSE/Operational**. Fare doppio clic sull'elemento per aprire il registro.

   a.  Puoi anche accedere al registro espandendo Registri **applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **SENSE** e fai clic su **Operativo.**

   > [!NOTE]
   > SENSE è il nome interno usato per fare riferimento al sensore comportamentale che alimenta Microsoft Defender per Endpoint.

3. Gli eventi registrati dal servizio verranno visualizzati nel registro. Per un elenco degli eventi registrati dal servizio, vedere la tabella seguente.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>ID evento</th>
<th>Messaggio</th>
<th>Descrizione</th>
<th>Azione</th>
</tr>
<tr>
<td>1</td>
<td>Servizio Microsoft Defender for Endpoint avviato (versione <code>variable</code> ).</td>
<td>Si verifica durante l'avvio, l'arresto e l'onboarding del sistema.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>2</td>
<td>Arresto del servizio Microsoft Defender for Endpoint.</td>
<td>Si verifica quando il dispositivo viene arrestato o offboarded.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>3</td>
<td>Avvio del servizio Microsoft Defender for Endpoint non riuscito. Codice di errore: <code>variable</code> .</td>
<td>Il servizio non è stato avviato.</td>
<td>Esaminare altri messaggi per determinare le possibili cause e i passaggi per la risoluzione dei problemi.</td>
</tr>
<tr>
<td>4 </td>
<td>Microsoft Defender for Endpoint service ha contattato il server all'indirizzo <code>variable</code> .</td>
<td>Variabile = URL del Defender per i server di elaborazione degli endpoint.<br>
Questo URL corrisponde a quello visualizzato nel firewall o nell'attività di rete.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code> .</td>
<td>Variabile = URL del Defender per i server di elaborazione degli endpoint.<br>
Il servizio non è riuscito a contattare i server di elaborazione esterni in tale URL.</td>
<td>Verificare la connessione all'URL. Vedere <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>6 </td>
<td>Il servizio Microsoft Defender for Endpoint non è stato onboarding e non sono stati trovati parametri di onboarding.</td>
<td>Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</td>
<td>L'onboarding deve essere eseguito prima di avviare il servizio.<br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender for Endpoint service failed to read the onboarding parameters. Errore: <code>variable</code> .</td>
<td>Variabile = descrizione dettagliata dell'errore. Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender for Endpoint service failed to clean its configuration. Codice di errore: <code>variable</code> .</td>
<td><b>Durante l'onboarding:</b> Il servizio non è riuscito a pulire la configurazione durante l'onboarding. Il processo di onboarding continua. <br><br> <b>Durante l'offboarding:</b> Il servizio non è riuscito a pulire la configurazione durante l'offboarding. Il processo di offboarding è terminato ma il servizio continua a essere in esecuzione.
 </td>
<td><b>Onboarding:</b> Non è necessaria alcuna azione. <br><br> <b>Offboarding:</b> Riavviare il sistema.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>9 </td>
<td>Microsoft Defender for Endpoint service failed to change its start type. Codice di errore: <code>variable</code> .</td>
<td><b>Durante l'onboarding:</b> Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale. <br><br><b>Durante l'offboarding:</b> Impossibile modificare il tipo di avvio del servizio. Il processo di offboarding continua. </td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>10  </td>
<td>Microsoft Defender for Endpoint service failed to persist the onboarding information. Codice di errore: <code>variable</code> .</td>
<td>Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>11 </td>
<td>Onboarding o ri-onboarding di Defender per il servizio endpoint completato.</td>
<td>Il dispositivo è stato eseguito correttamente.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.<br>
La visualizzazione del dispositivo nel portale potrebbe richiedere diverse ore.</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint non è riuscito ad applicare la configurazione predefinita.</td>
<td>Il servizio non è stato in grado di applicare la configurazione predefinita.</td>
<td>Questo errore dovrebbe risolversi dopo un breve periodo di tempo.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender per l'ID dispositivo endpoint calcolato: <code>variable</code> .</td>
<td>Normale processo operativo.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>15 </td>
<td>Microsoft Defender for Endpoint non può avviare il canale di comando con URL: <code>variable</code> .</td>
<td>Variabile = URL del Defender per i server di elaborazione degli endpoint.<br>
Il servizio non è riuscito a contattare i server di elaborazione esterni in tale URL.</td>
<td>Verificare la connessione all'URL. Vedere <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a><br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>18 </td>
<td>Configurazione guidata (Windows Welcome) completata.</td>
<td>Il servizio verrà avviato solo al termine dell'installazione degli aggiornamenti di Windows.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>19</td>
<td>Configurazione guidata (Windows Welcome) non è ancora stata completata.</td>
<td>Il servizio verrà avviato solo al termine dell'installazione degli aggiornamenti di Windows.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.<br>
Se l'errore persiste dopo un riavvio del sistema, assicurati che tutti gli aggiornamenti di Windows siano installati completamente.</td>
</tr>
<tr>
<td>20</td>
<td>Impossibile attendere il completamento della Configurazione guidata (Installazione di Windows). Codice di errore: <code>variable</code> .</td>
<td>Errore interno.</td>
<td>Se l'errore persiste dopo un riavvio del sistema, assicurati che tutti gli aggiornamenti di Windows siano installati completamente.</td>
</tr>
<tr>
<td>25</td>
<td>Il servizio Microsoft Defender for Endpoint non è riuscito a reimpostare lo stato di integrità nel Registro di sistema. Codice di errore: <code>variable</code> .</td>
<td>Il dispositivo non è stato eseguito correttamente.
Verrà segnalata al portale, tuttavia il servizio potrebbe non essere visualizzato come registrato in SCCM o nel Registro di sistema.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender for Endpoint service non è riuscito a impostare lo stato di onboarding nel Registro di sistema. Codice di errore: <code>variable</code> .</td>
<td>Il dispositivo non è stato eseguito correttamente.<br>
Verrà segnalata al portale, tuttavia il servizio potrebbe non essere visualizzato come registrato in SCCM o nel Registro di sistema.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus. Processo di onboarding non riuscito. Codice di errore: <code>variable</code> .</td>
<td>In genere, Microsoft Defender Antivirus entra in uno stato passivo speciale se un altro prodotto antimalware in tempo reale viene eseguito correttamente nel dispositivo e il dispositivo segnala a Defender for Endpoint.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a><br>
Verificare che la protezione antimalware in tempo reale venga eseguita correttamente.</td>
</tr>
<tr>
<td>28</td>
<td>Registrazione del servizio Esperienze utente connesse all'endpoint e telemetria di Microsoft Defender per endpoint non riuscita. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a><br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>29</td>
<td>Impossibile leggere i parametri di offboarding. Tipo di errore: %1, Codice errore: %2, Descrizione: %3 </td>
<td>Questo evento si verifica quando il sistema non&#39;i parametri di offboarding.</td>
<td>Assicurati che il dispositivo abbia accesso a Internet, quindi esegui di nuovo l'intero processo di offboarding. Assicurati che il pacchetto di offboarding non sia scaduto.</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus. Codice di errore: <code>variable</code> .</td>
<td>In genere, Microsoft Defender Antivirus entra in uno stato passivo speciale se un altro prodotto antimalware in tempo reale viene eseguito correttamente nel dispositivo e il dispositivo segnala a Defender for Endpoint.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10</a><br>
Verificare che la protezione antimalware in tempo reale venga eseguita correttamente.</td>
</tr>
<tr>
<td>31</td>
<td>Annullamento della registrazione di Esperienze utente connesse e telemetria di Microsoft Defender per endpoint non riuscito. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows durante l'onboarding. Il processo di offboarding continua.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Verificare la presenza di errori con il servizio di telemetria di Windows.</a></td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process. Codice errore: %1</td>
<td>Si è verificato un errore durante l'offboarding.</td>
<td>Riavviare il dispositivo.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint service failed to persist SENSE GUID. Codice di errore: <code>variable</code> .</td>
<td>Un identificatore univoco viene usato per rappresentare ogni dispositivo che segnala al portale.<br>
Se l'identificatore non viene salvato in modo permanente, lo stesso dispositivo potrebbe comparire due volte nel portale.</td>
<td>Controlla le autorizzazioni del Registro di sistema nel dispositivo per assicurarti che il servizio possa aggiornare il Registro di sistema.</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a><br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>35</td>
<td>Il servizio Microsoft Defender for Endpoint non è riuscito a rimuovere se stesso come dipendenza dal servizio Esperienze utente connesse e telemetria. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows durante l'offboarding. Il processo di offboarding continua.
</td>
<td>Verificare la presenza di errori con il servizio dati di diagnostica Windows.</td>
</tr>
<tr>
<td>36</td>
<td>Registrazione delle esperienze utente connesse all'endpoint e del servizio di telemetria di Microsoft Defender per endpoint completata. Codice di completamento: <code>variable</code> .</td>
<td>Registrazione di Defender per Endpoint con il servizio Esperienze utente connesse e telemetria completata.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint Un modulo sta per superare la quota. Modulo: %1, Quota: {%2} {%3}, Percentuale di utilizzo della quota: %4.</td>
<td>Il dispositivo ha quasi usato la quota allocata della finestra corrente di 24 ore. Sta per essere limitato.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>38</td>
<td>La connessione di rete viene identificata come bassa. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Connessione a consumo: %2, Internet disponibile: %3, rete gratuita disponibile: %4.</td>
<td>Il dispositivo utilizza una rete a consumo/a pagamento e contatta il server con minore frequenza.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>39</td>
<td>La connessione di rete viene identificata normalmente. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Connessione a consumo: %2, Internet disponibile: %3, rete gratuita disponibile: %4.</td>
<td>Il dispositivo non utilizza una connessione a consumo/a pagamento e contatta il server come al solito.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>40</td>
<td>Lo stato della batteria è identificato come basso. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Stato batteria: %2.</td>
<td>Il dispositivo ha un livello di batteria basso e contatta il server con minore frequenza.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>41</td>
<td>Lo stato della batteria viene identificato come normale. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Stato batteria: %2.</td>
<td>Il dispositivo non ha un livello di batteria basso e contatta il server come al solito.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint component failed to perform action. Componente: %1, Azione: %2, Tipo eccezione: %3, Messaggio eccezione: %4</td>
<td>Errore interno. Avvio del servizio non riuscito.</td>
<td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint component failed to perform action. Componente: %1, Azione: %2, Tipo eccezione: %3, Errore eccezione: %4, Messaggio eccezione: %5</td>
<td>Errore interno. Avvio del servizio non riuscito.</td>
<td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding di Defender per il servizio endpoint completato.</td>
<td>Il servizio è stato offboarded.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>45</td>
<td>Impossibile eseguire la registrazione e avviare la sessione di traccia eventi [%1]. Codice errore: %2</td>
<td>Errore durante l'avvio del servizio durante la creazione della sessione ETW. Ciò ha causato un errore di avvio del servizio.</td>
<td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
<td>46</td>
<td>Impossibile registrare e avviare la sessione di traccia eventi [%1] a causa della mancanza di risorse. Codice errore: %2. Ciò è molto probabile perché sono presenti troppe sessioni di traccia eventi attive. Il servizio verrà ritentato tra 1 minuto.</td>
<td>Si è verificato un errore durante l'avvio del servizio durante la creazione della sessione ETW a causa della mancanza di risorse. Il servizio è stato avviato ed è in esecuzione, ma non segnala alcun evento sensore fino all'avvio della sessione ETW.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione. Il servizio tenterà di avviare la sessione ogni minuto.</td>
</tr>
<tr>
<td>47</td>
<td>La sessione di traccia eventi è stata registrata e avviata correttamente, recuperata dopo i precedenti tentativi non riusciti.</td>
<td>Questo evento segue l'evento precedente dopo l'avvio corretto della sessione ETW.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>48</td>
<td>Impossibile aggiungere un provider [%1] alla sessione di traccia eventi [%2]. Codice di errore: %3. Ciò significa che gli eventi di questo provider non verranno segnalati.</td>
<td>Impossibile aggiungere un provider alla sessione ETW. Di conseguenza, gli eventi del provider non vengono segnalati.</td>
<td>Controllare il codice di errore. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>Comando di configurazione cloud non valido ricevuto e ignorato. Versione: %1, stato: %2, codice errore: %3, messaggio: %4</td>
   <td>Ricevuto un file di configurazione non valido dal servizio cloud ignorato.</td>
   <td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>50</td>
   <td>Nuova configurazione cloud applicata correttamente. Versione: %1.</td>
   <td>È stata applicata correttamente una nuova configurazione dal servizio cloud.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>51</td>
   <td>Impossibile applicare la nuova configurazione cloud, versione: %1. Applicazione dell'ultima configurazione valida nota, versione %2.</td>
   <td>Ricevuto un file di configurazione non valido dal servizio cloud. L'ultima configurazione valida nota è stata applicata correttamente.</td>
   <td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>52</td>
   <td>Impossibile applicare la nuova configurazione cloud, versione: %1. Impossibile applicare anche l'ultima configurazione valida nota, versione %2. La configurazione predefinita è stata applicata correttamente.</td>
   <td>Ricevuto un file di configurazione non valido dal servizio cloud. Impossibile applicare l'ultima configurazione valida nota e la configurazione predefinita è stata applicata.</td>
   <td>Il servizio tenterà di scaricare un nuovo file di configurazione entro 5 minuti. Se non vedi l'evento #50 - contatta il supporto.</td>
</tr>
<tr>
   <td>53</td>
   <td>Configurazione cloud caricata dall'archiviazione persistente, versione: %1.</td>
   <td>La configurazione è stata caricata dall'archiviazione permanente all'avvio del servizio.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>55</td>
   <td>Impossibile creare l'autologger Secure ETW. Codice errore: %1</td>
   <td>Impossibile creare il logger ETW sicuro.</td>
   <td>Riavviare il dispositivo. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>56</td>
   <td>Impossibile rimuovere l'autologger Secure ETW. Codice errore: %1</td>
   <td>Impossibile rimuovere la sessione ETW sicura durante l'offboarding.</td>
   <td>Contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>57</td>
   <td>Acquisizione di uno snapshot del computer per la risoluzione dei problemi.</td>
   <td>È in corso la raccolta di un pacchetto di indagine, noto anche come pacchetto forense.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>59</td>
   <td>Avvio del comando: %1</td>
   <td>Avvio dell'esecuzione del comando di risposta.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>60</td>
   <td>Impossibile eseguire il comando %1, errore: %2.</td>
   <td>Impossibile eseguire il comando di risposta.</td>
   <td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>61</td>
   <td>I parametri del comando di raccolta dati non sono validi: SasUri: %1, compressionLevel: %2.</td>
   <td>Impossibile leggere o analizzare gli argomenti del comando di raccolta dati (argomenti non validi).</td>
   <td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>62</td>
   <td>Impossibile avviare il servizio Esperienze utente connesse e telemetria. Codice errore: %1</td>
   <td>Avvio del servizio Esperienze utente connesse e telemetria (diagtrack) non riuscito. La telemetria non di Microsoft Defender for Endpoint non verrà inviata da questo computer.</td>
   <td>Cercare altri suggerimenti per la risoluzione dei problemi nel registro eventi: Microsoft-Windows-UniversalTelemetryClient/Operational.</td>
</tr>
<tr>
   <td>63</td>
   <td>Aggiornamento del tipo di avvio del servizio esterno. Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3, codice di uscita: %4</td>
   <td>Tipo di avvio aggiornato del servizio esterno.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>64</td>
   <td>Avvio del servizio esterno arrestato. Nome: %1, codice di uscita: %2</td>
   <td>Avvio di un servizio esterno.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>65</td>
   <td>Impossibile caricare il driver Minifilter del componente Eventi di sicurezza Microsoft. Codice errore: %1</td>
   <td>Impossibile caricare il minifiltro MsSecFlt.sys filesystem.</td>
   <td>Riavviare il dispositivo. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>66</td>
   <td>Aggiornamento dei criteri: modalità latenza - %1</td>
   <td>Il criterio C&C connection frequency è stato aggiornato.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>68</td>
   <td>Il tipo di avvio del servizio è imprevisto. Nome servizio: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3</td>
   <td>Tipo di avvio del servizio esterno imprevisto.</td>
   <td>Correggere il tipo di avvio del servizio esterno.</td>
</tr>
<tr>
   <td>69</td>
   <td>Il servizio è stato arrestato. Nome servizio: %1</td>
   <td>Il servizio esterno è stato arrestato.</td>
   <td>Avviare il servizio esterno.</td>
</tr>
<tr>
   <td>70</td>
   <td>Aggiornamento dei criteri: consenti raccolta di esempio - %1</td>
   <td>Il criterio di raccolta di esempio è stato aggiornato.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>71</td>
   <td>Esecuzione del comando completata: %1</td>
   <td>Il comando è stato eseguito correttamente.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>72</td>
   <td>Tentativo di inviare il primo report del profilo computer completo. Codice risultato: %1</td>
   <td>Solo informativo.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>73</td>
   <td>Avvio di Sense per la piattaforma: %1</td>
   <td>Solo informativo.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>74</td>
   <td>Il tag del dispositivo nel Registro di sistema supera il limite di lunghezza. Nome tag: %2. Limite di lunghezza: %1.</td>
   <td>Il tag del dispositivo supera il limite di lunghezza.</td>
   <td>Usa un tag dispositivo più breve.</td>
</tr>
<tr>
   <td>81</td>
   <td>Impossibile creare l'autologger ETW di Microsoft Defender per endpoint. Codice errore: %1</td>
   <td>Impossibile creare la sessione ETW.</td>
   <td>Riavviare il dispositivo. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>82</td>
   <td>Impossibile rimuovere l'autologger ETW di Microsoft Defender for Endpoint. Codice errore: %1</td>
   <td>Impossibile eliminare la sessione ETW.</td>
   <td>Contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>84</td>
   <td>Impostare Windows Defender in esecuzione antivirus. Forza modalità passiva: %1, codice risultato: %2.</td>
   <td>Imposta la modalità di esecuzione del defender (attiva o passiva).</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>85</td>
   <td>Impossibile attivare il file eseguibile di Microsoft Defender for Endpoint. Codice errore: %1</td>
   <td>Impossibile eseguire l'eseguibile SenseIR.</td>
   <td>Riavviare il dispositivo. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>86</td>
   <td>L'avvio ha arrestato nuovamente il servizio esterno che dovrebbe essere in servizio. Nome: %1, codice di uscita: %2</td>
   <td>Avvio del servizio esterno di nuovo.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>87</td>
   <td>Impossibile avviare il servizio esterno. Nome: %1</td>
   <td>Impossibile avviare il servizio esterno.</td>
   <td>Contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>88</td>
   <td>Aggiornamento del tipo di avvio del servizio esterno di nuovo. Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3, codice di uscita: %4</td>
   <td>È stato aggiornato il tipo di avvio del servizio esterno.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>89</td>
   <td>Impossibile aggiornare il tipo di avvio del servizio esterno. Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3</td>
   <td>Impossibile aggiornare il tipo di avvio del servizio esterno.</td>
   <td>Contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>90</td>
   <td>Impossibile configurare System Guard Runtime Monitor per la connessione al servizio cloud nell'area geografica %1. Codice errore: %2</td>
   <td>System Guard Runtime Monitor non invierà dati di attestazione al servizio cloud.</td>
   <td>Controlla le autorizzazioni nel percorso di registrazione: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Se non vengono individuati problemi, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>91</td>
   <td>Impossibile rimuovere le informazioni sull'area geografica di System Guard Runtime Monitor. Codice errore: %1</td>
   <td>System Guard Runtime Monitor non invierà dati di attestazione al servizio cloud.</td>
   <td>Controlla le autorizzazioni nel percorso di registrazione: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Se non vengono individuati problemi, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>92</td>
   <td>Interruzione dell'invio della quota di dati informatici del sensore perché la quota dei dati viene superata. Riprenderà l'invio al termine del periodo di quota. State Mask: %1</td>
   <td>Superare il limite di limitazione.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>93</td>
   <td>Ripresa dell'invio dei dati informatici del sensore. State Mask: %1</td>
   <td>Riprendere l'invio di dati informatici.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>94</td>
   <td>Il file eseguibile di Microsoft Defender for Endpoint è stato avviato</td>
   <td>L'eseguibile SenseCE è stato avviato.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>95</td>
   <td>L'eseguibile di Microsoft Defender for Endpoint è terminato</td>
   <td>L'eseguibile SenseCE è terminato.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>96</td>
   <td>Microsoft Defender for Endpoint Init ha chiamato. Codice risultato: %2</td>
   <td>L'eseguibile SenseCE ha chiamato inizializzazione MCE.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>97</td>
   <td>Ci sono problemi di connettività al cloud per lo scenario DLP</td>
   <td>Esistono problemi di connettività di rete che influiscono sul flusso di classificazione DLP.</td>
   <td>Controllare la connettività di rete.</td>
</tr>
<tr>
   <td>98</td>
   <td>La connettività al cloud per lo scenario DLP è stata ripristinata</td>
   <td>La connettività alla rete è stata ripristinata e il flusso di classificazione DLP può continuare.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>99</td>
   <td>Rilevato l'errore seguente durante la comunicazione con il server: (%1). Risultato: (%2)</td>
   <td>Si è verificato un errore di comunicazione.</td>
   <td>Per ulteriori dettagli, controllare gli eventi seguenti nel registro eventi.</td>
</tr>
<tr>
   <td>100</td>
   <td>Avvio del file eseguibile di Microsoft Defender for Endpoint non riuscito. Codice errore: %1</td>
   <td>Impossibile avviare il file eseguibile SenseCE.</td>
   <td>Riavviare il dispositivo. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
   <td>102</td>
   <td>Il file eseguibile Di rilevamento e risposta di Microsoft Defender per endpoint di rete è stato avviato</td>
   <td>L'eseguibile SenseNdr è stato avviato.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
   <td>103</td>
   <td>L'eseguibile microsoft Defender for Endpoint Network Detection and Response è terminato</td>
   <td>L'eseguibile SenseNdr è terminato.</td>
   <td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
</tbody>
</table>

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Argomenti correlati
- [Aggiungere di dispositivi Windows 10](configure-endpoints.md)
- [Configurare le impostazioni del proxy del dispositivo e della connettività Internet](configure-proxy-internet.md)
- [Risolvere i problemi di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
