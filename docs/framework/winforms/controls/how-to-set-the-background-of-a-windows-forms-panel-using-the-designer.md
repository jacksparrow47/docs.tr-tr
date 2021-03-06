---
title: 'Nasıl yapılır: Tasarımcı Kullanarak Windows Formları Panelinin Arka Planını Ayarlama'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 86ab8bc979765fe79ccc76db9a0566459fde6e46
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499919"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak Windows Formları Panelinin Arka Planını Ayarlama
Bir Windows Forms <xref:System.Windows.Forms.Panel> denetim arka plan rengi hem de arka plan görüntüsü görüntüleyebilirsiniz. <xref:System.Windows.Forms.Control.BackColor%2A> Özelliği etiketler gibi panelinde bulunan ve radyo düğmeleri, denetimleri arka plan rengini ayarlar. Varsa <xref:System.Windows.Forms.Control.BackgroundImage%2A> özelliği ayarlı değil, <xref:System.Windows.Forms.Control.BackColor%2A> seçimi tüm panel doldurur. Varsa <xref:System.Windows.Forms.Control.BackgroundImage%2A> özelliği ayarlanmışsa, görüntünün arkasındaki panelde bulunan denetimleri görüntülenir.  
  
 Aşağıdaki yordamı gerektiren bir **Windows uygulama** proje içeren bir form bir <xref:System.Windows.Forms.Panel> denetimi. Böyle bir projeyi ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturmak](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Windows Form Tasarımcısı'nda arka planını ayarlama  
  
1.  Seçin <xref:System.Windows.Forms.Panel> denetimi.  
  
2.  İçinde **özellikleri** penceresinde, oku, İleri düğmesine tıklayın <xref:System.Windows.Forms.Control.BackColor%2A> bir penceresi üç sekme ile görüntülenecek özelliği.  
  
3.  Seçin **özel** renkler paleti görüntülemek için sekmesinde.  
  
4.  Seçin **Web** veya **sistem** renkler için önceden tanımlanmış adlarının bir listesini görüntülemek için sekmesinde ve bir renk seçin.  
  
5.  İçinde **özellikleri** penceresinde, oku, İleri düğmesine tıklayın <xref:System.Windows.Forms.Control.BackgroundImage%2A> özelliği.  
  
6.  İçinde **açık** iletişim kutusunda, görüntülemek istediğiniz dosyayı seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel Denetimi](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Nasıl yapılır: Tasarımcı Kullanarak Windows Forms Panel Denetimi ile Denetimleri Gruplandırma](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
