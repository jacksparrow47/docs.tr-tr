---
title: add (C# Başvurusu)
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: b55827b60a89da2569fad9da135c84571a24b094
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390974"
---
# <a name="add-c-reference"></a>add (C# Başvurusu)
`add` Bağlamsal anahtar sözcük için istemci kodu abone olduğunda çağrılan bir özel olay erişimci tanımlamak için kullanılır, [olay](../../../csharp/language-reference/keywords/event.md). Özel bir sağlarsanız `add` erişimci gerekir da sağlamanız bir [Kaldır](../../../csharp/language-reference/keywords/remove.md) erişimcisi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, özel bir olayını gösterir `add` ve [Kaldır](../../../csharp/language-reference/keywords/remove.md) erişimcileri. Tam bir örnek için bkz: [nasıl yapılır: arabirim olaylarını uygulama](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 Genellikle kendi özel olay erişimcilerini sağlamanız gerekmez. Olay bildirdiğinizde, derleyici tarafından otomatik olarak oluşturulan erişimcileri, çoğu senaryo için yeterlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
- [Olaylar](../../../csharp/programming-guide/events/index.md)
