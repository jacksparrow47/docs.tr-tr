---
title: Uygulama geliştirmede PNRP
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 55716e7baa382bffbb37dc9248ec1cbd15065ac1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504624"
---
# <a name="pnrp-in-application-development"></a>Uygulama geliştirmede PNRP
Windows Vista'da adı yayını ve çözümleme işlevleri bir Basitleştirilmiş PNRP uygulama programlama arabirimiyle (API) ağ uygulamalarına erişebilirsiniz.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Eş Adı Çözümleme Protokolü'nü uygulama  
 Basitleştirilmiş PNRP API ile bulut açıkça adı ve adreslerini kaydetmek için belirtilmedi; PNRP bileşeni, uygun bulut birleştirme ve bulutlarda yayımlamak için adresleri otomatik olarak belirler.  
  
 Son derece Basitleştirilmiş PNRP ad çözümlemesi için Windows Vista'da, PNRP adları artık Windows Sockets işlevi getaddrinfo() tümleştirilmiştir. PNRP bir IPv6 adresi için bir ad çözümlemede kullanmak için uygulamaları getaddrinfo() işlevi tam olarak nitelikli etki alanı adı (FQDN) name.prnp.net çözümlemek için kullanabilir hangi çözümlenen Eş adı addır. Windows Vista'da ayrılmış olarak etki alanı PNRP ad çözümlemesi için pnrp.net etki alanıdır.  
  
 İleti PeerToPeer uygulamalar arasında geçirme PeerChannel'a ve WCF gibi temel mimarileri tarafından işlenen hala [büyük veriler ve akış](https://go.microsoft.com/fwlink/?LinkID=179652).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Net.PeerToPeer>
