---
title: Başlangıç Ayarları Şeması
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 68f37e3efca784b94be90d5779c9bc402f144448
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530340"
---
# <a name="startup-settings-schema"></a>Başlangıç Ayarları Şeması
Başlangıç ayarları, uygulamanın çalışması gereken ortak dil çalışma zamanı sürümünü belirtin.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Uygulama yalnızca sürüm 1.0 ortak dil çalışma zamanının desteklediğini belirtir. Çalışma zamanı sürüm 1.1 ile oluşturulan uygulamaların kullanması gereken  **\<supportedRuntime >** öğesi.|  
|[\<supportedRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Uygulamanın hangi ortak dil çalışma zamanı sürümünü desteklediğini belirtir.|  
|[\<Başlangıç >](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|İçeren  **\<requiredRuntime >** ve  **\<supportedRuntime >** öğeleri.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırma Dosyası Şeması](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver > hangi çalışma zamanı sürümünün kullanılacağını belirtme](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
