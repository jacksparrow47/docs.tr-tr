---
title: COM Birlikte Çalışma'ya Giriş (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: ecd514231c36cf3b65b1f0dd05f26d05f3c9c88d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561483"
---
# <a name="introduction-to-com-interop-visual-basic"></a>COM Birlikte Çalışma'ya Giriş (Visual Basic)
Bileşen Nesne Modeli (COM) diğer bileşenleri ve uygulamaları barındırmak için işlevselliği kullanıma sunma nesneyi sağlar. COM nesneleri Windows yıllardır programlama için temel kullanımda olsa, Ortak Dil Çalışma Zamanı Modülü (CLR) tasarlanmış uygulamalar birçok avantaj sunar.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] uygulamalar bu COM ile geliştirilen sonunda değiştirir O zamana kadar kullanabilir veya Visual Studio kullanarak COM nesneleri oluşturmak gerekebilir. COM birlikte çalışabilirlik veya *COM birlikte çalışma*, var olan COM nesneleri için geçişi sırasında kullanmanıza olanak tanır [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] kendi hızınızda.  
  
 Kullanarak [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] COM bileşenleri oluşturmak için Kayıtsız COM birlikte çalışma kullanabilirsiniz. Bu, birden fazla sürümünün bir bilgisayarda yüklü ve son kullanıcılar, XCOPY veya FTP uygulamanızı bilgisayarlarında uygun bir dizine kopyalamak için burada çalıştırılabilir kullanma olanak tanır, hangi DLL sürümü etkin denetlemenize olanak tanır. Daha fazla bilgi için [Registration-Free COM birlikte çalışma](https://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Yönetilen kod ve veriler  
 Geliştirilmiş kod için [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] olarak adlandırılır *yönetilen kod*ve CLR tarafından kullanılan meta veriler içerir. Tarafından kullanılan veri [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] uygulamaları çağrılır *yönetilen verilerini* ayırma ve belleği geri kazanmak ve tür denetimi gibi verilerle ilgili görevler çalışma zamanı yönettiği için. Varsayılan olarak, Visual Basic .NET yönetilen kod ve veri kullanır ancak yönetilmeyen kod ve COM nesneleri (Bu sayfada daha sonra açıklanmıştır) birlikte çalışma derlemelerini kullanarak verileri erişebilirsiniz.  
  
## <a name="assemblies"></a>Derlemeleri  
 Bir derlemenin birincil yapı bloğudur bir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] uygulama. Yerleşik, oluşturulan ve dağıtılan bir veya daha fazla dosya içeren bir tek uygulama birim olarak işlevleri koleksiyonudur. Her derleme, derleme bildirimi içerir.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Tür kitaplıkları ve derleme bildirimleri  
 Tür kitaplıkları, COM nesneleri, üye adları ve veri türleri gibi özellikleri açıklar. Derleme bildirimleri için de aynı işlevi gerçekleştirmek [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] uygulamalar. Bunlar aşağıdakiler hakkında bilgi içerir:  
  
-   Derleme kimliği, sürüm, kültür ve dijital imza.  
  
-   Derleme uygulamasını oluşturan dosyaları.  
  
-   Türleri ve derlemeyi oluşturan kaynakları. Bu, ondan dışarı içerir.  
  
-   Diğer derlemelerdeki derleme zamanı bağımlılıklarını.  
  
-   Derlemenin düzgün çalışması gereken izinler.  
  
 Derlemeler ve derleme bildirimleri hakkında daha fazla bilgi için bkz. [derlemeler ve genel derleme önbelleği](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>İçeri ve dışarı aktarma tür kitaplıkları  
 Visual Studio bir tür kitaplığından bilgileri içeri aktarmanıza olanak sağlayan, Tlbimp gibi bir yardımcı içeren bir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] uygulama. Tlbexp yardımcı programını kullanarak derlemelerden tür kitaplıkları oluşturabilirsiniz.  
  
 Tlbimp ve Tlbexp hakkında daha fazla bilgi için bkz: [Tlbimp.exe (tür kitaplığı içeri Aktarıcı)](../../../framework/tools/tlbimp-exe-type-library-importer.md) ve [Tlbexp.exe (tür kitaplığı dışarı Aktarıcı)](https://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Birlikte çalışma derlemeleri  
 Birlikte çalışma derlemeleri [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] yönetilen ve yönetilmeyen arasında köprü derlemeleri kod, eşleme COM Nesne üyeleri eşdeğerine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] yönetilen üyeler. Birlikte çalışma derlemelerini Visual Basic .NET tarafından oluşturulan çoğu, birlikte çalışabilirlik hazırlama gibi COM nesneleri ile çalışma ayrıntılarını işler.  
  
## <a name="interoperability-marshaling"></a>Birlikte çalışabilirlik hazırlama  
 Tüm [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] uygulamaları, nesnelerin kullandığı programlama diline bakılmaksızın birlikte çalışabilirliği sağlamak genel türleri kümesini paylaşır. Parametreler ve dönüş değerleri COM nesnelerinin bazen yönetilen kod içinde kullanılan farklı veri türleri kullanın. *Birlikte çalışabilirlik hazırlama* ve COM nesneleri dışarı taşırken paketleme parametreler ve dönüş değerleri eşdeğeri veri türlerini işlemidir. Daha fazla bilgi için [birlikte çalışma hazırlama](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM Birlikte Çalışma](../../../visual-basic/programming-guide/com-interop/index.md)  
 [İzlenecek yol: COM Nesnelerinde Kalıtım Uygulama](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Yönetilmeyen Kod ile Birlikte Çalışma](../../../framework/interop/index.md)  
 [Birlikte Çalışabilirlik İle İlgili Sorun Giderme](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Derlemeler ve Genel Derleme Önbelleği](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Tlbimp.exe (Tür Kitaplığı İçeri Aktarıcı)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (Tür Kitaplığı Dışarı Aktarıcı)](https://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Birlikte Çalışma için Hazırlama](../../../framework/interop/interop-marshaling.md)  
 [Kayıtsız COM Birlikte Çalışma](https://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
