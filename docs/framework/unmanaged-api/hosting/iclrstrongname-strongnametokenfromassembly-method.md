---
title: ICLRStrongName::StrongNameTokenFromAssembly Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd083193fa8fed2abc8a1a498325f7edd89bc96
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43658006"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a>ICLRStrongName::StrongNameTokenFromAssembly Yöntemi
Belirtilen derleme dosyasından bir güçlü ad simgesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `wszFilePath`  
 [in] Derleme için taşınabilir yürütülebilir (PE) dosya yolu.  
  
 `ppbStrongNameToken`  
 [out] Döndürülen tanımlayıcı ad belirteç.  
  
 `pcbStrongNameToken`  
 [out] Tanımlayıcı ad belirtecinin bayt cinsinden boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK` yöntemi başarıyla tamamlandı Aksi takdirde hata olduğunu gösteren HRESULT değerini (bkz [ortak HRESULT değerlerini](https://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).  
  
## <a name="remarks"></a>Açıklamalar  
 Genel anahtar kısaltılmış bir tanımlayıcı ad belirtecidir. Oluşturulan derlemeyi imzalamak için kullanılacak ortak anahtarı bir 64-bit karma belirtecidir. Belirteç, tanımlayıcı ad bütünleştirilmiş kodun bir parçası olan ve derleme meta verileri okuyabilir.  
  
 Belirteç oluşturulduktan sonra çağırmalısınız [Iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) ayrılan belleği serbest bırakmak için yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MetaHost.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [StrongNameTokenFromAssemblyEx Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [ICLRStrongName Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
