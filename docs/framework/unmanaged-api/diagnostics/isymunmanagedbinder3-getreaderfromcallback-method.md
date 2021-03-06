---
title: ISymUnmanagedBinder3::GetReaderFromCallback Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f44d50f6736e0698fd876eedab78dbf41434af4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426322"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback Metodu
Uygulamak ya da geri çağırma ya da tedarik olanak tanır. bir `IID_IDiaReadExeAtRVACallback` veya `IID_IDiaReadExeAtOffsetCallback` bellekten hata ayıklama dizin bilgileri elde edilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `importer`  
 [in] Meta veri alma arayüzü için bir işaretçi.  
  
 `fileName`  
 [in] Dosya adı için bir işaretçi.  
  
 `searchPath`  
 [in] Arama yolu için bir işaretçi.  
  
 `searchPolicy`  
 [in] Değerini [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) bir simge Okuyucu için arama yaparken kullanılacak ilkeyi belirtir numaralandırması.  
  
 `callback`  
 [in] Geri çağırma işlevi için bir işaretçi.  
  
 `pRetVal`  
 [out] Ayarlanmış bir işaretçi döndürülen için [Isymunmanagedreader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** CorSym.idl  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ISymUnmanagedBinder3 Arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
