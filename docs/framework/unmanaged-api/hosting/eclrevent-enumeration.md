---
title: EClrEvent Numaralandırması
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d79b0c1fed0178f8463174fe981f250d6f6fb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430713"
---
# <a name="eclrevent-enumeration"></a>EClrEvent Numaralandırması
Ana bilgisayar geri aramalar kaydedebilirsiniz ortak dil çalışma zamanı (CLR) olaylarını açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`Event_ClrDisabled`|Önemli bir CLR hata belirtir.|  
|`Event_DomainUnload`|Belirli bir eklentiyi belirtir <xref:System.AppDomain>.|  
|`Event_MDAFired`|Yönetilen hata ayıklama Yardımcısı (MDA) ileti oluşturulan belirtir.|  
|`Event_StackOverflow`|Bir yığın taşması hata oluştuğunu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ana bilgisayar tarafından açıklanan olay türlerinden herhangi birini için geri çağırmaları kaydedebilirsiniz `EClrEvent` yöntemlerini çağırarak [Iclroneventmanager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) arabirimi. Konak bir işaretçi çağırarak bu arabirime alır [Iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) yöntemi.  
  
 `Event_CLRDisabled` Ve `Event_DomainUnload` olayları yükseltilmiş birden çok kez ve bir kaldırma veya CLR devre dışı bırakma sinyal için farklı iş parçacıklarından.  
  
 `Event_MDAFired` Olayını oluşturulmasını bir [Mdaınfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) MDA ileti ayrıntılarını içeren örneği. Mda'lar hakkında daha fazla bilgi için bkz: [yönetilen hata ayıklama Yardımcıları ile hataları tanılama](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IActionOnCLREvent Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Barındırma Sabit Listeleri](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
