---
title: '방법: 다형 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 18e2bfee223fa14ec9a232fe308ad2edda6bec55
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760829"
---
# <a name="how-to-execute-a-polymorphic-query"></a>방법: 다형 쿼리 실행
이 항목에서는 다형를 실행 하는 방법을 보여 줍니다. [!INCLUDE[esql](../../../../../includes/esql-md.md)] 사용 하 여 쿼리는 [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) 연산자입니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1.  추가 [School 모델](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) 프로젝트에 Entity Framework를 사용 하 여 프로젝트를 구성 하 고 있습니다. 자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  개념적 모델의 단계를 수행 하 여 hierrachy 당 테이블 상속을 포함을 수정 [연습: 매핑 상속-계층-테이블](http://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 OFTYPE 연산자를 사용하여 `OnsiteCourses` 컬렉션의 `Courses`만으로 구성된 컬렉션을 가져와서 표시합니다.  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a>참고 항목  
 [Entity Framework용 EntityClient 공급자](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [Entity SQL 언어](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
