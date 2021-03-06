---
title: Visual Studio ile .NET core uygulama dağıtımı
description: Visual Studio ile .NET Core uygulama dağıtımı öğrenin
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.openlocfilehash: 2829bb5a2f5857f6124e5c1f78f5247fe8d1f552
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407455"
---
# <a name="deploying-net-core-apps-with-visual-studio"></a>Dağıtımı .NET Core uygulamaları Visual Studio ile

Dağıtabileceğiniz bir .NET Core uygulaması ya da farklı bir *framework bağımlı dağıtım*, uygulama ikili dosyalarını içerir, ancak hedef sistem üzerinde veya olarak .NET Core varlığını bağımlı bir *müstakil Dağıtım*, hem uygulama hem de .NET Core ikili dosyalarını içerir. .NET Core uygulama dağıtımı genel bakış için bkz. [.NET Core uygulaması dağıtımını](index.md).

Aşağıdaki bölümlerde, aşağıdaki türde dağıtımları oluşturmak için Microsoft Visual Studio kullanmayı göstermektedir:

- Framework bağımlı dağıtım
- Framework bağımlı dağıtım üçüncü taraf bağımlılıkları
- Kendi içinde dağıtım
- Üçüncü taraf bağımlılıkları kendi içinde dağıtım

.NET Core uygulamaları geliştirmek için Visual Studio'yu kullanma hakkında daha fazla bilgi için bkz: [Windows üzerinde .NET Core önkoşulları](../windows-prerequisites.md#prerequisites-with-visual-studio-2017).

## <a name="framework-dependent-deployment"></a>Framework bağımlı dağıtım

Herhangi bir üçüncü taraf bağımlılıkları olan bir framework bağımlı dağıtımının oluşturmaya, sınamaya ve uygulama yayımlama yalnızca içerir. C# dilinde yazılmış basit bir örnek işlemini gösterir.  

1. Projeyi oluşturun.

   Seçin **dosya** > **yeni** > **proje**. İçinde **yeni proje** iletişim kutusunda **.NET Core** içinde **yüklü** Proje Türleri bölmesinde ve seçin **konsol uygulaması (.NET Core)** Orta bölmedeki şablonu. "FDD" gibi bir proje adı girin **adı** metin kutusu. Seçin **Tamam** düğmesi.

1. Uygulamanın kaynak kodunu ekleyin.

   Açık *Program.cs* Düzenleyicisi'nde dosya ve otomatik olarak oluşturulan kodu aşağıdaki kodla değiştirin. Kullanıcının metin girmesini ister ve kullanıcı tarafından girilen kelimeler görüntüler. Normal ifade kullanan `\w+` giriş metnindeki sözcükleri ayırmak için.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Uygulamanızı hata ayıklama yapısını oluşturun.

   Seçin **derleme** > **yapı çözümü**. Ayrıca derlemek ve seçerek uygulamanızı hata ayıklama yapısını çalıştırmak **hata ayıklama** > **hata ayıklamayı Başlat**.

1. Uygulamanızı dağıtın.

   Hata ayıklama ve test programı sonra uygulamanızla birlikte dağıtılacak dosyalar oluşturun. Visual Studio'dan yayımlamak için aşağıdakileri yapın:

      1. Çözüm yapılandırmasını değiştirme **hata ayıklama** için **yayın** uygulamanızın derleme bir sürüm (yerine bir hata ayıklama) sürümü için araç çubuğundaki.

      1. Projede (çözümü değil) sağ tıklatın **Çözüm Gezgini**seçip **Yayımla**.

      1. İçinde **Yayımla** sekmesinde **Yayımla**. Visual Studio, uygulamanızın yerel dosya sistemine oluşturan dosyaların yazar.

      1. **Yayımla** sekmesi, artık tek bir profil gösterir **FolderProfile**. Profilin yapılandırma ayarları gösterilir **özeti** sekmesinin bölümünde.

   Ortaya çıkan dosyalar adlı bir dizinde yerleştirilir `PublishOutput` projenizin alt dizininde olan *.\bin\release* alt.

