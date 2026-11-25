# Verificatore di Robots.txt e Direttive di Scansione

[![Verificatore Robots.txt](https://img.shields.io/badge/TAVARDT-Robots.txt-5b3cf5.svg)](https://tools.tavardt.com/it/verificatore-robots-txt/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Audit tecnico per file robots.txt, verifica della corretta accessibilita dei motori di ricerca, gestione dei bot IA e individuazione di blocchi errati.

Sviluppato e gestito dalla divisione di scansione web e infrastrutture di **TAVARDT**.

***

## Funzionalita dell'Audit di Robots.txt

* **Prevenzione di Blocchi di Indicizzazione**: Individuazione di regole errate che escludono i bot dai contenuti principali.
* **Governance dei Bot IA e Motori di Ricerca**: Configurazione selettiva per crawler tradizionali e scraper di intelligenza artificiale.
* **Dichiarazione della Sitemap XML**: Verifica della presenza e raggiungibilita della direttiva `Sitemap:`.
* **Controllo della Sintassi di Esclusione**: Analisi di percorsi protetti, comandi `Allow`, `Disallow` e `Crawl-delay`.
* **Punteggio di Efficienza di Scansione**: Indice tecnico da 0 a 100 con raccomandazioni per il webmaster.

***

## Installazione ed Esecuzione

Richiede Python 3.8 o superiore senza dipendenze esterne.

```bash
git clone https://github.com/TAVARDT-Italia/robots-txt-validator-it.git
cd robots-txt-validator-it
python robots_validator.py https://esempio.it
```

Per l'output in formato JSON:

```bash
python robots_validator.py https://esempio.it -json
```

***

## Piattaforma di Diagnosi Online

Per simulare l'accesso dei bot e verificare i file robots.txt:

* **Verificatore di Robots.txt Ufficiale**
* **[Portale Aziendale TAVARDT](https://ag.tavardt.com/it/)**

***

## Consulenza in Scansione Web e SEO Tecnico

Per progetti avanzati di governance dei bot conformi a Standard W3C e Protocollo di Esclusione Robot, contattare **TAVARDT**.

***

## Link Utili

* **Portale Aziendale:** https://ag.tavardt.com/it/
* **Suite di Diagnostica:** https://tools.tavardt.com/it/
* **Contatto Tecnico:** https://ag.tavardt.com/it/contatto/

***

### Licenza
Rilasciato sotto licenza MIT. Per maiores informações, consultare il file [LICENSE](LICENSE).

***

© 2026 TAVARDT. Tutti i diritti riservati.
