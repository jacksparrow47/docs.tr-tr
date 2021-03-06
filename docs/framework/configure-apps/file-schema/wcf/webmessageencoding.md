---
title: '&lt;webMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: eddda5e805d7e2cc361b6925d34d13eb8fd614f9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385400"
---
# <a name="ltwebmessageencodinggt"></a>&lt;webMessageEncoding&gt;
Düz metin XML'i, JavaScript nesne gösterimi (JSON) ileti Kodlamalar ve okunabilir ve bir Windows Communication Foundation (WCF) bağlaması içinde kullanıldığında yazılan için "ham" ikili içeriğin sağlar.  
  
 \<system.serviceModel>  
\<bağlamaları >  
\<customBinding >  
\<bağlama >  
\<webMessageEncoding >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`maxReadPoolSize`|Yeni okuyucu ayırmadan aynı anda okunabilecek ileti miktarı. Daha büyük havuz boyutları sistemi daha büyük bir çalışma kümesi, etkinlik artışlarını daha dayanıklı hale getirmek. Her iç kodlayıcılarda (yalnızca metin, JSON ve "ham") için 64 okuyucular varsayılandır.<br /><br /> Bu sayı arttıkça bellek tüketimi artırılması, ancak yenilerini oluşturmak yerine, önceden oluşturulan okuyucular havuzundan kullanmanız mümkün olduğundan, gelen iletilerin ani artışları ile dağıtılacak Kodlayıcı hazırlar.|  
|`maxWritePoolSize`|Yeni yazıcı ayırmadan aynı anda gönderilebilecek ileti miktarı. Daha büyük havuz boyutları sistemi daha büyük bir çalışma kümesi, etkinlik artışlarını daha dayanıklı hale getirmek. Her iç kodlayıcılarda (yalnızca metin, JSON ve "ham") için 16 yazıcılar varsayılandır.<br /><br /> Bu sayı arttıkça bellek tüketimi artırılması, ancak yenilerini oluşturmak yerine, önceden oluşturulan yazıcılar havuzundan kullanmanız mümkün olduğundan, giden iletilerin ani artışları ile uğraşmak için Kodlayıcı hazırlar.|  
|`writeEncoding`|Bağlamadaki yayma iletileri için kullanılacak kodlama karakter kümesini belirtir. Geçerli değerler şunlardır:<br /><br /> -UnicodeFffeTextEncoding: Unicode büyük Endian'ya kodlaması.<br />-Utf16TextEncoding: Unicode kodlaması.<br />-Utf8TextEncoding: 8 bit kodlama.<br /><br /> Utf8TextEncoding varsayılandır. Bu öznitelik türünde <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<readerQuotas >](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<bağlama >](../../../../../docs/framework/misc/binding.md)|Özel bağlama tüm bağlama yeteneklerini tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kodlama bir ileti bir dizi bayta dönüştürme işlemidir. Kod çözme ters işlemidir. Bu işlemler, bir karakter kodlaması belirtimi gerektirir.  
  
 `webMessageEncoding` Düz metin XML ve JSON Kodlamalar ve "ham" ikili verileri işlemek için bir dizi iç kodlayıcılar için temsilci atayarak çalışır. Bu temsilci bileşik ileti Kodlayıcı tarafından gerçekleştirilir.  
  
 Bu bağlama öğesi ve kendi bileşik Kodlayıcı tarafından kullanılan SOAP ileti kullanmayan senaryolarda kodlama denetlemek için kullanılan `webHttpBinding` öğesi. Bu senaryolar, "Düz eski XML" (POX), temsili durum aktarımı (REST), gerçekten basit dağıtım (RSS) ve Atom dağıtım ve zaman uyumsuz JavaScript ve XML (AJAX) içerir. Bileşik ileti Kodlayıcı SOAP veya WS-Addressing desteklemez.  
  
 Bağlama öğesi, bir yazma karakter kullanarak kodlaması ile yapılandırılabilir `writeEncoding` özniteliği. Sağlanan <xref:System.Text.Encoding> değeri JSON ve XML metinsel çalışmalarının yazma davranışını belirtir. Okuma sırasında tüm geçerli ileti kodlama ve metin kodlaması anladım.  
  
 `maxReadPoolSize` ve `maxWritePoolSize` okuyucular ve yazıcılar sırasıyla ayrılacak en fazla sayısını ayarlamak için de kullanılabilir. Varsayılan olarak, 64 okuyucular ve yazıcılar 16 ayrılır.  
  
 Varsayılan karmaşıklığı kısıtlamaları, kullanılarak da ayarlanır [ \<readerQuotas >](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) öğesi bir sınıf hizmet (DOS) reddi karşı korumak için uç nokta işlemeyi bağlamak için ileti karmaşıklığı kullanmak için bu girişim saldırıları kaynaklar.  
  
## <a name="example"></a>Örnek  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [İleti Kodlama](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [İleti Kodlayıcı Seçme](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)  
 [Bağlamaları Genişletme](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Özel Bağlamalar](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
