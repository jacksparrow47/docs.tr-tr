---
title: '&lt;defaultPorts&gt; &lt;ekleme&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd487238ebe327a5f89b737fdf764d94f955a411
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a>&lt;defaultPorts&gt; &lt;ekleme&gt;
İstemci uygulaması dinlediği bir varsayılan iletişim uç noktası.  
  
 \<Sistem. ServiceModel >  
\<davranışları >  
\<serviceBehaviors >  
\<davranışı >  
\<useRequestHeadersForMetadataAddress >  
\<defaultPorts >  
\<ekleme >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|bağlantı noktası|Varsayılan iletişim bağlantı noktası numarası belirten bir tamsayı|  
|düzen|Bir iletişim bağlantı noktası ile ilişkili protokolü ayarları grubu belirten bir dize.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<defaultPorts >](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|İstemci uygulaması dinlediği varsayılan iletişim uç noktalarını listeleme varsayılan bağlantı noktaları koleksiyonu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>