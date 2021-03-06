---
title: Kod Açıklamaları (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: fafc80cc4847e9ec05f19fc7f3d31d2d5b11197a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661158"
---
# <a name="comments-in-code-visual-basic"></a>Kod Açıklamaları (Visual Basic)
Kod örneklerini okurken açıklama sembolüyle sık karşılaştığınız (`'`). Bu simge, metni yok saymak için Visual Basic derleyiciye veya *yorum*. Açıklamalar, okuyan kişinin yararına olması için koda eklenmiş kısa ve açıklayıcı notlardır.  
  
 Tüm yordamlara, ilgili yordamın işlevsel özelliklerini (neler yaptığını) açıklayan kısa bir açıklama ile başlanması iyi bir programlama uygulamasıdır. Bu hem sizin yararınıza, hem de kodu inceleyen herhangi bir kişinin yararına olur. Gerçekleştirme ayrıntılarını (yordamın bunu nasıl yaptığı), işlevsel özellikleri anlatan açıklamalardan ayırmalısınız. Açıklamaya gerçekleştirme ayrıntılarını eklediğinizde, işlevi güncelleştirirken bunları da güncelleştirmeyi unutmayın.  
  
 Açıklamalar aynı satırdaki bir deyimi izleyebilir veya tüm bir satırı kaplayabilir. Her ikisi de aşağıdaki kodda gösterilmiştir.  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 Açıklamanız için birden fazla satır gerekiyorsa, aşağıdaki örnekte gösterildiği gibi her satırda açıklama sembolünü kullanın.  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a>Açıklamalara İlişkin Kurallar  
 Aşağıdaki tabloda, kodun bir bölümünden önce hangi tür açıklamaların gelebileceğine dair genel kurallar verilmektedir. Bunlar önerilerdir; Visual Basic açıklama eklemek için kuralları zorunlu kılmaz. Hem sizin, hem de kodu okuyan herhangi bir kişinin işine en çok yarayacak şeyleri yazın.  
  
|||  
|---|---|  
|Açıklama türü|Açıklama tanımı|  
|Amaç|Yordamın ne yaptığını açıklar (bunu nasıl yaptığını değil)|  
|Varsayımlar|Her bir dış bağımsız değişkeni, denetimi, dosya açmayı veya yordamın erişim sağladığı diğer öğeyi listeler|  
|Etkiler|Her bir etkilenen dış bağımsız değişkeni, denetimi veya dosyayı ve sahip olduğu etkiyi (bu etki bariz değilse) listeler|  
|Girişler|Bağımsız değişkenin amacını belirtir|  
|Döndürür|Yordamın döndürdüğü değerleri açıklar|  
  
 Aşağıdaki hususları unutmayın:  
  
-   Her önemli değişken bildiriminin önünde, bildirilen değişkenin kullanımını anlatan bir açıklama bulunmalıdır.  
  
-   Değişkenler, denetimler ve yordamlar, yalnızca karmaşık gerçekleştirme ayrıntıları için açıklamaya gerek duyulacak şekilde yeterince açık adlandırılmalıdır.  
  
-   Açıklamalar, aynı satırdaki bir satır devamlılığı dizisinden sonra gelemez.  
  
 Ekleyebilir veya bir veya daha fazla kod satırlarını ve seçerek bir kod bloğu için açıklama sembolleri kaldırmak **yorum** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton ")) ve **açıklamayı Kaldır** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) düğmelerini **Düzenle**  araç çubuğu.  
  
> [!NOTE]
>  Metinle koyarak kodunuza açıklama ekleyebilirsiniz `REM` anahtar sözcüğü. Ancak, `'` sembol ve **yorum**/**açıklamayı Kaldır** düğmeleri daha kolay ve daha az alan ve bellek gerektirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML açıklamalarıyla kodunuzu belgeleme](https://msdn.microsoft.com/magazine/dd722812.aspx)  
 [Nasıl yapılır: XML Belgesi Oluşturma](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML Açıklama Etiketleri](../../../visual-basic/language-reference/xmldoc/index.md)  
 [Program Yapısı ve Kod Kuralları](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [REM Deyimi](../../../visual-basic/language-reference/statements/rem-statement.md)
