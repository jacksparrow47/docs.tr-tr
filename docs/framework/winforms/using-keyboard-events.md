---
title: Klavye Olaylarını Kullanma
ms.date: 03/30/2017
helpviewer_keywords:
- KeyPress event [Windows Forms]
- keyboards [Windows Forms], keyboard events
- KeyUp event
- KeyDown event
- keyboard events
- events [Windows Forms], keyboard
ms.assetid: d3f3e14b-a459-4ee6-9875-8957e34f8ee9
ms.openlocfilehash: 2c6059e5d0957de09dd2c4832573c784935eb510
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43658853"
---
# <a name="using-keyboard-events"></a>Klavye Olaylarını Kullanma
Çoğu Windows Forms program klavye girdisi klavye olaylarını işleme göre işleyin. Bu konu, klavye olayları zaman her bir olay ve sağlanan verileri her olay için kullanılacağı hakkında ayrıntılar dahil olmak üzere, genel bir bakış sağlar.  Ayrıca bkz: [olay işleyicilerine genel bakış (Windows Forms)](https://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [olaylara genel bakış (Windows Forms)](https://msdn.microsoft.com/library/1h12f09z\(v=vs.110\)).  
  
## <a name="keyboard-events"></a>Klavye olayları  
 Windows Forms, bir kullanıcı bir klavye tuşuna bastığında oluşan iki olay ve bir kullanıcı bir klavye anahtar bıraktığında bir olay sağlar:  
  
-   <xref:System.Windows.Forms.Control.KeyDown> Gerçekleştiğinde bir kez  
  
-   <xref:System.Windows.Forms.Control.KeyPress> Olayı, bir kullanıcı aynı tuşunu basılı tutar birden çok kez gerçekleşebilir.  
  
-   <xref:System.Windows.Forms.Control.KeyUp> Olayı, bir kullanıcı bir anahtar zaman serbest sonra oluşur.  
  
 Bir kullanıcı bir tuşuna bastığında, Windows Forms klavye iletisi karakter anahtarı veya fiziksel bir anahtar belirtir yükseltmek için hangi olay tabanlı belirler. Karakter ve fiziksel anahtarlar hakkında daha fazla bilgi için bkz. [nasıl klavye girişi çalışır](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
 Aşağıdaki tabloda, üç klavye olaylarını açıklar.  
  
|Klavye olayı|Açıklama|Sonuçları|  
|--------------------|-----------------|-------------|  
|<xref:System.Windows.Forms.Control.KeyDown>|Bir kullanıcı bir fiziksel tuşuna bastığında bu olay tetiklenir.|İşleyici için <xref:System.Windows.Forms.Control.KeyDown> alır:<br /><br /> <ul><li>A <xref:System.Windows.Forms.KeyEventArgs> sağlayan parametresi <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (bir fiziksel klavye düğmeyi belirtir) özelliği.</li><li><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Özelliği (SHIFT, CTRL ya da ALT).</li><li><xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> (Değiştiricisi ve anahtar kodu birleştirir) özelliği. <xref:System.Windows.Forms.KeyEventArgs> Parametresi de sağlar:<br /><br /> <ul><li><xref:System.Windows.Forms.KeyEventArgs.Handled%2A> Temel denetim anahtar almasını önlemek için ayarlanabilir özelliği.</li><li><xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> Gizlemek için kullanılan özellik <xref:System.Windows.Forms.Control.KeyPress> ve <xref:System.Windows.Forms.Control.KeyUp> bu tuş vuruşu olayları.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyPress>|Anahtar veya anahtarlarının bir karakter, sonuç basıldığında bu olay tetiklenir. Örneğin, bir kullanıcı kaydırma ve küçük harf bir büyük harf "A" karakteri neden "a" tuşuna bastığında.|<xref:System.Windows.Forms.Control.KeyPress> sonra yükseltilmiş <xref:System.Windows.Forms.Control.KeyDown>.<br /><br /> <ul><li>İşleyici için <xref:System.Windows.Forms.Control.KeyPress> alır:</li><li>A <xref:System.Windows.Forms.KeyPressEventArgs> basıldığını anahtarı karakter kodunu içeren bir parametre. Bu karakter kodunu, her bir karakter anahtar ve değiştiricisi anahtar bileşimi için benzersizdir.<br /><br />     Örneğin, "A" anahtarı oluşturur:<br /><br /> <ul><li>İle SHIFT tuşunu basılı, 65 karakter kodu</li><li>Veya kendi kendine basıldığında, 97 CAPS LOCK tuşunun,</li><li>Ve 1 ile CTRL tuşuna basıldığında.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyUp>|Bir kullanıcı bir fiziksel anahtar yayımlandığında bu olay tetiklenir.|İşleyici için <xref:System.Windows.Forms.Control.KeyUp> alır:<br /><br /> <ul><li>A <xref:System.Windows.Forms.KeyEventArgs> parametresi:<br /><br /> <ul><li>Sağlayan <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (bir fiziksel klavye düğmeyi belirtir) özelliği.</li><li><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Özelliği (SHIFT, CTRL ya da ALT).</li><li><xref:System.Globalization.SortKey.KeyData%2A> (Değiştiricisi ve anahtar kodu birleştirir) özelliği.</li></ul></li></ul>|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir Windows Forms Uygulamasında Klavye Girdisi](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Klavye Girdisi Nasıl Çalışır](../../../docs/framework/winforms/how-keyboard-input-works.md)  
 [Bir Windows Forms Uygulamasında Fare Girdisi](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
