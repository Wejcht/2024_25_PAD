# Dokumentacja techniczna integracji z Google Drive

**Nazwa projektu:** `zse-pad-cloud-example`
**Cel: ** Celem projektu jest stworzenie integracji aplikacji z usługą Google Drive.

## Wymagane biblioteki do działania projektu

Aby zainstalować każdy z pakietów należy uruchomić visual studio 2022 i na pasku odszukać menedżer pakietów nugget, następnie wyszukać podane niżej

- Google.Apis.Auth.OAuth2
- Google.Apis.Drive.v3
- Google.Apis.Services
- Google.Apis.Util.Store

## Etapy konfiguracji

### 1. Utworzenie projektu w Google Cloud

- Wejdź na Google Cloud Console
- Utwórz nowy projekt
- Włącz API Google Drive
- Utwórz dane logowania typu "Desktop App"
- Pobierz plik **credentials.json** i umieść go w folderze aplikacji

### 2. Konfiguracja aplikacji

- Załaduj dane logowania
- Zainicjalizuj usługę **DriveService** z autoryzacją

### 3. Struktura folderu /src aplikacji

```
src/
├── Program.cs
├── DriveServiceHelper.cs
├── MainWindow.xaml
└── MainWindow.xaml.cs
```

## Przykład użycia metody ``UploadFile()`` z klasy **DriveServiceHelper**

```
var fileId = DriveServiceHelper.UploadFile("plik.zip", "backup.zip");
Console.WriteLine(\$"ID pliku: {fileId}");
```

## Uwagi końcowe

- Autoryzacja użytkownika następuje przy pierwszym uruchomieniu
- Token zapisywany jest lokalnie w pliku token.json
- Plik DriveServiceHelper.cs pełni rolę pomocniczą do autoryzacji i wysyłki