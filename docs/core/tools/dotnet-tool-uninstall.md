---
title: DotNet Aracı kaldırma komutu - .NET Core CLI
description: Dotnet araç kaldırma komutu makinenizden belirtilen .NET Core genel aracı kaldırır.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 93a43e19df4c7f220ac1e2d2db397cba4d791e83
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539880"
---
# <a name="dotnet-tool-uninstall"></a>DotNet Aracı kaldırma

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>Ad

`dotnet tool uninstall` -Belirtilen kaldırır [.NET Core genel aracı](global-tools.md) makinenizden.

## <a name="synopsis"></a>Özeti

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a>Açıklama

`dotnet tool uninstall` Komutu, .NET Core Araçları Genel makinenizden kaldırmak bir yol sağlar. Komutunu kullanmak için aşağıdakilerden birini kullanarak bir kullanıcı genelinde aracı kaldırmak istediğiniz belirtmeniz gerekir `--global` nerede yolunu belirtin veya seçeneği kullanılarak yüklenen aracı `--tool-path` seçeneği.

## <a name="arguments"></a>Arguments

`PACKAGE_NAME`

.NET Core genel kaldırmak için Aracı'nı içeren NuGet paket adı/kimliği. Paket adını kullanarak bulabilirsiniz [dotnet araç listesi](dotnet-tool-list.md) komutu.

## <a name="options"></a>Seçenekler

`-g|--global`

Aracının kaldırılması için kullanıcı genelinde yüklemesinden olduğunu belirtir. İle birleştirilemez `--tool-path` seçeneği. Bu seçeneği belirtmezseniz, belirtmeniz gerekir `--tool-path` seçeneği.

`-h|--help`

Komut için kısa bir Yardım yazdırır.

`--tool-path <PATH>`

Konum, genel Aracı'nı kaldırmak konumu belirtir. YOL mutlak veya göreli olabilir. İle birleştirilemez `--global` seçeneği. Bu seçeneği belirtmezseniz, belirtmeniz gerekir `--global` seçeneği.

## <a name="examples"></a>Örnekler

Kaldırır [dotnetsay](https://www.nuget.org/packages/dotnetsay/) genel aracı:

`dotnet tool uninstall -g dotnetsay`

Kaldırır [dotnetsay](https://www.nuget.org/packages/dotnetsay/) belirli bir Windows klasörden genel aracı:

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

Kaldırır [dotnetsay](https://www.nuget.org/packages/dotnetsay/) belirli Linux/macOS klasöründe bulunan genel aracı:

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>Ayrıca bkz.

* [.NET core Araçları Genel](global-tools.md)