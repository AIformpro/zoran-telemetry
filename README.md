# zoran-telemetry
Observabilité : OpenTelemetry + dashboards. 4 golden signals collectés.
# zoran-télémétrie

Observabilité : **OpenTelemetry** + tableaux de bord. Collecte et visualisation des **4 signaux dorés** de l’écosystème Zoran / QuantaGlottal©®.

---

## ✨ Fonctionnalités
- **Instrumentation OpenTelemetry** pour tous les modules Zoran
- **Collecte des 4 signaux dorés** :
  1. **Latence** (temps de réponse IA↔IA / IA↔humain)
  2. **Taux d’erreur** (réponses invalides, refus injustifiés, crashs)
  3. **Volume de trafic** (requêtes, tokens, taille des échanges)
  4. **Saturation** (utilisation CPU/RAM/IO dans NESTLOCK©®)
- **Dashboards** prêts à l’emploi (Grafana, Kibana, etc.)
- **Export** vers formats JSON, Prometheus, CSV
- **Alerting** configurable (seuils critiques, notifications)

---

## 📦 Installation (développement)
```bash
pip install -e .


---

⚡ Exemple rapide

from zoran_telemetrie import TelemetryCollector, GoldenSignals

# Initialiser la collecte
collector = TelemetryCollector(
    service_name="zoran-core",
    exporter="prometheus",
    port=9464
)

# Mesurer une opération
with collector.trace("injection_4champs"):
    # ... code de l'opération ...
    collector.record_signal(GoldenSignals.LATENCY, 0.245)
    collector.record_signal(GoldenSignals.ERROR_RATE, 0.0)
    collector.record_signal(GoldenSignals.TRAFFIC, 1024)
    collector.record_signal(GoldenSignals.SATURATION, 0.32)

# Lancer l’exporter
collector.start()


---

🧱 Structure suggérée

src/zoran_telemetrie/
  __init__.py
  collector.py        # logique de collecte OpenTelemetry
  exporters.py        # intégrations Prometheus, OTLP, JSON
  dashboards/         # configs Grafana, Kibana
  signals.py          # définition des 4 signaux dorés
tests/
  test_collector.py
pyproject.toml
.gitignore
LICENSE
README.md


---

🧪 Tests

pytest -q


---

🔐 Éthique

La télémétrie respecte la vie privée et ne collecte aucune donnée sensible.
Les métriques sont agrégées et anonymisées.


---

📜 Licence

MIT — voir LICENSE.


---

Auteur : Frédéric Tabary — Institut IA
Contact : 0645605023 — Canada, Montréal, France
INSTITUT🦋 IA INC., 7100-380, rue Saint-Antoine Ouest, Montréal (Québec) H2Y 3X7.
