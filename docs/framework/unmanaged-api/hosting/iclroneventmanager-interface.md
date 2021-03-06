---
title: ICLROnEventManager Arabirimi
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c22dfa99d8069c060a525a9ae2cbef73d6625898
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434109"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager Arabirimi
Kaydolun ve ortak dil çalışma zamanı (CLR) olayları için geri çağırmaları kaydı için ana izin yöntemleri sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[RegisterActionOnEvent Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|Belirtilen olay için bir geri çağırma işaretçi kaydeder.|  
|[UnregisterActionOnEvent Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|Belirtilen olay için daha önce kaydedilmiş geri işaretçi kaydını siler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Konak kaydetmek ve olay geri aramalar kaydı için bir başvuru edinir `ICLROnEventManager` çağırarak [Iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) yöntemi.  
  
> [!NOTE]
>  Tarafından tanımlanan olayları [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) birden çok kez ve bir kaldırma veya CLR devre dışı bırakma sinyal için farklı iş parçacıklarından tetiklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EClrEvent Sabit Listesi](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [IActionOnCLREvent Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
