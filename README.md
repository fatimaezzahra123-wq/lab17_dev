# 📡 ReceiverDemo — BroadcastReceiver Android Lab

## 🎬 Démo vidéo

[![Demo ReceiverDemo](https://img.youtube.com/vi/9QiKkQpjhqQ/0.jpg)](https://youtu.be/9QiKkQpjhqQ?si=fnrBz8k0cu4j0W3Q)

▶️ **[Voir la démo sur YouTube](https://youtu.be/9QiKkQpjhqQ?si=fnrBz8k0cu4j0W3Q)**

---

## 📌 Objectif

Application Android démontrant l'utilisation des **BroadcastReceiver** — composants qui réagissent aux événements diffusés par le système ou par l'application elle-même.

---

## ✨ Fonctionnalités

| Fonctionnalité | Type | Déclencheur |
|---|---|---|
| Détection du mode avion | Receiver **dynamique** | `ACTION_AIRPLANE_MODE_CHANGED` |
| Démarrage du téléphone | Receiver **statique** | `BOOT_COMPLETED` |
| Broadcast personnalisé | Receiver **custom** | Bouton dans l'app |

---

## 🗂️ Structure du projet

```
app/
├── manifests/
│   └── AndroidManifest.xml
└── java/com.example.receiverdemo/
    ├── MainActivity.java           # Gestion du cycle register/unregister
    ├── AirplaneModeReceiver.java   # Receiver dynamique (mode avion)
    ├── BootReceiver.java           # Receiver statique (boot)
    └── CustomEventReceiver.java    # Receiver custom intra-app
```

---

## ⚙️ Configuration

- **Language** : Java  
- **Minimum SDK** : API 24 (Android 7.0)  
- **Target SDK** : API 34+

---

## 🚀 Lancer le projet

```bash
# Cloner le repo
git clone https://github.com/TON_USERNAME/ReceiverDemo.git

# Ouvrir dans Android Studio
# File → Open → sélectionner le dossier ReceiverDemo

# Lancer sur émulateur ou téléphone physique
# Cliquer sur ▶️ Run
```

---

## 🧪 Tests

**Test 1 — Custom Broadcast**
- Cliquer `Envoyer Custom Broadcast`
- Toast attendu : `Custom reçu : Bonjour depuis le custom broadcast !`

**Test 2 — Mode Avion**
- Cliquer `Activer Receiver Avion`
- Aller dans Paramètres → activer/désactiver le mode avion
- Toast attendu : `Mode Avion ACTIVÉ` / `Mode Avion DÉSACTIVÉ`

**Test 3 — Boot Receiver**
```bash
adb reboot
```
- Toast attendu au démarrage : `Téléphone démarré - Receiver statique activé !`

---

## 📚 Concepts clés

**Receiver dynamique** — enregistré/désenregistré dans le code (`registerReceiver` / `unregisterReceiver`). Actif uniquement quand l'Activity est vivante.

**Receiver statique** — déclaré dans `AndroidManifest.xml`. Peut se déclencher même si l'app est fermée.

**`exported="false"`** — obligatoire depuis Android 12 pour bloquer les broadcasts externes malveillants.

**`onDestroy()`** — toujours désenregistrer les receivers dynamiques pour éviter les fuites mémoire.

---

## 👩‍💻 Auteur

FATIMAEZZAHRA ENNASSIRI
