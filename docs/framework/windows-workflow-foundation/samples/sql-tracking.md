---
title: SQL izleme
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 5f8d7bbd57965b4d7399373416caea87d4d84187
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402679"
---
# <a name="sql-tracking"></a>SQL izleme
Bu örnek nasıl yazılacağını özel SQL izleme katılımcı gösterir, bu bir SQL veritabanı'na izleme kayıtları yazar. Windows Workflow Foundation (WF) iş akışı yürütme iş akışı örneğinin görünürlük elde etmek için izleme sağlar. İzleme çalışma zamanı iş akışı iş akışı yürütülürken kayıtları izleme yayar. İş akışı izleme hakkında daha fazla bilgi için bkz: [takip ve izleme iş akışı](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).  
  
#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1.  Bilgisayarınızda SQL Server 2008, SQL Server 2008 Express veya üzerinin yüklü doğrulayın. Örnek ile paketlenmiş betikleri yerel bilgisayarınızda bir SQL Express örneği kullanımını varsayılır. Lütfen veritabanı ile ilgili betikleri örneği çalıştırmadan önce değiştirin. farklı bir örneğine sahipseniz.  
  
2.  SQL Server veritabanı izleme betikleri dizininde (\WF\Basic\Tracking\SqlTracking\CS\Scripts) Trackingsetup.cmd çalıştırarak oluşturun. Bu TrackingSample adlı bir veritabanı oluşturur.  
  
    > [!NOTE]
    >  Betik, SQL Express varsayılan örnekte veritabanı oluşturur. Farklı bir veritabanı örneği üzerinde yüklemek istiyorsanız, Trackingsetup.cmd betiği düzenleyin.  
  
3.  İçinde SqlTrackingSample.sln açın [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.  
  
5.  Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
     Tarayıcı penceresi açılır ve dizin için uygulama listesi gösterilir.  
  
6.  Tarayıcıda StockPriceService.xamlx tıklayın.  
  
7.  Tarayıcı, yerel hizmet WSDL adresini içeren StockPriceService sayfası görüntüler. Bu adresini kopyalayın.  
  
     Yerel Hizmet WSDL adresi örneğidir http://localhost:65193/StockPriceService.xamlx?wsdl.  
  
8.  Kullanarak [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], WCF test istemcisi (WcfTestClient.exe) çalıştırın. Bunu yapmak için Microsoft Visual Studio 10.0\Common7\IDE dizininde bulunur.  
  
9. WCF test İstemcisi'nde tıklayın **dosya** menü ve select **Hizmet Ekle**. Yerel hizmet adresi metin kutusuna yapıştırın. Tıklayın **Tamam** iletişim kutusunu kapatmak için.  
  
10. WCF test İstemcisi'nde çift tıklayarak **GetStockPrice**. Bu açılır `GetStockPrice` bir parametre, değer alan işlemi `Contoso` tıklatıp **Invoke**.  
  
11. Bir SQL veritabanına yayılan izleme kayıtları yazılır. İzleme kayıtları görüntülemek için SQL Management Studio'da TrackingSample veritabanını açın ve tablolara gidin. SQL Server Management Studio hakkında daha fazla bilgi için bkz: [Karşınızda SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645). SQL Server 2008 Management Studio Express'i indirilebilir [burada](https://go.microsoft.com/fwlink/?LinkId=180520). Tabloları seçme sorgusu çalıştıran izleme kayıtları ilgili tablolarında depolanan verileri görüntüler.  
  
#### <a name="to-uninstall-the-sample"></a>Örnek kaldırmak için  
  
1.  Örnek dizini (\WF\Basic\Tracking\SqlTracking) theTrackingcleanup.cmd betiği çalıştırın.  
  
    > [!NOTE]
    >  Trackingcleanup.cmd, yerel bilgisayarınıza SQL Express veritabanında silmeyi dener. Başka bir SQL server örneği kullanıyorsanız, Trackingcleanup.cmd düzenleyin.  
  
> [!IMPORTANT]
>  Örnekler, bilgisayarınızda yüklü. Devam etmeden önce şu (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek, şu dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AppFabric izleme örnekleri](https://go.microsoft.com/fwlink/?LinkId=193959)
