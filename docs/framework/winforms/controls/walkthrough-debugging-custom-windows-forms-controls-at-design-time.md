---
title: 'İzlenecek yol: Tasarım Zamanında Özel Windows Formları Denetimleri Hatalarını Ayıklama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: 824c1e47cf50dc13a3a986e48a49158b15dbb935
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43557307"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>İzlenecek yol: Tasarım Zamanında Özel Windows Formları Denetimleri Hatalarını Ayıklama
Özel denetim oluşturduğunuzda, genellikle, tasarım zamanı davranışını hata ayıklamak gerekli bulacaksınız. Özel denetim için özel bir tasarımcı yazıyorsanız bu özellikle doğrudur. Ayrıntılar için bkz [izlenecek yol: bir Windows Forms denetimi olduğunu alır avantajı, Visual Studio tasarım-zamanı özellikleri oluşturma](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 Diğer .NET Framework sınıfları debug gibi özel kontrollerinizi Visual Studio kullanarak hata ayıklama yapabilirsiniz. Visual Studio'ya özel denetiminizin kodu çalıştıran ayrı bir örneğini hata ayıklayacaktır fark  
  
 Bu kılavuzda gösterilen görevler aşağıdakileri içerir:  
  
-   Özel denetiminizi barındırmak için bir Windows Forms projesi oluşturma  
  
-   Bir denetim kitaplığı projesi oluşturma  
  
-   Bir özellik için özel denetim ekleme  
  
-   Konak formuna özel denetim ekleme  
  
-   Tasarım zamanı hata ayıklama için projeyi ayarlama  
  
-   Özel denetiminizi tasarım zamanında hata ayıklama  
  
 İşlemi tamamladığınızda, özel denetiminin tasarım zamanı davranışını hata ayıklama için gerekli görevleri bir anlayışa sahip olacaksınız.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım, uygulama projesi oluşturmaktır. Bu proje, özel denetimin barındıran uygulaması oluşturmak için kullanır.  
  
#### <a name="to-create-the-project"></a>Proje oluşturmak için  
  
-   "DebuggingExample" adlı bir Windows uygulaması projesi oluşturun (**dosya** > **yeni** > **proje**  >  **Visual C#** veya **Visual Basic** > **Klasik Masaüstü** > **Windows Forms uygulamalarındaki**).  
  
## <a name="creating-a-control-library-project"></a>Bir denetim kitaplığı projesi oluşturma  
 Sonraki adım, denetim kitaplığı projesi oluşturun ve özel denetimi ayarlamaktır.  
  
#### <a name="to-create-the-control-library-project"></a>Denetim Kitaplığı projesini oluşturmak için  
  
1.  Ekleme bir **Windows Denetim Kitaplığı** çözüme bir proje.  
  
2.  Yeni bir **UserControl** DebugControlLibrary projeye öğe. Ayrıntılar için bkz [NIB: nasıl yapılır: Yeni proje öğeleri ekleme](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Yeni kaynak dosyanın temel "DebugControl" adını verin.  
  
3.  Kullanarak **Çözüm Gezgini**, projenin varsayılan denetimi kod dosyası taban adı ile silerek Sil "`UserControl1`". Ayrıntılar için bkz [NIB: nasıl yapılır: kaldırma, silme ve öğeleri hariç](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Çözümü oluşturun.  
  
## <a name="checkpoint"></a>Denetim noktası  
 Bu noktada, özel denetiminizi görmeye olacaktır **araç kutusu**.  
  
#### <a name="to-check-your-progress"></a>İlerleme durumunuzu kontrol etmek için  
  
-   Adlı yeni sekmeyi bulun **DebugControlLibrary bileşenleri** ve seçmek için tıklayın. Açıldığında, denetiminiz olarak listelenen göreceğiniz **DebugControl** varsayılan simgesinin yanında.  
  
## <a name="adding-a-property-to-your-custom-control"></a>Bir özellik için özel denetim ekleme  
 Tasarım zamanında özel denetiminizin kodu çalıştığını göstermek için özellik ekleme ve özelliği uygulayan kod içinde bir kesme noktası ayarlayın.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>Bir özellik için özel denetim eklemek için  
  
1.  Açık **DebugControl** içinde **Kod Düzenleyicisi**. Aşağıdaki kodu sınıf tanımına ekleyin:  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  Çözümü oluşturun.  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>Konak formuna özel denetim ekleme  
 Özel denetiminizi tasarım zamanı davranışını hata ayıklamak için bir konak formda özel denetim sınıfının bir örneğini yerleştirmeniz gerekir.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>Konak formuna özel denetim eklemek için  
  
1.  Form1 içinde "DebuggingExample" projesinde açın **Windows Form Tasarımcısı**.  
  
2.  İçinde **araç kutusu**açın **DebugControlLibrary bileşenleri** sürükleyin ve sekme bir **DebugControl** forma örneği.  
  
3.  Bulma `DemoString` özel özelliğinde **özellikleri** penceresi. Herhangi bir özellik gibi değerini değiştirebileceğinize dikkat edin. Gerektiğini de unutmayın `DemoString` özelliği seçildiğinde, özellik açıklama dizesi sonunda görünür **özellikleri** penceresi.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Tasarım zamanı hata ayıklama için projeyi ayarlama  
 Özel denetiminizin tasarım zamanı davranışını hata ayıklamak için Visual Studio'ya özel denetiminizin kodu çalıştıran ayrı bir örneğini hata ayıklayacaktır.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Tasarım zamanı hata ayıklama için projeyi ayarlamak için  
  
1.  Sağ **DebugControlLibrary** projesi **Çözüm Gezgini** seçip **özellikleri**.  
  
2.  İçinde **DebugControlLibrary** özellik sayfasını, select **hata ayıklama** sekmesi.  
  
     İçinde **başlatma eylemi** bölümünden **harici program Başlat**. Artık Visual Studio, ayrı bir örneğini hata ayıklama şekilde üç nokta simgesine tıklayın (![VisualStudioEllipsesButton ekran](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) Visual Studio IDE için Gözat düğmesini. Yürütülebilir dosyanın adı **devenv.exe**, ve varsayılan bir konuma yüklediyseniz, %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe yoludur.  
  
3.  İletişim kutusunu kapatmak için **Tamam** 'ı tıklatın.  
  
4.  Sağ **DebugControlLibrary** seçin ve proje **başlangıç projesi olarak ayarla** bu hata ayıklama yapılandırmasını etkinleştirmek için.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>Özel denetiminizi tasarım zamanında hata ayıklama  
 Özel denetiminizi Tasarım modunda çalışırken hata ayıklamak hazırsınız. Hata ayıklama oturumu başlattığınızda, Visual Studio'nun yeni bir örneği oluşturulur ve "DebuggingExample" çözümü yüklemek için kullanır. Form1 içinde açtığınızda **Form Tasarımcısı**, özel denetiminizi örneği oluşturulur ve çalıştırmaya başlayın.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>Özel denetiminizi tasarım zamanında hata ayıklama  
  
1.  Açık **DebugControl** kaynak dosyada **Kod Düzenleyicisi** ve bir kesme noktası yerleştirmek `Set` erişimcisine `DemoString` özelliği.  
  
2.  Hata ayıklama oturumu başlatmak için F5 tuşuna basın. Visual Studio'nun yeni bir örneğini oluşturulduğunu unutmayın. İki yolla örnekleri ayırt edebilirsiniz:  
  
    -   Hata ayıklama örneğindeki ifadesi **çalıştıran** başlık çubuğunda  
  
    -   Hata ayıklama örneğindeki sahip **Başlat** düğmesini kendi **hata ayıklama** araç çubuğunda devre dışı  
  
     Kesme noktasına içinde hata ayıklama örneğindeki ayarlanır.  
  
3.  Visual Studio'nun yeni örneğini "DebuggingExample" çözümü açın. Çözüm seçerek kolayca bulabilirsiniz **son projeler** gelen **dosya** menüsü. En son dosya kullanılan "DebuggingExample.sln" Çözüm dosyası listelenir.  
  
4.  Açık olarak Form1 **Form Tasarımcısı** seçip **DebugControl** denetimi.  
  
5.  Değiştirin `DemoString` özelliği. Değişiklik yaparsanız, hata ayıklama örneğindeki Visual Studio'nun odağı alır ve yürütmeyi, kesme noktasında durur unutmayın. Özellik erişimcisi aracılığıyla tek adımlı yapabilecekleriniz gibi herhangi bir kod gerekir.  
  
6.  Hata ayıklama oturumunuzu ile işiniz bittiğinde, barındırılan bir Visual Studio örneğini kapatma veya tıklayarak çıkabilirsiniz **hata ayıklamayı Durdur** hata ayıklama örneğindeki düğmesi.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Tasarım zamanında özel kontrollerinizi ayıklayabilirsiniz, Visual Studio IDE denetiminizin etkileşim genişletme için çok sayıda olasılık vardır.  
  
-   Kullanabileceğiniz <xref:System.ComponentModel.Component.DesignMode%2A> özelliği <xref:System.ComponentModel.Component> yalnızca tasarım zamanında yürütülür kod yazmak için sınıf. Ayrıntılar için bkz <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Birkaç öznitelik özel denetiminizin etkileşim Tasarımcısı ile düzenlemek için denetimin özelliklerini uygulayabilirsiniz. İçinde bu özniteliklerin bulabilirsiniz <xref:System.ComponentModel?displayProperty=nameWithType> ad alanı.  
  
-   Özel denetim için özel bir tasarımcı yazabilirsiniz. Bu, Visual Studio tarafından kullanıma sunulan Genişletilebilir Tasarımcı altyapısını kullanarak tasarım deneyimi üzerinde tam denetim sağlar. Ayrıntılar için bkz [izlenecek yol: bir Windows Forms denetimi olduğunu alır avantajı, Visual Studio tasarım-zamanı özellikleri oluşturma](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Visual Studio Tasarım-Zamanı Özellikleri'nden Faydalanan Windows Forms Denetimi Oluşturma](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [Nasıl yapılır: tasarım zamanı hizmetlere erişme](https://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [Nasıl yapılır: Windows Forms tasarım zamanı desteğine erişim](https://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
