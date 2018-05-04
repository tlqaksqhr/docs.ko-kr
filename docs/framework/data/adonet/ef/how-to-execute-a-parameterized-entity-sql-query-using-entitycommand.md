---
title: '방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: c8469f8f13178a09c636d33070fd5ad4cbb912aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행
이 항목에서는 실행 하는 방법을 보여 줍니다.는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 를 사용 하 여 매개 변수가 있는 쿼리는 <xref:System.Data.EntityClient.EntityCommand> 개체입니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1.  추가 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 프로젝트에 사용 하 여 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다. 자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 매개 변수가 있는 쿼리 문자열을 생성하는 방법을 보여 줍니다. 그런 다음 <xref:System.Data.EntityClient.EntityCommand>를 만들고 두 매개 변수를 이 <xref:System.Data.EntityClient.EntityParameter>의 <xref:System.Data.EntityClient.EntityCommand> 컬렉션에 추가한 후 `Contact` 항목 컬렉션을 반복합니다.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 매개 변수가 있는 쿼리를 실행 합니다.](http://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
 [Entity SQL 언어](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
