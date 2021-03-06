---
title: Geç Hesaplamalar (F#)
description: 'F # geç hesaplamalar uygulamalarınızı ve kitaplıkları performansını geliştirebilirsiniz nasıl öğrenin.'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563938"
---
# <a name="lazy-computations"></a>Geç Hesaplamalar

*Geç hesaplamalar* hemen değerlendirilmez, ancak sonuç gerektiğinde yerine değerlendirilir hesaplamalar şunlardır. Bu, kodunuzu performansının artırılmasına yardımcı olabilir.

## <a name="syntax"></a>Sözdizimi

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Açıklamalar

Önceki sözdiziminde *ifade* yalnızca bir sonuç gerekli olduğunda değerlendirilen kodu ve *tanımlayıcısı* sonucu depolayan bir değerdir. Değer [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), burada gerçek türü için kullanılan `'T` ifade sonucundan belirlenir.

Geç hesaplamalar hesaplamanın sonucu gerekli durumlar için yürütmesi kısıtlayarak performansını artırmak etkinleştirin.

Gerçekleştirilecek hesaplama zorlamak için yöntemi çağırın `Force`. `Force` yalnızca bir kez gerçekleştirilmesi yürütme neden olur. Sonraki çağrılar `Force` aynı sonucu, ancak herhangi bir kod yürütülmez döndürür.

Aşağıdaki kod yavaş hesaplama kullanımını ve kullanımını gösterir `Force`. Bu kod türünü `result` olan `Lazy<int>`ve `Force` yöntemi döndürür bir `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Geç değerlendirme, ama `Lazy` yazın, sıraları için de kullanılır. Daha fazla bilgi için bkz: [sıraları](sequences.md).

## <a name="see-also"></a>Ayrıca Bkz.

[F# Dili Başvurusu](index.md)

[LazyExtensions Modülü](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
