---
title: 'Nasıl yapılır: ListView için Özel Görünüm Modu Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 239fb2e9a364bd0265ff7cf644ee296878280cf3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561701"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Nasıl yapılır: ListView için Özel Görünüm Modu Oluşturma
Bu örnekte, özel bir oluşturma işlemi gösterilmektedir <xref:System.Windows.Controls.ListView.View%2A> modu için bir <xref:System.Windows.Controls.ListView> denetimi.  
  
## <a name="example"></a>Örnek  
 Kullanmalısınız <xref:System.Windows.Controls.ViewBase> sınıfı için özel bir görünüm oluşturduğunuzda <xref:System.Windows.Controls.ListView> denetimi. Aşağıdaki örnekte adlı bir görünüm modu `PlainView`, türetilen <xref:System.Windows.Controls.ViewBase> sınıfı.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Özel Görünüm için bir stil uygulamak için kullanma <xref:System.Windows.Style> sınıfı. Aşağıdaki örnekte tanımlayan bir <xref:System.Windows.Style> için `PlainView` görünüm modu. Önceki örnekte, bu stil değeri olarak ayarlanır <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> için tanımlanan özellik `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Bir özel görünüm modunda verilerin düzeni tanımlamak için tanımladığınız bir <xref:System.Windows.DataTemplate> nesne. Aşağıdaki örnekte tanımlayan bir <xref:System.Windows.DataTemplate> verileri görüntülemek için kullanılabilecek `PlainView` görünüm modu.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Aşağıdaki örnek nasıl tanımlanacağını gösterir bir <xref:System.Windows.ResourceKey> için `PlainView` kullanan görünüm modu <xref:System.Windows.DataTemplate> önceki örnekte tanımlanır.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 A <xref:System.Windows.Controls.ListView> denetimi, özel bir görünüm kullanabilirsiniz, ayarlarsanız <xref:System.Windows.Controls.ListView.View%2A> özelliğini kaynak anahtarı. Aşağıdaki örnek nasıl belirtileceğini gösterir `PlainView` görünüm modu için bir <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Tam bir örnek için bkz. [birden çok örneği ile ListView](https://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView Genel Bakış](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView Genel Bakış](../../../../docs/framework/wpf/controls/gridview-overview.md)
