---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c04bff4070b0f1c288c8853e5045fbf670d8e9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655675"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Derleyicinin birinci bir uyarı hata olarak ele almasını neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terim|Tanım|  
|---|---|  
|+ &#124; -|İsteğe bağlı. Varsayılan olarak, `-warnaserror-` olan etkili; uyarılar derleyici çıktı dosyası üretmeyi engellemez. `-warnaserror` Aynı seçeneği olarak `-warnaserror+`, hata olarak kabul edilmesi uyarıları oluşturulmasına neden olur.|  
|`numberList`|İsteğe bağlı. Uyarı Kimliği virgülle ayrılmış listesi olduğu numaraları `-warnaserror` seçeneği uygulanır. Hiçbir uyarı kimliği belirtilmezse, `-warnaserror` seçenek, tüm uyarıları için geçerlidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `-warnaserror` Seçeneği tüm uyarıları hata olarak değerlendirir. Uyarılar yerine hata olarak bildirilen normalde bildirilen iletiler. Derleyici uyarıları olarak aynı uyarı sonraki oluşumlarını bildirir.  
  
 Varsayılan olarak, `-warnaserror-` yalnızca vericidir uyarıların neden olur, etkilidir. `-warnaserror` Aynı seçeneği olarak `-warnaserror+`, hata olarak kabul edilmesi uyarıları oluşturulmasına neden olur.  
  
 Hata olarak kabul edilmesi için yalnızca birkaç belirli uyarıları istiyorsanız, hata olarak değerlendirmek için uyarı numaralarını virgülle ayrılmış bir listesini belirtebilirsiniz.  
  
> [!NOTE]
>  `-warnaserror` Seçeneği denetlemez nasıl uyarılar görüntülenir. Kullanım [- nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) uyarılarını devre dışı bırakma seçeneği.  
  
|-Tüm uyarıları Visual Studio IDE içinde hata olarak ele warnaserror ayarlamak için|  
|---|  
|1.  Seçili bir projeyi **Çözüm Gezgini**. Üzerinde **proje** menüsünde tıklatın **özellikleri**. <br />2.  Tıklatın **derleme** sekmesi.<br />3.  Emin olun **tüm uyarıları devre dışı bırakmak** onay kutusunu olarak işaretli.<br />4.  Denetleme **tüm uyarıları hata ele** onay kutusu.|  
  
|-Visual Studio IDE hataları gibi belirli uyarıları kabul warnaserror ayarlamak için|  
|---|  
|1.  Seçili bir projeyi **Çözüm Gezgini**. Üzerinde **proje** menüsünde tıklatın **özellikleri**.<br />2.  Tıklatın **derleme** sekmesi.<br />3.  Emin olun **tüm uyarıları devre dışı bırakmak** onay kutusunu olarak işaretli.<br />4.  Emin olun **tüm uyarıları hata ele** onay kutusunu olarak işaretli.<br />5.  Seçin **hata** gelen **bildirim** hata olarak kabul uyarı bitişik sütun.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod derlerken `In.vb` ve birinci bulduğu her uyarı için bir hata görüntülenecek derleyici yönlendirir.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod derlerken `T2.vb` ve yalnızca kullanılmayan yerel değişkenler (42024) için uyarıyı hata olarak kabul eder.  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Visual Basic'teki Uyarıları Yapılandırma](/visualstudio/ide/configuring-warnings-in-visual-basic)
