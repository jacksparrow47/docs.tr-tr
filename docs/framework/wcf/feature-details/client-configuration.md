---
title: İstemci Yapılandırması
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: eef3d4743c26a06bd114618522aff9f68e46628c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527722"
---
# <a name="client-configuration"></a>İstemci Yapılandırması
Windows Communication Foundation (WCF) istemci yapılandırması, adresi, bağlama, davranış ve Sözleşme, istemci uç noktası için hizmet uç noktalarına bağlanmak için hangi istemcilerin kullanın, "ABC" özelliklerini belirtmek için kullanabilirsiniz. [ \<İstemci >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) öğeye sahip bir [ \<uç noktası >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) öğesi özniteliklerini genel uç noktasını yapılandırmak için kullanılır. Bu öznitelikler, bu konunun "Yapılandırma uç noktaları" bölümünde ele alınmıştır.  
  
 [ \<Uç noktası >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) öğeyi de içeren bir [ \<meta veri >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) içeri aktarma ve meta verileri, dışarı aktarma için ayarları belirtmek için kullanılan öğe bir [ \<üstbilgiler >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) özel adres üstbilgileri koleksiyonunu içeren öğe ve bir [ \<kimlik >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) diğer uç noktalar tarafından bir uç nokta kimlik doğrulaması sağlayan öğesi onunla ileti değiş tokuşu. [ \<Üstbilgiler >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) ve [ \<kimlik >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) öğeleridir parçası <xref:System.ServiceModel.EndpointAddress> ve [adresleri](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) konu. Bu konunun yapılandırma meta verileri alt kısmında meta verileri uzantıları kullanımını açıklayan konulara bağlantılar sağlanmaktadır.  
  
## <a name="configuring-endpoints"></a>Uç noktalarını yapılandırma  
 İstemci yapılandırması birini belirtmek istemcinin sağlamak için tasarlanmıştır veya ek uç noktalar, her biri kendi ad, adres ve Sözleşme, her başvuru ile [ \<bağlamaları >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) ve [ \< davranışlar >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) uç noktanın yapılandırmak için kullanılacak istemci yapılandırma öğeleri. Bu WCF çalıştırma zamanı bekliyor adı olduğundan istemci yapılandırma dosyası "App.config" adlı olmalıdır. Aşağıdaki örnek, bir istemci yapılandırma dosyası gösterir.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"   
                 bypassProxyOnLocal="false"   
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"   
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 İsteğe bağlı `name` özniteliği bir uç nokta verilen bir sözleşme için benzersiz olarak tanımlar. Tarafından kullanılan <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> ya da <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> hangi uç noktaya istemci yapılandırmasında hedeflenmiş ve hizmete bir kanal oluşturulduğunda yüklenmesi gereken belirtmek için. Joker karakter uç noktası yapılandırma adı "*" gösterir ve kullanılabilir <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> sağlanmış tam olarak biri kullanılabilir ve aksi takdirde, herhangi bir uç nokta yapılandırma dosyasında yükleyeceğini yöntemi bir özel durum oluşturur. Bu öznitelik belirtilmezse, karşılık gelen uç noktası belirtilen sözleşme türü ile ilişkili varsayılan uç nokta olarak kullanılır. İçin varsayılan değer `name` özniteliktir gibi diğer adıyla eşleşen boş bir dize.  
  
 Her uç nokta bulun ve uç noktayı tanımlamak için kendisiyle ilişkili bir adres olmalıdır. `address` Özniteliği, uç nokta konumu sağlayan URL'yi belirtmek için kullanılabilir. Ancak bir hizmet uç noktası adresi de kodda bir Tekdüzen Kaynak Tanımlayıcısı (URI) oluşturarak belirtilebilir ve eklendiğinden <xref:System.ServiceModel.ServiceHost> birini kullanarak <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> yöntemleri. Daha fazla bilgi için [adresleri](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Giriş da anlaşılacağı gibi [ \<üstbilgiler >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) ve [ \<kimlik >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) öğeleridir parçası <xref:System.ServiceModel.EndpointAddress> de ele [ Adresleri](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) konu.  
  
 `binding` Öznitelik, bir hizmete bağlanılırken kullanılacak uç nokta bağlama türünü bekliyor gösterir. Türü, başvurulabilmesi için ise bir kayıtlı yapılandırma bölümü olması gerekir. Önceki örnekte budur [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) uç noktasını kullandığını gösteren bölüm bir <xref:System.ServiceModel.WSHttpBinding>. Ancak, uç nokta kullanabileceğiniz belirli bir türde birden fazla bağlaması olabilir. Bunların her biri kendi bölümüne sahiptir [ \<bağlama >](../../../../docs/framework/misc/binding.md) (bağlama) türü öğe içinde. `bindingconfiguration` Özniteliği aynı türdeki bağlamaları arasında ayrım yapmak için kullanılır. Değeri ile eşleşen `name` özniteliği [ \<bağlama >](../../../../docs/framework/misc/binding.md) öğesi. Bir istemci yapılandırma hakkında daha fazla bilgi için bkz yapılandırmayı kullanarak bağlama [nasıl yapılır: yapılandırmada İstemci bağlaması belirtme](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 `behaviorConfiguration` Belirtmek için kullanılan öznitelik [ \<davranışı >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) , [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) uç nokta kullanmanız gerekir. Değeri ile eşleşen `name` özniteliği [ \<davranışı >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) öğesi. İstemci davranışlarını belirlemek için yapılandırma kullanma örneği için bkz: [istemci davranışlarını yapılandırma](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 `contract` Öznitelik hangi anlaşmanın uç nokta gösterme belirtir. Bu değer eşlendiği <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> , <xref:System.ServiceModel.ServiceContractAttribute>. Tam tür adı hizmeti uygulayan sınıfın varsayılan değerdir.  
  
### <a name="configuring-metadata"></a>Yapılandırma meta verileri  
 [ \<Meta veri >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) öğe meta verileri kaydetmek için kullanılan ayarları içeri aktarma uzantıları belirtmek için kullanılır. Meta veri sistemini genişletme hakkında daha fazla bilgi için bkz. [meta veri sistemini genişletme](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uç Noktalar: Adresler, Bağlamalar ve Anlaşmalar](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [İstemci Davranışlarını Yapılandırma](../../../../docs/framework/wcf/configuring-client-behaviors.md)
