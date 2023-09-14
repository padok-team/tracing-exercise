# Tracing Exercise

## Objectifs

Cet exercice a pour but de vous familiariser avec le tracing dans Kubernetes.

Voici les objectifs de cet exercice :
- Déployer un serveur et un client qui communiquent entre eux et sont instrumentés avec opentelemetry
- Déployer un collecteur opentelemetry
- Déployer un jaeger
- Connecter l'otel collector au jaeger
- Vérifier que les traces sont bien envoyées à jaeger

## Contenu du repo

- `src/` : code du serveur et du client (en GO)
- `kubernetes/` : manifests Kubernetes à déployer

## Prérequis

- La CLI [kubectl](https://kubernetes.io/docs/reference/kubectl/)
- git
- Connaissances basiques de Kubernetes

## Exercice

### Mise en place

- Cloner le repository
- Récupérer le fichier kubeconfig du cluster playground auprès de votre formateur
- Configurer la variable d'environnement KUBECONFIG pour cibler le cluster playground
- Tester la connexion à Kubernetes avec la commande `kubectl get nodes`

### Déploiement du serveur et du client

Nous allons déployer un serveur et un client écrits en Go. Le client va régulièrement appeler le serveur.

- Déployer le serveur et le client (dans `kubernetes/client.yaml` et `kubernetes/server.yaml`)
  - Vérifier leurs logs : ils doivent afficher des messages d'erreur car ils ne peuvent pas contacter le collecteur opentelemetry
- Déployer le collecteur opentelemetry

- Vérifier dans les manifests Kubernetes du client et du serveur : quelle variable peut-on modifier pour changer l'adresse du collecteur opentelemetry ?



- Deploy server & client
- For the moment, they log errors because they cannot contact the otel collector
- Deploy otel collector
- Check logs
- Deploy jaeger
- Connect otel collector to jaeger
- Check jaeger UI

<!-- Laisser l'erreur TLS jaeger -->
<!-- Mettre des liens vers les bonnes docs pour les variables à trouver -->
<!-- Déploiement de stakater reloader -->