Uygulamanızın dosyaları ile birlikte uygulamanızı hata ayıklama bilgilerini içeren bir program veritabanı (.pdb) dosyası yayımlama işlemi yayar. Dosya, öncelikle bir özel durum hata ayıklama için kullanışlıdır. Bu paket, uygulamanızın dosyaları ile değil seçebilirsiniz. Uygulamanızı yayın derlemesinin hatalarını ayıklamak istediğiniz olay, ancak kaydetmeniz gerekir.

İstediğiniz gibi uygulama dosyalarını tam kümesini dağıtın. Örneğin, bunları bir Zip dosyasına paketleyin, basit bir kullanın `copy` komutunu ya da bunları seçtiğiniz herhangi bir yükleme paketi ile birlikte dağıtabilirsiniz. Yüklendikten sonra kullanıcılar daha sonra uygulamanızı kullanarak yürütebilirsiniz `dotnet` komut ve uygulama dosya adı gibi sağlama `dotnet fdd.dll`.

Uygulama ikili dosyalarını ek olarak, yükleyicinizi de paylaşılan framework yükleyici paket veya uygulama yüklemesinin bir parçası olarak bir önkoşul olarak için kontrol edin.  Makine genelinde olduğundan paylaşılan framework'ün yüklemesini yönetici/kök erişim gerektirir.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Framework bağımlı dağıtım üçüncü taraf bağımlılıkları

Bir veya daha fazla üçüncü taraf bağımlılıkları olan bir framework bağımlı dağıtımının bağımlılıkları projenize kullanılabilir olmasını gerektirir. Uygulamanızı oluşturmadan önce aşağıdaki ek adımlar gereklidir:

1. Kullanım **NuGet Paket Yöneticisi** projenize; NuGet paketine başvuru eklemek ve paket zaten sisteminizde kullanılabilir değilse, yükleyin. Paket Yöneticisi'ni açmak için seçmeniz **Araçları** > **NuGet Paket Yöneticisi** > **çözüm için NuGet paketlerini Yönet**.

1. Onaylayın `Newtonsoft.Json` sisteminizde yüklü olduğundan ve yüklü değilse, yükleyin. **Yüklü** sekmesi, sisteminizde yüklü olan NuGet paketlerini listeler. Varsa `Newtonsoft.Json` listelenmiyorsa, seçin **Gözat** sekmesinde ve arama kutusuna "Newtonsoft.Json". Seçin `Newtonsoft.Json` seçip, sağ bölmede, projenizi seçmeden önce **yükleme**.

1. Varsa `Newtonsoft.Json` olduğundan, sisteminizde yüklü, projenize sağ bölmede, proje seçerek eklemek **çözüm için paketlerini Yönet** sekmesi.

