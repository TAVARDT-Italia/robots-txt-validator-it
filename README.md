<p align="center">
  <a href="https://ag.tavardt.com/it/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Verificatore di Robots.txt e Governance dei Crawler

[![Verificatore Robots.txt](https://img.shields.io/badge/TAVARDT-Robots.txt-5b3cf5.svg)](https://tools.tavardt.com/it/verificatore-robots-txt/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Il **TAVARDT Verificatore di Robots.txt** fornisce verifica automatizzata delle direttive di scansione, conformità allo standard RFC 9309 e governance dei bot di intelligenza artificiale in Italia.

***

## Architettura del Protocollo e Matrice di Governance

I crawler dei motori di ricerca e gli agenti di intelligenza artificiale consultano il robots.txt per determinare le sezioni accessibili e le policy di indicizzazione. Errori come blocchi globali accidentali o sitemap omesse causano la perdita immediata della visibilità organica.

Questo strumento diagnostico analizza la sintassi delle regole, rileva ritardi eccessivi di scansione, valuta le autorizzazioni per i bot di IA e verifica le dichiarazioni delle sitemap partendo da 100 punti base senza dipendenze esterne.

Il motore di scansione esamina le direttive secondo lo standard ufficiale RFC 9309 e le prassi dei crawler internazionali:

<table>
  <thead>
    <tr>
      <th>Vettore di Governance</th><th>Criterio di Controllo</th><th>Deduzione</th><th>Impatto su Scansione e SEO</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Regola di Disallow Globale</strong></td><td>Verifica blocchi <code>User-agent: *</code> con <code>Disallow: /</code> privi di eccezioni <code>Allow:</code>.</td><td>-50 pts</td><td>Blocco critico che impedisce ai motori di ricerca di indicizzare l'intero portale.</td>
    </tr>
    <tr>
      <td><strong>Dichiarazione Sitemap XML</strong></td><td>Controlla la presenza di almeno una direttiva <code>Sitemap:</code> collegata a un feed valido.</td><td>-20 pts</td><td>Riduce l'efficienza di scansione e rallenta l'indicizzazione dei contenuti recenti.</td>
    </tr>
    <tr>
      <td><strong>Crawl-Delay Eccessivo</strong></td><td>Identifica direttive <code>Crawl-delay</code> superiori a 5 secondi applicate globalmente.</td><td>-15 pts</td><td>Restringe il crawl budget dei motori nei siti con cataloghi estesi.</td>
    </tr>
    <tr>
      <td><strong>Governance dei Bot di IA</strong></td><td>Mappa le politiche di accesso per 12 agenti di intelligenza artificiale (GPTBot, ClaudeBot, PerplexityBot, ecc.).</td><td>Segnale di Audit</td><td>Tutela la proprietà dei contenuti contro l'estrazione non autorizzata per il training di modelli.</td>
    </tr>
    <tr>
      <td><strong>Raggiungibilità dell'Host</strong></td><td>Verifica codice HTTP 200 e stabilità della connessione durante il recupero del file.</td><td>Punteggio azzerato a 0</td><td>Host non raggiungibile che impedisce l'acquisizione delle direttive di indicizzazione.</td>
    </tr>
  </tbody>
</table>

### Scala di Governance e Livelli di Stato

Il sistema definisce un punteggio complessivo di qualità classificando lo stato del file robots.txt:

* <strong>80 a 100 (COMPLIANT)</strong>: Piena conformità allo standard RFC 9309; sitemap dichiarate, nessun blocco globale e regole ben strutturate.
* <strong>50 a 79 (WARNING)</strong>: Direttive funzionanti ma con margini di ottimizzazione, come assenza di sitemap o ritardi elevati.
* <strong>0 a 49 (CRITICAL)</strong>: Blocco totale dei crawler, inaccessibilità del file o regole disallow distruttive per l'indicizzazione.

***

## Installazione ed Esecuzione

Sviluppato unicamente con moduli standard di Python 3.8+, senza dipendenze esterne.

```bash
git clone https://github.com/TAVARDT-Italia/robots-txt-validator-it.git
cd robots-txt-validator-it
```

### Esecuzione Standard CLI

```bash
python robots_validator.py https://esempio.it
```

### Output Strutturato per Pipeline in JSON

```bash
python robots_validator.py https://esempio.it -j
```

***

## Linee Guida Nazionali e Governance Digitale

La gestione rigorosa del robots.txt rispetta le indicazioni nazionali in materia di affidabilità e governance dei servizi digitali. Regole di esclusione corrette proteggono percorsi riservati garantendo al contempo l'indicizzazione dei contenuti destinati agli utenti.

Si raccomanda l'inserimento di controlli automatici del file robots.txt nelle routine di deployment per prevenire problemi di de-indicizzazione.

***

## Domande Frequenti Tecniche

### In che modo il verificatore individua i blocchi globali di indicizzazione?

Il motore analizza i blocchi con <code>User-agent: *</code>. Qualora trovi la regola <code>Disallow: /</code> senza istruzioni compensatorie <code>Allow:</code>, detrae 50 punti ed emette un allarme critico.

### Perché l'omissione della sitemap viene penalizzata?

Dichiarare la sitemap nel robots.txt agevola i motori di ricerca nella scoperta delle risorse ufficiali. L'omissione della direttiva <code>Sitemap:</code> comporta una penalità di 20 punti.

### Quali problematiche comporta un crawl-delay elevato?

Un <code>Crawl-delay</code> superiore a 5 secondi limita la capacità di scansione dei bot sui portali ampi, ritardando l'indicizzazione delle nuove pagine. Tale configurazione determina una penalità di 15 punti.

### Quali bot di intelligenza artificiale vengono monitorati?

La procedura traccia dodici crawler di intelligenza artificiale: GPTBot, ChatGPT-User, ClaudeBot, Anthropic-AI, PerplexityBot, CCBot, Cohere-AI, Google-Extended, Applebot-Extended, Omgilibot, Diffbot e ByteSpider.

### Cosa indicano i livelli di stato e conformità?

Un punteggio tra 80 e 100 corrisponde allo stato COMPLIANT sotto RFC 9309. Tra 50 e 79 punti il livello è WARNING, mentre sotto i 50 punti lo stato è CRITICAL, segnalando blocchi gravi.

***

## Supporto Tecnico e Consulenza Digitale

Per verifiche approfondite di SEO tecnica, governance dei crawler e standard di conformità web, contattare gli esperti di **TAVARDT**.

***

## Link Utili

* **Portale Aziendale:** https://ag.tavardt.com/it/
* **Suite di Diagnostica:** https://tools.tavardt.com/it/
* **Contatto Tecnico:** https://ag.tavardt.com/it/contatto/

***

### Licenza
Rilasciato sotto licenza MIT.

***

© 2026 TAVARDT. Tutti i diritti riservati.
