# Plugins auf der Plattform einreichen

Das Einreichen eines Plugins ist bei uns nur für GitHub-Projekte möglich, die eine bestimmte Datei im Hauptverzeichnis beinhalten. Die Datei muss den Namen deinplugin.yaml tragen und eine vorgegebene Form besitzen. Die komplette Spezifikation der deinplugin.yaml-Datei findest du in einem von uns angelegten GitHub-Repository. Wenn du direkt einsteigen willst, kannst du aber auch die unten gezeigten Beispiele anschauen oder dich an der deinplugin.yaml-Datei bereits eingereichter Plugins orientieren.

Außerdem haben wir eine [Schema-Datei](schema.json) bereitgestellt, welche eine deinplugin.yaml-Datei validieren kann.

## Aufbau der deinplugin.yaml-Datei

Im Folgenden wird ein loser Aufbau für verschiedene Komponenten der Spezifikations-Datei dargestellt. Das Herzstück ist dabei das `SpecsObject`, welches in der deinplugin.yaml-Datei untergebracht ist. Die anderen Objekte sind innerhalb des Hauptobjektes zu finden.
Zwingend benötigte Felder sind mit einem Sternchen (*) gekennzeichnet.

### `SpecsObject`
```yaml
specVersion*: int
type*: String
  {plugin, lib}
name*: [LanguageObject]
authors*: [String]
download: DownloadObject
supportedPlatforms: [String]
  {spigot, paper, sponge}
supportedGameVersions: String (Semantic Version)
category*: String
  {adminTool, devTool, chat, economy, game, protection, roleplay, worldManagement, misc}
dependencies: [DependencyObject]
introduction*: [LanguageObject]
description*: [LanguageObject]
installation: [LanguageObject]
tags: [String]
images: [String]
icon: String
videoSources: [String]
```

### `LanguageObject`
**Info**: Wird kein separates LanguageObject angelegt (zB. mittels name: Test), so wird automatisch ein LanguageObject mit dem key null generiert.
```yaml
key: String
text* String
```

### `DownloadObject`
```yaml
url*: String
name*: String
```

### `DependencyObject`
```yaml
url*: String
name*: String
versionRange: String (Semantic Version)
required*: Boolean
```

## Bedeutung der Felder aus der Metadatei

`specVersion`: Version der Spezifikation (aktuelle Version: 1)\
`type`: Art des angebotenen Downloads (aktuell plugin oder lib)\
`name`: Anzeigename des Downloads\
`authors`: Autoren des Downloads\
`download`: Externer Download, der nicht unter GitHub-Releases bereitgestellt wird\
`supportedPlatforms`: Liste aller nterstützten Plattformen (aktuell `spigot`, `paper` und/oder `sponge`)\
`supportedGameVersions`: Unterstütze Minecraft-Versionen\
`category`: Kategorie des Downloads (aktuell: `adminTool`, `devTool`, `chat`, `economy`, `game`, `protection`, `roleplay`, `worldManagement`, oder `misc`)\
`dependencies`: Andere Bibliotheken, die für die reibungslose Nutzung des Downloads benötigt werden.\
`introduction`: Einleitungstext des Downlaods. Markdown-Format.\
`description`: Beschreibungstext des Downloads. Markdown-Format.\
`installation`: Installations-Guide des Downlaods. Markdown-Format.\
`tags`: Tags zur besseren Einordnung des Downloads.\
`images`: Bilder des Downloads.\
`icon`: Icon des Downloads.\
`videoSources`: Videos zum Download.\

## Beispiele

Die folgenden Beispiele sollen helfen, das Metadaten-Format besser zu verstehen.
Sie können außerdem als Template für das Erstellen einer eigenen Metadatei genutzt werden.

- [Beispiel: Minimale deinplugin.yaml-Datei](YAML-EXAMPLE/example_min.yaml)
- [Beispiel: Vollständige deinplugin.yaml-Datei](YAML-EXAMPLE/example_full.yaml)