---
title: '&lt;ekleme&gt; öğesi için &lt;schemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 3d3c72fd64042032d44c49ebde867d111ce03b94
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542646"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a>&lt;ekleme&gt; öğesi için &lt;schemaImporterExtensions&gt;
Tarafından kullanılan türleri ekler <xref:System.Xml.Serialization.XmlSchemaImporter> XSD türlerini .NET Framework türleriyle eşlemek için. Yapılandırma dosyaları hakkında daha fazla bilgi için bkz. [yapılandırma dosyası şeması](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<Yapılandırma >  
\<System.xml.Serialization >  
\<schemaImporterExtensions >  
\<Ekle >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Adı**|Örnek bulmak için kullanılan basit bir ad.|  
|**Türü**|Gerekli. Eklemek için şema uzantısı sınıfını belirtir. **Türü** öznitelik değeri tek bir satırda ve gerekir tam tür adını içerir. Derlemesi Genel Derleme Önbelleği'ne (GAC) yerleştirildiğinde, sürüm, kültür ve ortak anahtar belirteci imzalı derleme, aynı zamanda içermelidir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|\<schemaImporterExtensions >|Tarafından kullanılan türler içerir <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde XmlSchemaImporter türleri eşlerken kullanabileceğiniz bir uzantı türü ekler.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [\<System.xml.Serialization > öğesi](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [\<schemaImporterExtensions > öğesi](../../../docs/standard/serialization/schemaimporterextensions-element.md)
