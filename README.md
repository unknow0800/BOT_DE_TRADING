# Binance Trading Bot

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg?style=for-the-badge&logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-green.svg?style=for-the-badge&logo=pandas)](https://pandas.pydata.org/)
[![Binance](https://img.shields.io/badge/Binance-API-yellow.svg?style=for-the-badge&logo=binance)](https://binance.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

Bot de trading automatique en Python utilisant l’API Binance et des indicateurs techniques pour générer des signaux d’achat, de vente ou d’attente sur la paire **BTCUSDT**.

## Présentation

Ce projet a pour objectif de créer un bot simple capable de :

- récupérer les données de marché depuis Binance
- analyser ces données avec des indicateurs techniques
- générer un signal de trading
- envoyer automatiquement un ordre d’achat ou de vente

Le bot fonctionne actuellement avec une stratégie basée sur le **RSI**, la **SMA 50** et la **SMA 200**.

## Stratégie utilisée

Le signal de trading est défini selon les règles suivantes :

- **Buy** : RSI < 30 et SMA 50 > SMA 200
- **Sell** : RSI > 70 et SMA 50 < SMA 200
- **Hold** : aucune condition validée

Cette logique permet de combiner un signal de surachat/survente avec une confirmation de tendance.

## Fonctionnement

À chaque cycle, le script :

1. récupère les dernières bougies du marché
2. transforme les données en DataFrame avec `pandas`
3. calcule les indicateurs techniques avec `ta`
4. analyse la dernière ligne des données
5. décide d’acheter, de vendre ou de ne rien faire
6. relance le processus dans une boucle continue

## Technologies utilisées

- Python
- pandas
- ta
- python-binance

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/ton-username/ton-repo.git
cd ton-repo
```

### 2. Créer un environnement virtuel

```bash
python -m venv venv
```

### 3. Activer l’environnement virtuel

#### Sous Windows
```bash
venv\Scripts\activate
```

#### Sous Linux / macOS
```bash
source venv/bin/activate
```

### 4. Installer les dépendances

```bash
pip install -r requirements.txt
```

## Dépendances

Le projet utilise principalement les bibliothèques suivantes :

```txt
pandas
ta
python-binance
```

## Configuration

Avant de lancer le bot, il faut renseigner les clés API Binance dans le script :

```python
api_key = "YOUR_API_KEY"
api_secret = "YOUR_SECRET_KEY"
```

## Lancer le projet

```bash
python bot.py
```

## Structure du projet

```bash
.
├── bot.py
├── README.md
├── requirements.txt
└── .gitignore
```

## Exemple de sortie

```bash
Récupération des données de marché...
Dernier prix: 64250.10, RSI: 28.44, SMA 50: 64020.50, SMA 200: 63110.80, Signal: buy
```

## Objectif du projet

Ce projet a été réalisé dans un but d’apprentissage pour :

- manipuler une API de trading
- exploiter des données financières avec Python
- utiliser des indicateurs techniques
- comprendre la logique de base d’un bot de trading automatisé

## Limites actuelles

Le projet reste simple et peut être amélioré sur plusieurs points :

- pas de stop loss
- pas de take profit
- pas de backtesting
- pas de gestion avancée du risque
- pas de journalisation avec logs
- clés API directement dans le code

## Améliorations possibles

- stocker les clés API dans un fichier `.env`
- ajouter un système de logs
- intégrer un stop loss / take profit
- améliorer la stratégie avec d’autres indicateurs
- faire du backtesting sur données historiques
- gérer plusieurs cryptomonnaies

## Avertissement

Ce projet est à but éducatif uniquement.  
Le trading automatique comporte des risques financiers importants.  
Ne jamais utiliser ce bot sur un compte réel sans tests approfondis.

## Auteur

Projet développé par **MARC DOWE**
