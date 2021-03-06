---
title: Bir okuyucudan veri yükleme
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 7e74918c-bc72-4977-a49b-e1520a6d8f60
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5156374708beb07da875d2e2a8a3b74e52e21427
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569980"
---
# <a name="load-data-from-a-reader"></a>Bir okuyucudan veri yükleme
Kullanarak bir XML belgesi yüklerse <xref:System.Xml.XmlDocument.Load%2A> yöntemi ve bir parametresi bir <xref:System.Xml.XmlReader>, verileri diğer biçimlerinden davranışı karşılaştırıldığında ortaya çıkan davranış farklılıklar vardır. Okuyucu ilk durumuna ise <xref:System.Xml.XmlDocument.Load%2A> okuyucudan tüm içeriği kullanır ve XML belge nesne modeli (DOM) Okuyucudaki tüm verileri oluşturur.  
  
 Okuyucu zaten bir düğümünde herhangi bir yerde belge yerleştirilir ve okuyucu sonra geçirilir <xref:System.Xml.XmlDocument.Load%2A> yöntemi, <xref:System.Xml.XmlDocument.Load%2A> geçerli düğüme ve tüm geçerli derinlik belleğe kapatır bitiş etiketi kadar kardeşlerinin okumaya çalışır. Denenen başarısını <xref:System.Xml.XmlDocument.Load%2A> yük çalışırken, okuyucu açıktır düğümde bağlıdır olarak <xref:System.Xml.XmlDocument.Load%2A> okuyucu XML'den doğru biçimlendirilmiş olduğunu doğrular. Doğru biçimlendirilmiş XML değilse <xref:System.Xml.XmlDocument.Load%2A> bir özel durum oluşturur. Örneğin, aşağıdaki düğümleri kümesi iki kök düzeyinde öğesi içerebilir, doğru biçimlendirilmiş XML değil ve <xref:System.Xml.XmlDocument.Load%2A> bir özel durum oluşturur.  
  
-   EndElement düğüm tarafından izlenen bir öğe düğümü arkasından bir öğe düğümü ve ardından, açıklama düğümü.  
  
 Kök düzeyinde bir öğe olduğundan aşağıdaki düğümler kümesini tamamlanmamış bir DOM oluşturur.  
  
-   Açıklama düğümü EndElement düğümü tarafından izlenen bir açıklama düğümü arkasından instruction düğümünü ve ardından.  
  
 Bu bir özel durum oluşturmadığını ve veri yüklenir. Bu düğümler üstüne bir kök öğe ekleyin ve hatasız kaydedilebilmesi için doğru biçimlendirilmiş XML oluşturun.  
  
 Okuyucu belge (örneğin, bir beyaz boşluk veya öznitelik düğümü) kök düzeyinde için geçersiz bir yaprak düğüm üzerinde konumlandırılmış okuyucu yerleştirilmiş kadar okumaya devam eder bir düğümde kökü için kullanılabilir. Belgenin bu noktada yüklemeye başlar.  
  
 Varsayılan olarak, <xref:System.Xml.XmlDocument.Load%2A> XML belge türü tanımı (DTD) veya şema doğrulaması kullanarak geçerli olup olmadığını doğrulamaz. Yalnızca XML iyi biçimlendirilmiş olup olmadığını doğrular. Gerçekleşmesi doğrulama için sırayla oluşturmanız gerekir. bir <xref:System.Xml.XmlReader> kullanarak <xref:System.Xml.XmlReaderSettings> sınıfı. <xref:System.Xml.XmlReader> Sınıfı DTD ya da şema tanım dili (XSD) şeması kullanarak doğrulama zorla. <xref:System.Xml.ValidationType> Özelliği <xref:System.Xml.XmlReaderSettings> sınıfı belirler olup olmadığını <xref:System.Xml.XmlReader> örneği doğrulama zorlar. XML verilerini doğrulama hakkında daha fazla bilgi için Açıklamalar bölümüne bakın <xref:System.Xml.XmlReader> başvuru sayfası.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belge Nesne Modeli (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
