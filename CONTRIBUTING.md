# Contributing Guidelines

Thank you for your interest in contributing to our project. Whether it's a bug report, new feature, correction, or additional 
documentation, we greatly value feedback and contributions from our community.

Please read through this document before submitting any issues or pull requests to ensure we have all the necessary 
information to effectively respond to your bug report or contribution.

## Index

* [Introduction](#introduction)
  * [Reporting Bugs/Feature Requests](#reporting-bugsfeature-requests)
  * [Contributing via Pull Requests](#contributing-via-pull-requests)
  * [Finding contributions to work on](#finding-contributions-to-work-on)
  * [Code of Conduct](#code-of-conduct)
  * [Security issue notifications](#security-issue-notifications)
  * [Licensing](#licensing)
* [Prerequisites](#prerequisites)
* [Working with CloudFormation](#working-with-cloudformation)
* [Working with the Web UI](#working-with-the-web-ui)

## Introduction

### Reporting Bugs/Feature Requests

We welcome you to use the GitHub issue tracker to report bugs or suggest features.

Quando si presenta un problema, si prega di controllare (https://github.com/aws-sample), per assicurarsi che qualcun altro non abbia già segnalato il problema. Prova a includere quante più informazioni possibile. 


### Codice di condotta
Questo progetto ha adottato il [Codice di condotta di Amazon Open Source] (https://aws.github.io/code-of-conduct).
Per ulteriori informazioni, consultare le [Domande frequenti sul codice di condotta] (https://aws.github.io/code-of-conduct-faq) o contattare
opensource-codeofconduct@amazon.com con ulteriori domande o commenti.

### Notifiche di problemi di sicurezza
Se scopri un potenziale problema di sicurezza in questo progetto ti chiediamo di avvisare AWS / Amazon Security tramite la 
[pagina di segnalazione delle vulnerabilità] (http://aws.amazon.com/security/vulnerability-reporting/). ** Non ** creare un problema pubblico su github.

### Licenze
Vedi il file [LICENSE] (https://github.com/aws-samples/amazon-rekognition-engagement-meter/blob/master/LICENSE) per le licenze del progetto. 

## Prerequisiti
Le seguenti applicazioni sono richieste per contribuire:

* Node.js >=v8
* AWS CLI

Per iniziare, esegui `npm install`.

## Lavorare con CloudFormation
Il codice sorgente di CloudFormation si trova nella directory `src / cfn`. Il modello utilizza una risorsa personalizzata per effettuare alcune chiamate API 
iniziali ad Amazon Rekognition e per popolare il bucket S3 con le risorse statiche dell'interfaccia utente Web. Il codice sorgente lambda si trova nella directory `src / funzioni / setup`.

## Lavorare con l'interfaccia utente Web
Per sviluppare una versione locale dell'interfaccia utente Web:
1. Distribuire il modello CloudFormation.
2. Una volta distribuito lo stack CloudFormation, un output `url` sarà disponibile da CloudFormation nel formato di` https: // <s3-bucket-url> / index.html`. Scarica il file `https: // <s3-bucket-url> / settings.js` nella cartella` src / web-ui / public / `. In questo modo, sarà possibile sviluppare localmente utilizzando il gateway API e l'ID pool Cognito che CloudFormation ha appena creato in AWS. Nota che `settings.js` è" * gitignored * ".
3. Eseguire `npm start`. Il browser aprirà automaticamente l'interfaccia utente con la ricarica a caldo abilitata.
Per apportare modifiche, modifica i file nella cartella `src / web-ui`.
