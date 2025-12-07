# 🛠️ Setup Guide - The Forge Loader

## 🎯 Übersicht

Dieses Repository lädt dein **privates** The-Forge Script über Base64-encodierte Dateien.

## 🔑 Schritt 1: GitHub Token erstellen

1. Gehe zu: [github.com/settings/tokens](https://github.com/settings/tokens)
2. Klicke auf **"Generate new token"** → **"Generate new token (classic)"**
3. Gib dem Token einen Namen: z.B. `The-Forge-Loader`
4. Setze das Ablaufdatum (z.B. 90 Tage oder "No expiration")
5. Wähle die **"repo"** Berechtigung (voller Zugriff auf private Repositories)
6. Klicke auf **"Generate token"**
7. **WICHTIG:** Kopiere den Token sofort! Er wird nur einmal angezeigt!

## 💻 Schritt 2: Python Script vorbereiten

1. Lade `encode_and_upload.py` herunter:
   ```bash
   wget https://raw.githubusercontent.com/DJB5001/The-Forge-Loader/main/encode_and_upload.py
   ```

2. Öffne die Datei mit einem Text-Editor

3. Ersetze diese Zeile:
   ```python
   GITHUB_TOKEN = "YOUR_GITHUB_TOKEN_HERE"
   ```
   Mit deinem echten Token:
   ```python
   GITHUB_TOKEN = "ghp_deinTokenHier123456789"
   ```

4. Speichere die Datei

## 🚀 Schritt 3: Script ausführen

### Voraussetzungen:
- Python 3.6 oder höher
- `requests` Library installiert

Installiere requests falls nicht vorhanden:
```bash
pip install requests
```

### Script starten:
```bash
python encode_and_upload.py
```

oder:
```bash
python3 encode_and_upload.py
```

## ✅ Schritt 4: Verifizieren

Das Script wird:
1. ✅ Alle 13 Lua-Dateien aus **The-Forge** (privat) herunterladen
2. 🔒 Jede Datei in Base64 encodieren
3. 📤 Alle encoded Dateien in **The-Forge-Loader/encoded/** hochladen
4. ✅ Erfolgsmeldung anzeigen

Überprüfe danach:
- [github.com/DJB5001/The-Forge-Loader/tree/main/encoded](https://github.com/DJB5001/The-Forge-Loader/tree/main/encoded)
- Dort sollten jetzt 13 `.b64` Dateien sein

## 🎮 Schritt 5: In Roblox verwenden

Jetzt kannst du den Loader in Roblox verwenden:

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/DJB5001/The-Forge-Loader/main/loader.lua"))()
```

## 🔄 Updates durchführen

Wenn du Änderungen an The-Forge machst:

1. Pushe die Änderungen zu **The-Forge** (privates Repo)
2. Führe `encode_and_upload.py` erneut aus
3. Alle Dateien werden automatisch aktualisiert

## 🔒 Sicherheit

### ✅ Vorteile:
- Dein Quellcode bleibt in einem privaten Repository
- Base64-Encoding erschwert das Lesen
- Nur du hast Zugriff auf das Original

### ⚠️ Hinweise:
- **Niemals** deinen GitHub Token committen!
- Base64 ist keine echte Verschlüsselung
- Erfahrene User können den Code noch dekodieren
- Für echte Sicherheit: Serverseitige Lösung verwenden

## 🛠️ Troubleshooting

### "Failed to get file: 404"
- Überprüfe, ob die Datei in The-Forge existiert
- Stelle sicher, dass der Dateiname korrekt ist

### "Failed to upload: 401 Unauthorized"
- Dein Token ist ungültig oder abgelaufen
- Erstelle einen neuen Token mit "repo" Berechtigung

### "Failed to upload: 403 Forbidden"
- Du hast keine Schreibrechte für The-Forge-Loader
- Stelle sicher, dass du der Owner bist

### "ModuleNotFoundError: No module named 'requests'"
```bash
pip install requests
```

## 📞 Support

Bei Problemen:
- Discord: discord.gg/MTXnFfHXW9
- GitHub Issues: [Issues öffnen](https://github.com/DJB5001/The-Forge-Loader/issues)

---

**Viel Erfolg! 🚀**
