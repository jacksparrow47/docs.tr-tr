---
title: '-target: appcontainerexe (C# Derleyici Seçenekleri)'
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 8042e1888da63d26f3639ed372bfc7fadcd515f0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507880"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-target: appcontainerexe (C# Derleyici Seçenekleri)
Kullanırsanız **-target: appcontainerexe** derleyici seçeneği, derleyici bir uygulama kapsayıcısında çalıştırılması gereken bir Windows yürütülebilir (.exe) dosyası oluşturur. Bu seçenek eşdeğerdir [-target: winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) için tasarlanmıştır ancak [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanın bir uygulama kapsayıcısında çalışmasını zorunlu kılmak için bu seçenek bir bit ayarlar [Taşınabilir Çalıştırılabilir](/windows/desktop/Debug/pe-format) (PE) dosyası. Söz konusu bit ayarlandığında, CreateProcess yöntemi yürütülebilir dosyayı bir uygulama kapsayıcısı dışında çalıştırmayı denerse bir hata oluşur.  
  
 Kullanmadığınız sürece [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) seçeneği, çıkış dosyası adını içeren giriş dosyasının adını alır [ana](../../../csharp/programming-guide/main-and-command-args/index.md) yöntemi.  
  
 Tüm bir komut isteminde bu seçeneği belirttiğinizde, kadar sonraki dosyalar **-out** veya **-hedef** seçeneği, yürütülebilir dosyayı oluşturmak için kullanılır.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Bu derleyici seçeneğini IDE içinde ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, projeniz için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  Üzerinde **uygulama** sekmesinde **çıkış türü** listesinde **Windows Store App**.  
  
     Bu seçenek yalnızca kullanılabilir [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] uygulama şablonları.  
  
 Bu derleyici seçeneğini program üzerinden ayarlamak hakkında daha fazla bilgi için bkz. <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut `filename.cs` yalnızca bir uygulama kapsayıcısında çalıştırılabilen bir Windows yürütülebilir dosyasına.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

- [-target (C# Derleyici Seçenekleri)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [-target: winexe (C# Derleyici Seçenekleri)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
- [C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/index.md)
