---
title: Özel Durumlar için En İyi Yöntemler
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd38b59e39f938d6347457100243f09935444d88
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "33578091"
---
# <a name="best-practices-for-exceptions"></a>Özel durumlar için en iyi yöntemler

İyi tasarlanmış bir uygulama, özel durumları ve hataları işleyerek uygulama kilitlenmelerini önler. Bu bölümde, özel durumlar oluşturma ve işleme için en iyi uygulamalar açıklanmaktadır.

## <a name="use-trycatchfinally-blocks"></a>Try/catch/finally bloklarını kullanma

Kullanım `try` / `catch` / `finally` büyük olasılıkla bir özel durum oluşturabilir kod etrafında engeller. 

İçinde `catch` engeller, her zaman sipariş özel durumlar en az belirli özel.

Kullanım bir `finally` veya kurtarabilirsiniz olup olmadığını, kaynakları temizlemek için blok.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Genel koşullar, özel durumları atma olmadan işleme

Oluşur ancak bir özel durum harekete, bunları özel durum kaçınır şekilde işlemesi göz önünde bulundurun olasılığı koşulları. Örneğin, zaten kapalı bir bağlantıyı kapatmak çalışırsanız elde edecekleriniz bir `InvalidOperationException`. Bunu kullanarak önlemek bir `if` kapatmak denemeden önce bağlantı durumu denetlemek için bildirimi.

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

Kapatmadan önce bağlantı durumunu denetleme, yakalayabilir `InvalidOperationException` özel durum.

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

Seçmek için yöntem olayın meydana gelmesine ne sıklıkta beklediğinize bağlıdır.

- Olay çok sık oluşmuyorsa, yani gerçekten olağanüstüyse ve bir hatayı gösteriyorsa (beklenmeyen bir dosya sonu gibi), özel durum işlemeyi kullanın. Özel durum işleme kullandığınızda, normal koşullarda daha az kod çalıştırılır.

- Olay düzenli olarak gerçekleşiyorsa ve normal yürütmenin bir parçası olarak kabul, kodda hata koşulları için kontrol edin. Sık karşılaşılan hata koşulları için iade ettiğinizde, özel durumlar önlemek için daha az kod yürütülür.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Sınıflar, özel durumlar önlenebilir olacağı şekilde tasarlayın

Bir sınıfı yöntemleri sağlayabilir veya bir özel durum çağrı yapmak önlemek etkinleştirdiğiniz özellikler tetikleyecektir. Örneğin, bir <xref:System.IO.FileStream> sınıfı, dosyanın sonuna ulaşılıp ulaşılmadığını belirlemeye yardımcı yöntemler sağlar. Bu, dosyanın sonundan okuduğunuzda oluşturulan özel durum önlemek için kullanılabilir. Aşağıdaki örnek, bir özel durum tetiklemeden dosya sonuna kadar okumak gösterilmektedir.

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

Özel durumlar önlemek için başka bir özel durum oluşturmaktansa çok yaygın hata durumları için null döndürmek için yoludur. Çok yaygın olan bir hata durumu, denetiminin normal akışı olarak kabul edilebilir. Bu durumda null değer döndürerek, uygulama performansı üzerindeki etkisini en aza indirirsiniz.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Bir hata kodunu döndürmek yerine özel durumlar

Özel durumlar hataları çağırmak için kod dönüş kodu denetlemedi gözden kaçan geçmemektedir emin olun. 

## <a name="use-the-predefined-net-exception-types"></a>Önceden tanımlanmış .NET özel durum türlerini kullanın

Önceden tanımlanmış bir yalnızca geçerli değildir, yeni bir özel durum sınıfı tanıtır. Örneğin:

- Throw bir <xref:System.InvalidOperationException> bir özellik kümesi veya yöntem çağrısı bir nesnenin geçerli durumuna uygun değilse bir özel durum.

- Throw bir <xref:System.ArgumentException> özel durum veya önceden tanımlanmış sınıfların türetilmesi <xref:System.ArgumentException> geçersiz parametreler geçirilmiş.

## <a name="end-exception-class-names-with-the-word-exception"></a>Son özel durum sınıf adlarını sözcüğü `Exception`

Bir özel durum gerekli olduğunda, uygun şekilde adlandırın ve türetmeniz <xref:System.Exception> sınıfı. Örneğin:

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a>Üç Oluşturucusu özel durum sınıfları içerir.

En az üç ortak oluşturucu kendi özel durum sınıflarınızı oluştururken kullanmak: varsayılan oluşturucu, bir dize iletisi alan bir oluşturucu ve bir dize iletisi ve bir iç özel durum alan bir oluşturucu.

* <xref:System.Exception.%23ctor>, varsayılan değerleri kullanır.
  
* <xref:System.Exception.%23ctor%28System.String%29>, bir dize iletisi kabul eder.  
  
* <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, kabul eden bir dize iletisi ve bir iç özel durum.  
  
