---
title: İşaretçi Karşılaştırması (C# Programlama Kılavuzu)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: fa980c944159c477c333762ffad569332fba9402
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43555516"
---
# <a name="pointer-comparison-c-programming-guide"></a>İşaretçi Karşılaştırması (C# Programlama Kılavuzu)
Herhangi bir türde işaretçileri karşılaştırmak için aşağıdaki işleçleri uygulayabilirsiniz:  
  
 **==   !=   \<   >   \<=   >=**  
  
 İşaretsiz tamsayılar olarak varsa adresleri iki işlenenden Karşılaştırma işleçleri karşılaştırın.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a>Örnek Çıktı  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [İşaretçi İfadeleri](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [C# İşleçleri](../../../csharp/language-reference/operators/index.md)  
- [İşaretçileri İşleme](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [İşaretçi türleri](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [Türler](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed Deyimi](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