Üçüncü taraf bağımlılıkları olan bir framework bağımlı dağıtım yalnızca üçüncü taraf bağımlılıklarını olarak taşınabilir olduğunu unutmayın. Örneğin, bir üçüncü taraf kitaplığı yalnızca macOS destekliyorsa, uygulamayı Windows sistemleri için taşınabilir değildir. Bu, üçüncü taraf bağımlılığı yerel kodu bağımlı olması durumunda gerçekleşir. Bunun iyi bir örnektir [Kestrel sunucu](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), üzerinde yerel bir bağımlılık gerektiren [libuv](https://github.com/libuv/libuv). Bu tür bir üçüncü taraf bağımlılığı bir uygulama için bir FDD oluşturulduğunda, yayımlanan çıktısını bir klasöre her biri için içeren [çalışma zamanı tanımlayıcı (RID)](../rid-catalog.md) yerel bağımlılık destekleyen (ve kendi NuGet paketini var).

## <a name="simpleSelf"></a> Üçüncü taraf bağımlılıkları olmadan kendi içinde dağıtım

Üçüncü taraf bağımlılıkları kendi içinde bir dağıtımla dağıtma içerir proje oluşturma değiştirme *csproj* oluşturmaya, sınamaya ve uygulama yayımlama dosyası. C# dilinde yazılmış basit bir örnek işlemini gösterir.

1. Projeyi oluşturun.

   Seçin **dosya** > **yeni** > **proje**. İçinde **Yeni Proje Ekle** iletişim kutusunda **.NET Core** içinde **yüklü** Proje Türleri bölmesinde ve seçin **konsol uygulaması (.NET Core)** Orta bölmedeki şablonu. "SCD" gibi bir proje adı girin **adı** metin kutusu ve select **Tamam** düğmesi.

1. Uygulamanın kaynak kodunu ekleyin.

   Açık *Program.cs* Düzenleyicisi'nde dosya ve otomatik olarak oluşturulan kodu aşağıdaki kodla değiştirin. Kullanıcının metin girmesini ister ve kullanıcı tarafından girilen kelimeler görüntüler. Normal ifade kullanan `\w+` giriş metnindeki sözcükleri ayırmak için.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Uygulamanızı hedefleyen platformlar tanımlayın.

   1. Projenizde (çözümü değil) sağ tıklatın **Çözüm Gezgini**seçip **Düzenle SCD.csproj**.

   1. Oluşturma bir `<RuntimeIdentifiers>` içindeki `<PropertyGroup>` bölümünü, *csproj* platformları kullanarak uygulamanızın hedeflediği tanımlayan dosyası ve hedeflediğiniz her platform için çalışma zamanı tanımlayıcı (RID) belirtin. Aynı zamanda RID ayırmak için noktalı virgül eklemeniz gerektiğini unutmayın. Bkz: [çalışma zamanı tanımlayıcı Kataloğu](../rid-catalog.md) çalışma zamanı tanımlayıcılarının listesi.

   Örneğin, aşağıdaki örnekte uygulama 64-bit Windows 10 işletim sistemleri ve OS X sürüm 10.11 64-bit işletim sistemi üzerinde çalıştırıldığını gösterir.

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```

   Unutmayın `<RuntimeIdentifiers>` öğesi hiçbir gidebilir `<PropertyGroup>` sahip olduğunuz, *csproj* dosya. Eksiksiz bir örnek *csproj* dosyası bu bölümde daha sonra görünür.

1. Uygulamanızı hata ayıklama yapısını oluşturun.

   Seçin **derleme** > **yapı çözümü**. Ayrıca derlemek ve seçerek uygulamanızı hata ayıklama yapısını çalıştırmak **hata ayıklama** > **hata ayıklamayı Başlat**.

1. Uygulamanızı yayımlayın.

   Hata ayıklama ve test programı sonra her platform için uygulamanızdan bu hedefler dağıtılacak dosyaların oluşturun.

   Uygulamanızı Visual Studio'dan yayımlamak için aşağıdakileri yapın:

      1. Çözüm yapılandırmasını değiştirme **hata ayıklama** için **yayın** uygulamanızın derleme bir sürüm (yerine bir hata ayıklama) sürümü için araç çubuğundaki.

      1. Projede (çözümü değil) sağ tıklatın **Çözüm Gezgini** seçip **Yayımla**.

      1. İçinde **Yayımla** sekmesinde **Yayımla**. Visual Studio, uygulamanızın yerel dosya sistemine oluşturan dosyaların yazar.

      1. **Yayımla** sekmesi, artık tek bir profil gösterir **FolderProfile**. Profilin yapılandırma ayarları gösterilir **özeti** sekmesinin bölümünde. **Hedef çalışma zamanı** hangi çalışma zamanı yayımlanan tanımlar ve **hedef konum** müstakil dağıtımı için dosyaların nerede yazılmış tanımlar.

      1. Visual Studio varsayılan olarak, tüm dosyaları için tek bir dizin yayımlanan yazar. Kolaylık olması için her bir hedef çalışma zamanı için ayrı profiller oluşturun ve yayımlanan dosyaları bir platforma özgü dizinde yerleştirmek için en iyisidir. Bu, her hedef platformu için ayrı bir yayımlama profili oluşturmayı içerir. Aşağıdakileri yaparak her platform için uygulama şimdi yeniden oluşturun:

         1. Seçin **yeni profil oluşturma** içinde **Yayımla** iletişim.

         1. İçinde **yayımlama hedefi seçin** iletişim kutusunda değişiklik **bir klasör seçin** konumuna *bin\Release\PublishOutput\win10 x64*. Seçin **Tamam**.

         1. Yeni profili seçin (**FolderProfile1**) profilleri listesinde olduğundan emin olun **hedef çalışma zamanı** olduğu `win10-x64`. Aksi takdirde seçin **ayarları**. İçinde **profil ayarları** iletişim kutusunda değişiklik **hedef çalışma zamanı** için `win10-x64` seçip **Kaydet**. Aksi takdirde seçin **iptal**.

         1. Seçin **yayımlama** için 64 bit Windows 10 platformlarını kullanarak uygulamanızı yayımlama.

         1. Bir profili yeniden oluşturmak için önceki adımları `osx.10.11-x64` platform. **Hedef konum** olduğu *bin\Release\PublishOutput\osx.10.11-x64*ve **hedef çalışma zamanı** olduğu `osx.10.11-x64`. Visual Studio bu profile atar adı **FolderProfile2**.

      Her bir hedef konum uygulamanızı başlatmak için gerekli dosyaları (uygulama dosyalarınızı ve tüm .NET Core dosyaları) tam kümesini içerdiğine dikkat edin.

Uygulamanızın dosyaları ile birlikte uygulamanızı hata ayıklama bilgilerini içeren bir program veritabanı (.pdb) dosyası yayımlama işlemi yayar. Dosya, öncelikle bir özel durum hata ayıklama için kullanışlıdır. Bu paket, uygulamanızın dosyaları ile değil seçebilirsiniz. Uygulamanızı yayın derlemesinin hatalarını ayıklamak istediğiniz olay, ancak kaydetmeniz gerekir.

Yayımlanan dosyaları istediğiniz herhangi bir şekilde dağıtın. Örneğin, bunları bir Zip dosyasına paketleyin, basit bir kullanın `copy` komutunu ya da bunları seçtiğiniz herhangi bir yükleme paketi ile birlikte dağıtabilirsiniz.

Aşağıdaki tamamlandıktan *csproj* bu proje için dosya.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a>Üçüncü taraf bağımlılıkları kendi içinde dağıtım

Bir veya daha fazla üçüncü taraf bağımlılıkları kendi içinde bir dağıtımının bağımlılıkları ekleme içerir. Uygulamanızı oluşturmadan önce aşağıdaki ek adımlar gereklidir:

1. Kullanım **NuGet Paket Yöneticisi** projenize; NuGet paketine başvuru eklemek ve paket zaten sisteminizde kullanılabilir değilse, yükleyin. Paket Yöneticisi'ni açmak için seçmeniz **Araçları** > **NuGet Paket Yöneticisi** > **çözüm için NuGet paketlerini Yönet**.

1. Onaylayın `Newtonsoft.Json` sisteminizde yüklü olduğundan ve yüklü değilse, yükleyin. **Yüklü** sekmesi, sisteminizde yüklü olan NuGet paketlerini listeler. Varsa `Newtonsoft.Json` listelenmiyorsa, seçin **Gözat** sekmesinde ve arama kutusuna "Newtonsoft.Json". Seçin `Newtonsoft.Json` seçip, sağ bölmede, projenizi seçmeden önce **yükleme**.

1. Varsa `Newtonsoft.Json` olduğundan, sisteminizde yüklü, projenize sağ bölmede, proje seçerek eklemek **çözüm için paketlerini Yönet** sekmesi.

Aşağıdaki tamamlandıktan *csproj* bu proje için dosya:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

Uygulamanızı dağıttığınızda, uygulamanızda kullanılan herhangi bir üçüncü taraf bağımlılıkları ile uygulama dosyalarınızı de yer alır. Üçüncü taraf kitaplıklar, uygulama üzerinde çalıştığı sistemde gerekmez.

Yalnızca bir üçüncü taraf kitaplığı ile kendi içinde bir dağıtım için bu kitaplığı tarafından desteklenen platformlar dağıtabileceğinizi unutmayın. Bu, daha önce yüklü sürece yerel bağımlılıkları hedef platformda nerede var olmaz yerel bağımlılıkları olan üçüncü taraf bağımlılıklarının framework bağımlı dağıtımınızda olması için benzer.

## <a name="see-also"></a>Ayrıca bkz.

* [.NET core uygulama dağıtımı](index.md)
* [.NET core çalışma zamanı tanımlayıcı (RID) Kataloğu](../rid-catalog.md)
