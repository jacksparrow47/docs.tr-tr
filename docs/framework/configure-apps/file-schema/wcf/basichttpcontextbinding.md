---
title: '&lt;BasicHttpContextBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 39b16b82-4ec6-4eff-8031-67e026870961
ms.openlocfilehash: 6a53251f9c5bc828fde1e2cc21cc9d06c477f1d6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419354"
---
# <a name="ltbasichttpcontextbindinggt"></a>&lt;BasicHttpContextBinding&gt;
Bağlam için sağlayan bir bağlama tanımlanıyor <xref:System.ServiceModel.BasicHttpBinding> değişim mekanizması olarak HTTP tanımlama bilgileri etkinleştirerek değiştirilmek üzere.  
  
 \<system.ServiceModel>  
\<bağlamaları >  
\<basicHttpContextBinding >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<basicHttpContextBinding>  
   <binding   
       allowCookies="Boolean"  
       bypassProxyOnLocal="Boolean"  
       closeTimeout="TimeSpan"   
       envelopeVersion="None/Soap11/Soap12"  
       hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"  
       maxReceivedMessageSize="Integer"  
       messageEncoding="Text/Mtom"  
       name="string"   
       openTimeout="TimeSpan"   
       proxyAddress="URI"  
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
       useDefaultWebProxy="Boolean"  
       <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
           <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                  proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                                    realm="string" />  
           <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                                    clientCredentialType="UserName/Certificate"/>  
       </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />   </binding>  