Bir örnek için bkz. [nasıl yapılır: Create User-Defined](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Uzaktan kod yürütüldüğünde, özel durum verileri kullanılabilir olduğundan emin olun

Kullanıcı tanımlı özel durumlar oluştururken, özel durumları için meta verileri uzaktan yürütülmekte olan kod için kullanılabilir olduğundan emin olun. 

Örneğin, uygulama etki alanları destekleyen .NET uygulamalarında, uygulama etki alanları arasında özel durumları oluşabilir. Bir özel durum kodu yürütür uygulama etki alanı B uygulama etki alanı oluşturduğunu varsayalım. Uygulama etki alanı için düzgün şekilde catch ve özel durumu işlemek için b uygulama etki alanı tarafından oluşturulan özel durumu içeren derlemeyi bulabilir olmalıdır B uygulama etki alanı kendi uygulama temel bir derlemede bulunan bir özel durum oluşturur, ancak uygulama etki alanı'nın uygulama temel altında değil, uygulama etki alanı özel mümkün olmayacaktır ve ortak dil çalışma zamanı bir <xref:System.IO.FileNotFoundException> özel durum. Bu durumu önlemek için, özel durum bilgisini içeren derlemeyi iki şekilde dağıtabilirsiniz:

- Derlemeyi iki uygulama etki alanı tarafından paylaşılan ortak bir uygulama temel dizinine koyun.

    \- veya -

- Eğer etki alanları ortak bir uygulama temel dizini paylaşmıyorsa, özel durum bilgisi içeren derlemeyi bir tanımlayıcı ad ile imzalayıp derlemeyi genel bütünleştirilmiş kod önbelleğine dağıtarak.

## <a name="use-grammatically-correct-error-messages"></a>Dilbilgisi bakımından doğru hata iletileri kullanın

Açık bir cümle yazın ve bitiş için noktalama işaretleri ekleyin. Atanan dizesindeki her cümle <xref:System.Exception.Message?displayProperty=nameWithType> özelliği, nokta ile bitmelidir. Örneğin, "günlük tablosu taştı." uygun ileti dizesi olabilir.

## <a name="include-a-localized-string-message-in-every-exception"></a>Her özel duruma bir yerelleştirilmiş dize arar: mesaj ekleyin

Kullanıcının gördüğü hata iletisi türetilir <xref:System.Exception.Message?displayProperty=nameWithType> özelliği oluşturulan özel durumun ve değil, özel durum sınıfı adı. Genellikle, bir değer atayın <xref:System.Exception.Message?displayProperty=nameWithType> mesajı dizesine eşliyor geçirerek özelliği `message` bağımsız değişkeni bir [özel Oluşturucu](xref:System.Exception.%23ctor%2A). 

Yerelleştirilmiş uygulamalar için uygulamanızı oluşturabilecek her bir özel durum için ileti yerelleştirilmiş bir dize sağlamanız gerekir. Kaynak dosyaları, yerelleştirilmiş hata iletileri sağlamak için kullanır. Uygulamaları yerelleştirme ve yerelleştirilmiş dizeleri alma hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](../../framework/resources/index.md) ve <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>Özel durumlar, gerektiği gibi ek özellikler sağlar

(Ek olarak özel ileti dizesi) bir özel durum için ek özellikler sağlar. ek bilgiler nerede olursa kullanışlı olacağı programlı bir senaryo olduğunda. Örneğin, <xref:System.IO.FileNotFoundException> sağlar <xref:System.IO.FileNotFoundException.FileName> özelliği.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Yığın izlemesi yararlı olacaktır, böylece bir yerde throw deyimleri

Burada özel durum oluşturulur ve bitişi deyim yığın izleme başlangıcı `catch` deyimi özel durumu yakalar.

## <a name="use-exception-builder-methods"></a>Exception Oluşturucu yöntemleri kullanın

Bir sınıfın uygulamasında aynı özel durumu farklı yerlerde oluşturması yaygındır. Fazla kodu önlemek için, özel durumu oluşturmak ve döndürmek için yardımcı yöntemler kullanın. Örneğin:

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
Bazı durumlarda, özel durum oluşturmak için özel durumun oluşturucusunu kullanmak daha uygun olacak. Örnek bir genel özel durum sınıfı olduğu gibi <xref:System.ArgumentException>.

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a>Bir özel durum oluştururken sonuçları Temizle

Bir yöntemi çağıranlar, bu yöntemde özel durum oluşturulduğunda bunun yan etkileri olmayacağını varsayabilmelidir. Örneğin, bir hesaptan geri alınmasının ve başka bir hesabı ürünü para aktarımı kodunuz ve havale yürütülürken bir özel durum mevzuatı etkin kalmasını istemezsiniz.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

Bu durumu yönetmek için bir havale işlem tarafından oluşturulan özel durumlar yakalayın ve geri çekilen alma yoludur.

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

Bu örnek kullanımını gösterir `throw` inceleyin gerek kalmadan gerçek sorunun nedenini görmek çağıranlar kolaylaştırmak özgün özel yeniden harekete geçirileceğini <xref:System.Exception.InnerException> özelliği. Yeni bir özel durum ve iç özel durum olarak özgün özel durumu içerecek şekilde bir alternatiftir:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a>Ayrıca Bkz.  
[Özel Durumlar](index.md)
