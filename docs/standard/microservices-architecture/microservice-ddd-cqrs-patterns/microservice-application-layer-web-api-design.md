---
title: Mikro hizmet uygulama katmanı ve Web API tasarlama
description: Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Mikro hizmet uygulama katmanı ve Web API tasarlama
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: e5c7e0acb0496aebce4d9cbe8cb51ced0c7166a2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106612"
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Mikro hizmet uygulama katmanı ve Web API tasarlama

## <a name="using-solid-principles-and-dependency-injection"></a>DÜZ ilkeleri ve bağımlılık ekleme kullanılarak

DÜZ ilkeleri mikro hizmet DDD desenlerle geliştirme gibi modern ve kritik bir uygulamada, kullanılacak kritik tekniklerle aynıdır. DÜZ bir kısaltma bu grupları beş temel ilkeler verilmiştir:

-   Tek sorumluluk İlkesi

-   Açık ve kapalı İlkesi

-   Liskov değiştirme İlkesi

-   Arabirim arasında ayrım yapma İlkesi

-   Bağımlılık tersine çevirme ilkesi

DÜZ nasıl uygulamanızı veya mikro hizmet iç Katmanlar tasarlayın ve aralarındaki bağımlılıkları ayırma hakkında daha fazla. Bu etki alanı, ancak uygulamanın teknik tasarım ilişkili değil. Son ilke, bağımlılık tersine çevirme (dı) ilkesini DDD katmanların bir daha iyi ayrılmış uygulaması sağlayan rest katmanların altyapısı katmanından ayırırsınız olanak tanır.

DI bağımlılık ters çevirmeyi ilkesini uygulamak için bir yoludur. Bu nesneler ve onların bağımlılıkları arasındaki bu sıkı bağ elde etmek için bir tekniktir. Ortak Çalışanlar doğrudan başlatmasını veya statik başvuruları kullanma yerine eylemlerini gerçekleştirmek için bir sınıf gereken nesneler için sağlanan (veya "içine eklenen") sınıfı. Çoğu zaman sınıfları bağımlılıklarını açık bağımlılıkları ilkesini izlemek vermeden kendi Oluşturucusu aracılığıyla bildirir. DI genellikle belirli denetimi tersine çevirme (IOC) kapsayıcılarında temel alır. Basit bir yerleşik IOC kapsayıcı ASP.NET Core sağlar, ancak Autofac veya Ninject gibi sık kullanılan IOC kapsayıcı de kullanabilirsiniz.

DÜZ ilkeleri izleyerek sınıflarınızı doğal olarak küçük, iyi faktörlere göre ve kolayca sınanan olma eğilimindedir. Ancak çok fazla bağımlılıkları sınıflar olarak eklenmiş varsa nasıl biliyor? Oluşturucu kullanılarak dı kullanırsanız, yalnızca sizin oluşturucusu için parametre sayısı bakarak algılayan kolay olacaktır. Çok fazla bağımlılıkları varsa, bu genellikle bir işaretidir (bir [kod kokusu](http://deviq.com/code-smells/)) sınıfınız çok işlemini yapmaya çalışan ve büyük olasılıkla tek sorumluluk ilkesini ihlal etme.

DÜZ ayrıntılı olarak ele için başka bir kılavuz kalırsınız. Bu nedenle, bu kılavuzda Bu konu için en az bir bilgiye sahip gerektirir.

#### <a name="additional-resources"></a>Ek kaynaklar

-   **DÜZ: Temel OOP ilkeleri**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **Ters çevirmeyi denetimi kapsayıcıları ve bağımlılık ekleme düzeni**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. Birleştirici yenilikler**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Önceki](nosql-database-persistence-infrastructure.md)
[sonraki](microservice-application-layer-implementation-web-api.md)