</basicHttpContextBinding>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`allowCookies`|İstemci tanımlama bilgilerini kabul eder ve bunları gelecekteki isteklerde yayar gösteren bir Boole değeri. Varsayılan, `false` değeridir.<br /><br /> Tanımlama bilgileri kullanan ASMX Web Hizmetleri ile etkileşim kurduğunuzda bu özelliği kullanabilirsiniz. Bu şekilde, sunucudan döndürülen tanımlama bilgilerini aydaki hizmet için tüm istemci isteklerini otomatik olarak kopyalanır emin olabilirsiniz.|  
|`bypassProxyOnLocal`|Yerel adresler için proxy sunucusunun atlanıp atlanmayacağını gösteren bir Boole değeri. Varsayılan, `false` değeridir.<br /><br /> Bir Internet kaynağına, yerel adres varsa yereldir. Yerel bir adres aynı bilgisayarda, yerel LAN veya intranet ve, sözdizimsel olarak, URI'ler olduğu gibi bir nokta (.) eksikliği tarafından tanımlanan biridir "http://webserver/" ve "http://localhost/".<br /><br /> Bu öznitelik ayarlama BasicHttpBinding ile yapılandırılmış uç noktaları yerel kaynaklara erişirken proxy sunucusu kullanıp kullanmadığını belirler. Bu öznitelik ise `true`, istekleri yerel Internet kaynakları için proxy sunucusu kullanmayın. Bu öznitelik ayarlandığında Hizmetleri aynı makinede konuşurken bir proxy üzerinden Git istemcilerin istiyorsanız ana bilgisayarın adı (localhost yerine) kullanın `true`.<br /><br /> Bu öznitelik olduğunda `false`, tüm Internet isteklerini Ara sunucu üzerinden yapılır.|  
|`closeTimeout`|A <xref:System.TimeSpan> bir kapatma işlemi tamamlamak sağlanan zaman aralığını belirten bir değer. Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>. Varsayılan değer 00:01:00 ' dir.|  
|`envelopeVersion`|Bu bağlama tarafından işlenen iletiler için kullanılan SOAP sürümünü belirtir. Yalnızca geçerli Soap11 değerdir.|  
|`hostnameComparisonMode`|URI ayrıştırmak için kullanılan HTTP ana bilgisayar adını karşılaştırma modunu belirtir. Bu öznitelik türünde <xref:System.ServiceModel.HostNameComparisonMode>, ana bilgisayar üzerinde URI'yi eşleştirirken hizmete erişmek için kullanılıp kullanılmayacağını belirtir. Varsayılan değer <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, ana bilgisayar adı eşleşme yok sayar.|  
|`maxBufferPoolSize`|Kanaldan iletiler alan ileti arabelleklerinin Yöneticisi tarafından kullanılmak için ayrılan maksimum belleğin belirten bir tamsayı değeri. Varsayılan değer: 524288 (0x80000) bayt.<br /><br /> Arabellek Yöneticisi bir arabellek havuzu kullanarak arabellekler maliyetini en aza indirir. Bunlar dışında kanal geldiğinizde arabellekler iletilerini işlemek için hizmet tarafından gerekli değildir. İleti yükü işlemek için arabellek havuzunda yeterli bellek yoksa, arabellek Yöneticisi çöp toplama taşması artıran CLR yığından ek bellek tahsis etmelisiniz. CLR çöp yığınındaki gelen kapsamlı ayırma arabellek havuzu boyutu çok küçük olduğunu ve bu özniteliği tarafından belirtilen sınırı artırarak performans daha büyük bir ayırma ile geliştirilebilir göstergesidir.|  
|`maxBufferSize`|Bu bağlama ile yapılandırılan bir uç nokta için işlenirken iletileri depolayan bir arabellek, bayt cinsinden en büyük boyutunu belirten bir tamsayı değeri. 65.536 bayt varsayılan değerdir.|  
|`maxReceivedMessageSize`|Bu bağlama ile yapılandırılan bir kanalda alınan iletinin üst bilgiler dahil bayt cinsinden en büyük ileti boyutunu tanımlar. pozitif bir tamsayı. İleti alıcısı için çok büyük ise, gönderici bir SOAP hatasını alır. Alıcı, iletiyi bırakır ve izleme günlüğüne etkinliğin bir giriş oluşturur. Varsayılan 65.536 bayt'tır.|  
|`messageEncoding`|SOAP iletisi kodlamak için kullanılan Kodlayıcısı tanımlar. Geçerli değerler şunlardır:<br /><br /> -Metin: metin ileti Kodlayıcı kullanın.<br />-Mtom: ileti aktarım kuruluş mekanizması 1.0 (MTOM) encoder'ı kullanın.<br /><br /> Metin varsayılandır. Bu öznitelik türünde <xref:System.ServiceModel.WSMessageEncoding>.|  
|`messageVersion`|İstemciler ve bağlama ile yapılandırılan hizmetler tarafından kullanılan ileti sürümü belirtir. Bu öznitelik türünde <xref:System.ServiceModel.Channels.MessageVersion>.|  
|`name`|Bağlama yapılandırma adını içeren bir dize. Bağlama için bir tanımlayıcı olarak kullanıldığından, bu değer benzersiz olmalıdır. Her bağlama sahip bir `name` ve `namespace` birlikte benzersiz özniteliği hizmetinin meta verilerde tanımlayın. Ayrıca, bu ad aynı türdeki bağlamaları arasında benzersizdir. İle başlayarak [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bağlamalar ve davranışları için gerekli değildir bir ada sahip. Varsayılan yapılandırma ve adsız bağlamaları ve davranışları hakkında daha fazla bilgi için bkz: [Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/simplified-configuration.md) ve [WCF hizmetleri için Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`namespace`|XML ad alanı bağlamanın belirtir. Varsayılan değer " http://tempuri.org/Bindings". Her bağlama sahip bir `name` ve `namespace` birlikte benzersiz özniteliği hizmetinin meta verilerde tanımlayın.|  
|`openTimeout`|A <xref:System.TimeSpan> tamamlamak açık işlem için sağlanan zaman aralığını belirten bir değer. Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>. Varsayılan değer 00:01:00 ' dir.|  
|`proxyAddress`|HTTP proxy adresini içeren bir URI. Varsa `useSystemWebProxy` ayarlanır `true`, bu ayar olmalıdır `null`. Varsayılan, `null` değeridir.|  
|`receiveTimeout`|A <xref:System.TimeSpan> tamamlamak alma işlemi için sağlanan zaman aralığını belirten bir değer. Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>. Varsayılan değer 00:10:00 ' dir.|  
|`sendTimeout`|A <xref:System.TimeSpan> tamamlamak bir gönderme işlemi için sağlanan zaman aralığını belirten bir değer. Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>. Varsayılan değer 00:01:00 ' dir.|  
|`textEncoding`|İletileri bağlamadaki yayma için kullanılacak kodlama karakter kümesini ayarlar. Geçerli değerler şunlardır:<br /><br /> -BigEndianUnicode: Unicode kodlama BigEndian.<br />-Unicode: 16-bit kodlaması.<br />-UTF8: 8-bit kodlama<br /><br /> UTF8 varsayılandır. Bu öznitelik türünde <xref:System.Text.Encoding>.|  
|`transferMode`|Geçerli bir <xref:System.ServiceModel.TransferMode> iletilerin ara belleğe veya bir istek veya yanıtı belirten bir değer.|  
|`useDefaultWebProxy`|Otomatik yapılandırılan HTTP Ara sunucusu sisteminin kullanılması gerekip gerekmediğini, varsa belirten bir Boole değeri. Varsayılan, `true` değeridir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Güvenlik >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Bağlama için güvenlik ayarlarını tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.|  
|[\<readerQuotas >](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<bağlamaları >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Bu öğe, standart ve özel bağlamalar koleksiyonunu tutar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bağlama öğesi ve bir değişim mekanizması bağlamının bir parçası olarak bir koruma düzeyi sağlar. bir `BasicHttpBinding`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.BasicHttpContextBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpContextBindingElement>  
 <xref:System.ServiceModel.Channels.ContextBindingElement>  
 [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)  
 [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Windows Communication Foundation Hizmetleri ve istemcileri yapılandırmak için bağlamaları kullanma](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<bağlama >](../../../../../docs/framework/misc/binding.md)  
 [\<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
