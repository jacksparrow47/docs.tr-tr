---
title: 'Nasıl yapılır: Görüntü ile bir Alanı Boyama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 5899531291c22ada76213905d0f2ca6944fcbba7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408026"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Nasıl yapılır: Görüntü ile bir Alanı Boyama
Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.ImageBrush> görüntü ile bir alanı boyama için sınıf. Bir <xref:System.Windows.Media.ImageBrush> tarafından belirtilen tek bir görüntü görüntüler, <xref:System.Windows.Media.ImageBrush.ImageSource%2A> özelliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek paints <xref:System.Windows.Controls.Control.Background%2A> kullanarak bir düğmeye bir <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Varsayılan olarak, bir <xref:System.Windows.Media.ImageBrush> görüntüsünü tamamen ın boyama yaptığınız alanı dolduracak şekilde uzatılır. Önceki örnekte, görüntü, büyük olasılıkla resmi bozmasını düğmeye dolduracak şekilde genişletilir. Ayarlayarak bu davranışı denetleyebilirsiniz <xref:System.Windows.Media.TileBrush.Stretch%2A> özelliği <xref:System.Windows.Media.TileBrush> için <xref:System.Windows.Media.Stretch.Uniform> veya <xref:System.Windows.Media.Stretch.UniformToFill>, görüntünün en boy oranını korumak fırça neden olur.  
  
 Ayarlarsanız <xref:System.Windows.Media.TileBrush.Viewport%2A> ve <xref:System.Windows.Media.TileBrush.TileMode%2A> özelliklerini bir <xref:System.Windows.Media.ImageBrush>, yinelenen bir desen oluşturabilirsiniz. Aşağıdaki örnek, bir görüntüden oluşturulan bir desen kullanarak bir düğme boyar.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Hakkında daha fazla bilgi için <xref:System.Windows.Media.ImageBrush> sınıfı [görüntüler, çizimler ve görsellerle boyama](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır <xref:System.Windows.Media.ImageBrush> sınıfı. Tam bir örnek için bkz. [ImageBrush örnek](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görüntüler, Çizimler ve Görsellerle Boyama](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
