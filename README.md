# Binance Trading Bot BTC/USDT

Un bot de trading automatique en Python utilisant l’API Binance et des indicateurs techniques simples pour générer des signaux d’achat et de vente sur la paire **BTCUSDT**.

## Aperçu

Ce projet récupère les données du marché via Binance, calcule plusieurs indicateurs techniques, puis décide d’acheter, vendre ou attendre selon des conditions définies dans le script.

La stratégie utilisée repose sur :

- le **RSI** pour détecter des zones de surachat ou de survente
- la **SMA 50** et la **SMA 200** pour confirmer la tendance

## Fonctionnement

Le bot effectue les étapes suivantes :

1. Récupère les dernières bougies du marché
2. Convertit les données dans un DataFrame avec pandas
3. Calcule les indicateurs techniques
4. Génère un signal de trading : `buy`, `sell` ou `hold`
5. Envoie un ordre au marché sur Binance si les conditions sont remplies
6. Répète le processus dans une boucle continue

## Indicateurs utilisés

- **RSI (Relative Strength Index)** sur 14 périodes
- **SMA 50**
- **SMA 200**

### Conditions de signal

- **buy** : RSI < 30 et SMA 50 > SMA 200
- **sell** : RSI > 70 et SMA 50 < SMA 200
- **hold** : sinon

## Technologies

- Python
- pandas
- ta
- python-binance

## Installation

Clone le projet :

```bash
git clone https://github.com/ton-username/ton-repo.git
cd ton-repo
```

Crée un environnement virtuel :

```bash
python -m venv venv
```

Active l’environnement :

### Windows
```bash
venv\Scripts\activate
```

### Linux / macOS
```bash
source venv/bin/activate
```

Installe les dépendances :

```bash
pip install -r requirements.txt
```

## Dépendances

Ce projet utilise :

- `pandas`
- `ta`
- `python-binance`

## Configuration

Dans ton script, remplace les valeurs suivantes par tes vraies clés API Binance :

```python
api_key = "YOUR_API_KEY"
api_secret = "YOUR_SECRET_KEY"
```

## Lancer le bot

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

## Exemple de sortie console

```bash
Récupération des données de marché...
Dernier prix: 64250.10, RSI: 28.44, SMA 50: 64020.50, SMA 200: 63110.80, Signal: buy
```

## Limites

Ce projet est un projet d’apprentissage. Il ne comprend pas encore :

- de backtesting
- de stop loss
- de take profit
- de gestion avancée du risque
- de journalisation propre
- de protection avancée des clés API

## Améliorations possibles

- Utiliser un fichier `.env` pour stocker les clés
- Ajouter des logs avec `logging`
- Ajouter un stop loss / take profit
- Faire du backtesting sur données historiques
- Gérer plusieurs paires
- Corriger précisément la temporisation pour qu’elle corresponde à l’intervalle utilisé

## Avertissement

Ce bot est fourni uniquement à des fins éducatives.  
Le trading de cryptomonnaies comporte des risques financiers importants.

## Auteur

Projet réalisé par **Ton Nom**
