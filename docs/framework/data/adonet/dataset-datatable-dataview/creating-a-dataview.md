---
title: DataView oluşturma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: b88df66ef2e065d1db8d4033eb1fb0e47ebdd189
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536462"
---
# <a name="creating-a-dataview"></a>DataView oluşturma
Oluşturmanın iki yolu vardır. bir <xref:System.Data.DataView>. Kullanabileceğiniz **DataView** oluşturucu veya bir başvuru oluşturabilirsiniz <xref:System.Data.DataTable.DefaultView%2A> özelliği <xref:System.Data.DataTable>. **DataView** Oluşturucu boş olabilir veya ya da sürebilir bir **DataTable** tek bir bağımsız değişken olarak veya bir **DataTable** filtre ölçütlerini ve sıralama ölçütü bir satır ile birlikte Durum Filtresi. Ek bağımsız değişkenleri kullanılabilir ile kullanma hakkında daha fazla bilgi için **DataView**, bkz: [sıralama ve filtreleme veri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Çünkü dizin için bir **DataView** hem zaman yerleşik **DataView** oluşturulur ve herhangi biri **sıralama**, **RowFilter**, veya  **RowStateFilter** özellikleri değiştirildiğinde, tüm ilk sıralama düzeni sağlayan veya oluşturduğunuzda filtreleme ölçütlerini oluşturucu bağımsız en iyi performans elde **DataView**. Oluşturma bir **DataView** sıralama veya filtre ölçütlerini belirtme ve ardından ayarlar olmadan **sıralama**, **RowFilter**, veya **RowStateFilter** özellikleri daha sonra en az iki kere derlenmesi için dizini neden olur: bir kez zaman **DataView** oluşturulur, ve yeniden sıralama veya filtreleme özelliklerinden herhangi birini değiştirildiği.  
  
 Oluşturduğunuz gerçekleştiriyorsanız bir **DataView** herhangi bir bağımsız değişken almaz Oluşturucusu kullanarak, kullanılacak mümkün olmayacaktır **DataView** ayarladığınız kadar **tablo** özelliği .  
  
 Aşağıdaki kod örneğinde nasıl oluşturulacağını gösterir. bir **DataView** kullanarak **DataView** Oluşturucusu. A **RowFilter**, **sıralama** sütun ve **DataViewRowState** ile birlikte sağlanan **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 Aşağıdaki kod örneği, varsayılan bir başvuru almak gösterilmiştir **DataView** , bir **DataTable** kullanarak **DefaultView** tablo özelliğidir.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Verileri Sıralama ve Filtreleme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi](https://go.microsoft.com/fwlink/?LinkId=217917)
