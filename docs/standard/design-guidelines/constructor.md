---
title: Oluşturucu tasarım
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575563"
---
# <a name="constructor-design"></a>Oluşturucu tasarım
Oluşturucular iki tür vardır: oluşturucular ve örnek oluşturucuları yazın.  
  
 Türü oluşturucuları statik ve CLR tarafından türü kullanılmadan önce çalıştırılır. Örnek oluşturucuları bir türünün bir örneği oluşturulduğunda çalıştırın.  
  
 Türü oluşturucuları parametreleri alamıyor. Örnek oluşturucuları olabilir. Herhangi bir parametre ele yok örnek oluşturucuları genellikle varsayılan oluşturucular denir.  
  
 Oluşturucular bir türün örneklerinin oluşturmak için en iyi yoludur. Çoğu geliştirici arayın ve örnekler (örneğin, Fabrika yöntemleri) oluşturma alternatif yolu düşünmeden önce bir oluşturucu kullanmayı deneyin.  
  
 **✓ CONSIDER** sağlayan basit, ideal olarak varsayılan, Oluşturucular.  
  
 Parametreler çok az sayıda basit bir oluşturucuya sahip ve tüm ilkel veya numaralandırmaları parametreleridir. Bu tür basit oluşturucular framework kullanılabilirliğini artırın.  
  
 **✓ CONSIDER** statik Üreteç yöntemi yerine bir oluşturucu istenen işlemin semantiği doğrudan yapımı yeni bir örneğini eşleşmiyorsa ya da Oluşturucusu tasarım yönergeleri izleyerek doğal olmayan hissi kullanarak.  
  
 **✓ DO** ana özelliklerini ayarlamak için kısayol olarak Oluşturucusu parametrelerini kullanın.  
  
 Semantiği fark olmalıdır bazı özellik kümeleri tarafından izlenen boş Oluşturucusu kullanma ve birden çok bağımsız değişkenlerle bir oluşturucu kullanma.  
  
 **✓ DO** Oluşturucu parametreleri yalnızca özelliğini ayarlamak için kullanılan Oluşturucu parametreleri ve bir özellik için aynı adı kullanın.  
  
 Tür parametreleri ve özellikleri arasındaki tek fark büyük/küçük harfleri.  
  
 **✓ DO** Oluşturucusu en az iş.  
  
 Oluşturucular kadar iş yakalama dışında Oluşturucu parametreleri yapmanız gerekir. Başka bir işlem maliyetini gerekli kadar Gecikmeli.  
  
 **✓ DO** uygunsa örnek Oluşturucular, özel durumlar oluşturma.  
  
 **✓ DO** böyle bir oluşturucu gerekliyse, sınıflar, bir ortak varsayılan oluşturucu açıkça bildirin.  
  
 Bir türde tüm oluşturucular açıkça bildirmeyin, birçok dilde (örneğin, C# ' ta) otomatik olarak ortak varsayılan bir oluşturucu ekleyin. (Soyut sınıflar korumalı Oluşturucu Al)  
  
 Parametreli oluşturucusu için sınıf ekleme derleyici varsayılan oluşturucu eklemesini engeller. Bu genellikle yanlışlıkla önemli değişiklikler neden olur.  
  
 **X AVOID** açıkça varsayılan oluşturucular üzerinde yapıları tanımlama.  
  
 Varsayılan Oluşturucu tanımlanmazsa, bu dizinin her bir yuvada çalıştırılacak sahip olmadığından bu dizi oluşturma daha hızlı hale getirir. C# ' de dahil olmak üzere birçok derleyicileri, bu nedenle parametresiz kurucular yapılar izin verme unutmayın.  
  
 **X AVOID** kurucusu içinde bir nesne üzerinde sanal üyeler çağırma.  
  
 En çok türetilen Tür oluşturucu tam henüz çalıştırılmadı olsa bile sanal üyesi çağırma çağrılacak, en çok türetilen override neden olur.  
  
### <a name="type-constructor-guidelines"></a>Türü kurucusunu yönergeleri  
 **✓ DO** statik oluşturucular özel yap.  
  
 Bir sınıf oluşturucu olarak da adlandırılan bir statik Oluşturucu türü başlatmak için kullanılır. CLR türünün ilk örneği oluşturulduğunda veya ilgili türdeki tüm statik üyeler denir önce statik Oluşturucusu çağırır. Kullanıcının statik Oluşturucusu ne zaman çağrıldığını üzerinde denetimi yoktur. Statik oluşturucu özel durumda değilse, CLR dışında bir kod tarafından çağrılabilir. Oluşturucuda gerçekleştirilen işlemler bağlı olarak bu beklenmeyen davranışlara neden olabilir. C# Derleyici statik oluşturucular özel olmasını zorlar.  
  
 **X DO NOT** statik oluşturucular özel durumlar oluşturma.  
  
 Bir özel durum türü oluşturucudan oluşturulursa türü geçerli uygulama etki alanında kullanılabilir değil.  
  
 **✓ CONSIDER** çalışma zamanı açıkça tanımlanmış bir statik oluşturucusu yok türleri performansını optimize etmek mümkün olduğundan statik oluşturucular açıkça kullanmak yerine statik alanları satır içi başlatılıyor.  
  
 *Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye Tasarımı Yönergeleri](../../../docs/standard/design-guidelines/member.md)  
 [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)
