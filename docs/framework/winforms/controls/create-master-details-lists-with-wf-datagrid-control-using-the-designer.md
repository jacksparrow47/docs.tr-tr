---
title: 'Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGrid Denetimi ile Ana-Ayrıntılar Listeleri Oluşturma'
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 44cb9cc77e109acd7dd4b2e02f4c93a4f9a35407
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501340"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGrid Denetimi ile Ana-Ayrıntılar Listeleri Oluşturma
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> Denetimi değiştirir ve işlevsellik ekler <xref:System.Windows.Forms.DataGrid> denetler; ancak, <xref:System.Windows.Forms.DataGrid> denetim korunur geriye dönük uyumluluk ve gelecekte kullanım için seçerseniz. Daha fazla bilgi için [farklar arasında Windows Forms DataGridView ve DataGrid denetimleri](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Varsa, <xref:System.Data.DataSet> içeren bir dizi ilgili tabloları, iki kullanabilirsiniz <xref:System.Windows.Forms.DataGrid> bir ana öğe-ayrıntı biçiminde verileri görüntülemek için denetimler. Bir <xref:System.Windows.Forms.DataGrid> ana kılavuz olarak atanan ve ikinci ayrıntıları kılavuz olarak atanır. Ana listesinde bir girişi seçtiğinizde, tüm ilgili alt girişlerinin Ayrıntılar listesinde gösterilir. Örneğin, varsa, <xref:System.Data.DataSet> Müşteriler tablosu ile ilgili bir sipariş tablonuz içeren ana kılavuz olmasını Customers ve Orders tablosunu ayrıntıları kılavuz olarak belirtmeniz gerekir. Ana grid'den gelen bir müşteri seçildiğinde, Northwind'deki Siparişler tablosunda, müşteriyle ilgili Siparişler tüm ayrıntılar kılavuzunda görüntülenmekteydi.  
  
 Aşağıdaki yordamı gerektiren bir **Windows uygulama** proje (**dosya** > **yeni** > **proje**  >  **Visual C#** veya **Visual Basic** > **Klasik Masaüstü** > **Windows Forms Uygulama**).  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Tasarımcıda bir ana-Ayrıntılar listesi oluşturmak için  
  
1.  İki ekleme <xref:System.Windows.Forms.DataGrid> formu için denetimler. Daha fazla bilgi için [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). İçinde [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> denetimi içinde değil **araç kutusu** varsayılan olarak. Daha fazla bilgi için [nasıl yapılır: araç kutusu öğeleri Ekle](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Aşağıdaki adımlar için geçerli olmayan [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], kullanan **veri kaynakları** penceresi tasarım zamanı veri bağlama için. Daha fazla bilgi için [Visual Studio'da verilere denetimler bağlama](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) ve [nasıl yapılır: Windows Forms uygulamasında görüntü ilgili verileri](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  İki veya daha fazla tablodan sürükleyin **Sunucu Gezgini** form.  
  
3.  Gelen **veri** menüsünde **Generate DataSet**.  
  
4.  XML Tasarımcısını kullanarak tablolar arasında ilişki ayarlayın. Ayrıntılar için bkz "nasıl yapılır: oluşturma-çok ilişkilerde XML şemaları ve veri kümeleri" MSDN'de.  
  
5.  İlişkileri seçerek Kaydet **Tümünü Kaydet** gelen **dosya** menüsü.  
  
6.  Yapılandırma <xref:System.Windows.Forms.DataGrid> ana kılavuz, aşağıdaki gibi belirtmek istediğiniz denetimi:  
  
    1.  Seçin <xref:System.Data.DataSet> aşağı açılan listeden <xref:System.Windows.Forms.DataGrid.DataSource%2A> özelliği.  
  
    2.  Ana Tablo (örneğin, "Müşteri"), aşağı açılan listeden seçin <xref:System.Windows.Forms.DataGrid.DataMember%2A> özelliği.  
  
7.  Yapılandırma <xref:System.Windows.Forms.DataGrid> ayrıntıları kılavuz, aşağıdaki gibi belirtmek istediğiniz denetimi:  
  
    1.  Seçin <xref:System.Data.DataSet> aşağı açılan listeden <xref:System.Windows.Forms.DataGrid.DataSource%2A> özelliği.  
  
    2.  Aşağı açılan listeden ana ve ayrıntı tablolar arasındaki ilişkiyi (örneğin, "Customers.CustOrd") seçin <xref:System.Windows.Forms.DataGrid.DataMember%2A> özelliği. İlişkiyi görmek için artı tıklayarak düğümü genişletin (**+**) oturum yanındaki aşağı açılan listesinde ana tablo.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DataGrid Denetimi](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [DataGrid Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Nasıl yapılır: Windows Forms DataGrid Denetimini Veri Kaynağına Bağlama](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Visual Studio'da verilere denetimler bağlama](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
