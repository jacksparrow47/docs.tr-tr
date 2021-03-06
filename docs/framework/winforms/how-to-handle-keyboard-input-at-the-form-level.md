---
title: 'Nasıl yapılır: Klavye Girdisini Form Düzeyinde İşleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: a75c4f116b32499f9ba33dd863f2a5b6952a3e24
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535865"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a>Nasıl yapılır: Klavye Girdisini Form Düzeyinde İşleme
Windows Forms Denetim iletileri ulaşmadan önce klavye iletileri form düzeyinde işleme yeteneği sağlar. Bu konu, bu görevi nasıl gerçekleştireceğinizi gösterir.  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a>Bir klavye iletisi form düzeyinde işlemek için  
  
-   İşlemek <xref:System.Windows.Forms.Control.KeyPress> veya <xref:System.Windows.Forms.Control.KeyDown> olay başlangıç formu ve kümesi <xref:System.Windows.Forms.Form.KeyPreview%2A> özellik formun `true` böylece form üzerinde herhangi bir denetim ulaşmadan önce klavye iletiler form tarafından alınır. Aşağıdaki kod örneği tanıtıcıları <xref:System.Windows.Forms.Control.KeyPress> tüm sayı tuşları algılama ve '1', '4' ve '7' kullanan olay.  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, yukarıdaki örnek için tüm uygulamasıdır. Uygulama içeren bir <xref:System.Windows.Forms.TextBox> odağı Taşı olanak tanıyan çeşitli diğer denetimler birlikte <xref:System.Windows.Forms.TextBox>. <xref:System.Windows.Forms.Control.KeyPress> Ana olay <xref:System.Windows.Forms.Form> '1', '4' ve '7', tüketir ve <xref:System.Windows.Forms.Control.KeyPress> olayı <xref:System.Windows.Forms.TextBox> '2', '5' ve '8' kalan anahtarlar görüntülenirken kullanır. Karşılaştırma <xref:System.Windows.Forms.MessageBox> sayı anahtar biraz bastığınızda çıkış <xref:System.Windows.Forms.TextBox> ile odaklı <xref:System.Windows.Forms.MessageBox> diğer denetimlerden birini odak modundayken bir sayı tuşuna bastığınızda çıktı.  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem, System.Drawing ve System.Windows.Forms öğelerini derlemelerine başvurular.  
  
 Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.  Ayrıca bkz: [nasıl yapılır: derleme ve çalıştırma bir tam Windows Formları kod örneği kullanarak Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir Windows Forms Uygulamasında Klavye Girdisi](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
