# BigEcho releases

Публичный репозиторий для готовых установщиков BigEcho.

Здесь не хранится исходный код приватного приложения. GitHub может показывать
source archives для каждого Release, но это архивы этого metadata-репозитория:
README, manifests и служебные JSON-файлы.

## Файлы релиза

Каждый production-релиз публикуется по тегу `vMAJOR.MINOR.PATCH` и содержит
versioned installer names:

- `BigEcho-3.3.0-macos-arm64.dmg` — macOS Apple Silicon.
- `BigEcho-3.3.0-macos-intel.dmg` — macOS Intel.
- `BigEcho-3.3.0-windows-x64.exe` — Windows NSIS installer.
- `BigEcho-3.3.0-windows-x64.msix` — Windows MSIX, только если релиз собран с
  полным Windows signing-набором.

Актуальный релиз доступен на странице:

https://github.com/chakveselchak/big_echo_releases/releases/latest

## Manifests и checksums

Публикуемые manifests:

- `latest.json` — manifest выбранного актуального релиза.
- `releases/vX.Y.Z.json` — immutable manifest конкретной версии.
- `SHA256SUMS` — checksums установщиков в GitHub Release assets.

Проверка на macOS/Linux:

```bash
shasum -a 256 -c SHA256SUMS
```

Проверка конкретного Windows installer:

```powershell
Get-FileHash .\BigEcho-3.3.0-windows-x64.exe -Algorithm SHA256
```

## Что не публикуется

В этот репозиторий нельзя добавлять:

- исходники `big_echo_premium`;
- приватные GitHub Actions artifacts;
- логи сборки с secrets;
- сертификаты, P12/PFX/P8 ключи или provisioning profiles.
