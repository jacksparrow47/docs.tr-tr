---
title: -baseaddress (C# Derleyici Seçenekleri)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: 58d1511387c93841f49d6ced934b492fe097876b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518526"
---
# <a name="-baseaddress-c-compiler-options"></a>-baseaddress (C# Derleyici Seçenekleri)
**- Baseaddress** seçeneği bir DLL yüklemek için tercih edilen temel adresini belirtmenize olanak sağlar. Bu seçeneği kullanmak neden ve ne zaman hakkında daha fazla bilgi için bkz: [Larry Osterman'ın blog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).  
  
## <a name="syntax"></a>Sözdizimi  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Arguments  
 `address`  
 DLL için temel adres. Bu adres, ondalık, onaltılık veya sekizlik sayı olarak belirtilebilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir DLL için varsayılan taban adresi, .NET Framework ortak dil çalışma zamanı tarafından ayarlanır.  
  
 Bu adres alt sıra Word'de yuvarlanacağı dikkat edin. Örneğin, 0x11110001 belirtirseniz 0x11110000 için yuvarlanır.  
  
 Bir DLL için imzalama işlemini tamamlamak için SN kullanın. EXE -R seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açın **özellikleri** sayfası.  
  
2.  Tıklayın **derleme** özellik sayfası.  
  
3.  Tıklayın **Gelişmiş** düğmesi.  
  
4.  Değiştirme **DLL temel adresi** özelliği.  
  
     Bu derleyici seçeneğini program üzerinden ayarlamak için bkz: <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
- [C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/index.md)  
- [Proje ve Çözüm Özelliklerini Yönetme](/visualstudio/ide/managing-project-and-solution-properties)
