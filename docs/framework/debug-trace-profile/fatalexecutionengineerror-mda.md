---
title: fatalExecutionEngineError MDA
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12b94198b88111d559cfe372c28bdbf4b37e3fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43553070"
---
# <a name="fatalexecutionengineerror-mda"></a>fatalExecutionEngineError MDA
`fatalExecutionEngineError` Yönetilen hata ayıklama Yardımcısı (MDA), ortak dil çalışma zamanı (CLR) önemli bir hata algılandığında etkinleştirilir. İşlem sonlandırılacak.  
  
## <a name="symptoms"></a>Belirtiler  
 Beklenmeyen işlem sonlandırma. CLR hata çeşitli nedenlerden dolayı ortaya çıkabileceğinden diğer belirtileri belirlenemiyor.  
  
## <a name="cause"></a>Sebep  
 CLR fatally bozulmuş. Bu çoğunlukla veri bozulması, işlevleri ve CLR ile geçersiz veri geçirme hatalı biçimlendirilmiş platform çağrıları çağırır gibi sorunları sayısına göre neden kaynaklanır.  
  
## <a name="resolution"></a>Çözüm  
 Ek Mda'leri etkinleştirme, sorunun belirlenmesine yardımcı olabilir. Aşağıdaki Mda'leri özellikle sorunu tanılamada yararlı olabilir:  
  
-   [invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a>Çalışma zamanı üzerindeki etkisi  
 Bu MDA çalışma zamanı davranışı üzerinde etkisi yoktur.  
  
## <a name="output"></a>Çıkış  
 Önemli hata ve hatanın oluştuğu iş parçacığının kimliği hata kodu nedeniyle CLR işlevi adresi.  
  
## <a name="configuration"></a>Yapılandırma  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution.Cer>  
 [Yönetilen Hata Ayıklama Yardımcıları ile Hataları Tanılama](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
