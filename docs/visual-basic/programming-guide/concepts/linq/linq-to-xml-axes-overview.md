---
title: LINQ to XML eksenlerine genel bakış (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9161f151-cfa8-4408-94ba-08a9ba3a486d
ms.openlocfilehash: d7d881564abfdaba6cb7efa8fb92849e48c6fa4c
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332180"
---
# <a name="linq-to-xml-axes-overview-visual-basic"></a>LINQ to XML eksenlerine genel bakış (Visual Basic)
Bir XML ağacı oluşturduğunuz veya bir XML belgesi bir XML ağacına yüklenen sonra öğeler ve öznitelikler bulun ve bunların değerlerini almak için sorgulayabilirsiniz. Koleksiyonlarına almak *eksen yöntemleri*ayrıca adlı *eksenleri*. Bazı eksenleri yöntemlerdir <xref:System.Xml.Linq.XElement> ve <xref:System.Xml.Linq.XDocument> sınıfları döndüren <xref:System.Collections.Generic.IEnumerable%601> koleksiyonları. Eksenlere başlık alanında uzantı yöntemlerini bazıları <xref:System.Xml.Linq.Extensions> sınıfı. Genişletme yöntemleri uygulanan eksenleri koleksiyonlarda çalışır ve koleksiyonları döndürür.  
  
 Bölümünde anlatıldığı gibi [XElement sınıfına genel bakış](https://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec)e <xref:System.Xml.Linq.XElement> nesne tek öğe düğümü temsil eder. Basit bir öğesi olabilir veya bir öğenin içeriğini (yapılandırılmış içeriği olarak da adlandırılır) karmaşık olabilir. Basit bir öğe boş olabilir veya bir değer içerebilir. Düğüm yapılandırılmış içerik varsa, alt öğelerin numaralandırmalar almak için çeşitli eksen yöntemleri kullanabilirsiniz. En sık kullanılan eksen yöntemler <xref:System.Xml.Linq.XContainer.Elements%2A> ve <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
 Koleksiyonları döndüren, eksen yöntemlere ek olarak, yaygın olarak kullanacağı iki daha fazla yöntem vardır [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sorgular. <xref:System.Xml.Linq.XContainer.Element%2A> Tek bir yöntemi döndürür <xref:System.Xml.Linq.XElement>. <xref:System.Xml.Linq.XElement.Attribute%2A> Tek bir yöntemi döndürür <xref:System.Xml.Linq.XAttribute>.  
  
 Birçok amaç için [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgu bir ağaç inceleyebilir, veri ayıklayın ve dönüştürmek için en güçlü bir yol sağlar. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorguları uygulayan nesneler üzerinde çalışan <xref:System.Collections.Generic.IEnumerable%601>ve [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eksen dönüş <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> koleksiyonları ve <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XAttribute> koleksiyonları. Bu koleksiyonlar, sorgular gerçekleştirmek için ihtiyacınız vardır.  
  
 Öğeleri ve özniteliklerinin koleksiyonu almak eksen yöntemlere ek olarak çok ayrıntılı ağacında yinelemek olanak tanıyan eksen yöntem vardır. Örneğin, öğeleri ve öznitelikleri ile ilgilenen yerine ağaç düğümleri ile çalışabilirsiniz. Öğeler ve öznitelikler daha hassas bir taneciklik düzeyini düğümlerdir. Düğümleri ile çalışırken, işleme yönergeleri ve daha fazla XML açıklamaları, metin düğümleri inceleyebilirsiniz. Bu işlev, örneğin, bir sözcük işlemcisi yazma ve XML belgeleri kaydetmek isterse birisi için önemlidir. Ancak, XML programcılar çoğunu öncelikle açısından öğeleri, öznitelikleri ve değerleri.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Öğe koleksiyonu almak için yöntemleri  
 Yöntemlerinin özetini verilmiştir <xref:System.Xml.Linq.XElement> sınıfı (veya kendi temel sınıflar) üzerinde çağıran bir <xref:System.Xml.Linq.XElement> öğelerinin bir koleksiyonunu dönün.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> bu öğenin öncüleri. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen öncüleri <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> , bu öğenin alt öğeleri. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen alt öğelerini <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> bu öğenin alt öğeleri. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen alt öğelerin <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> bu öğeden sonra gelen öğelerin. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen öğelerin bu öğeden sonra <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> bu öğeden önce gelen tüm öğeleri. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen öğelerin bu öğeden önce <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> bu öğeyi ve alt öğelerinden biri. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen öğelerin <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> bu öğeyi ve alt öğeleri. Aşırı döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement> belirtilen öğelerin <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-single-element"></a>Tek bir öğe almak için yöntemi  
 Aşağıdaki yöntem tek bir alt öğesinden alır. bir <xref:System.Xml.Linq.XElement> nesne.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=nameWithType>|İlk alt öğesini döndürür <xref:System.Xml.Linq.XElement> belirtilen nesnesi <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Bir öznitelik koleksiyonu alma yöntemi  
 Aşağıdaki yöntem öznitelikleri alır bir <xref:System.Xml.Linq.XElement> nesne.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|Döndürür bir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XAttribute> tüm öznitelikler.|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Tek bir öznitelik alma yöntemi  
 Aşağıdaki yöntem, tek bir özniteliği alır. bir <xref:System.Xml.Linq.XElement> nesne.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>|Döndürür <xref:System.Xml.Linq.XAttribute> belirtilen olan <xref:System.Xml.Linq.XName>.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ to XML eksenleri (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
