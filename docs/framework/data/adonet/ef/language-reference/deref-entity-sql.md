---
title: DEREF (varlık SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: abe47f8c72abe13bd5c27fe10a412ff94ab861cf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384973"
---
# <a name="deref-entity-sql"></a>DEREF (varlık SQL)
Bir başvuru değeri ve bu sonucu başvuru oluşturur başvurusunu kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Bir koleksiyon döndürür herhangi bir geçerli ifade.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başvurulan varlık değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 DEREF işleci bir başvuru değeri ve bu sonucu başvuru oluşturur başvurusunu kaldırır. Örneğin, varsa `r` türü ref başvurudur\<T >, `Deref(r)` türündeki bir ifade `T` tarafından başvurulan varlık verir `r`. Başvuru değeri null veya sarkan olduğu (yani, başvuru hedefinin yok), DEREF işlecinin sonucunu null.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sorgu DEREF işleci bir başvuru değeri ve ürettiği sonucu, başvuru başvuru için kullanır. Sorgu, AdventureWorks satış modelini temel alıyor. Derleme ve bu sorguyu çalıştırmak için bu adımları izleyin:  
  
1.  Verilen yordamı izleyin [nasıl yapılır: Bu döndürür PrimitiveType sonuçları sorguyu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Aşağıdaki sorguda ExecutePrimitiveTypeQuery yönteme bağımsız değişken olarak geçirin:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Entity SQL Başvurusu](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [Null Değer Atanabilir Yapılandırılmış Türler](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
