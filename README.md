# TestPkg

[![CI](https://github.com/IAFahim/com.iafahim.test-pkg/actions/workflows/ci.yml/badge.svg)](https://github.com/IAFahim/com.iafahim.test-pkg/actions)
[![License](https://img.shields.io/github/license/IAFahim/com.iafahim.test-pkg)](LICENSE)

**Build outside Unity. Ship as Unity package.**

```bash
dotnet test -c Release
git push
```

## Install

Add to `Packages/manifest.json`:

```json
"com.iafahim.test-pkg": "https://github.com/IAFahim/com.iafahim.test-pkg.git"
```

Or Unity → Package Manager → Add from git URL.

## How it works

```
Runtime/*.cs          ← your code (uses Unity.Mathematics types)
  │
  ├─ dotnet build     ← UnityMathematics.NoDeps NuGet
  │   dotnet test     ← same NuGet, no Unity needed
  │
  └─ Unity            ← com.unity.mathematics UPM via package.json
```

No DLLs. No Unity project needed to develop. Same source compiles in both.

## Dev

```bash
dotnet restore
dotnet test -c Release
```

MIT © 2026 IAFahim
