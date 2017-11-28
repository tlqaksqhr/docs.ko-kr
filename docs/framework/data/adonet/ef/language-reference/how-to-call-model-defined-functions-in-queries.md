---
title: "방법: 쿼리에서 모델 정의 함수 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 179c00def6b5a810806d536a8728cbbc544b1084
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>방법: 쿼리에서 모델 정의 함수 호출
이 항목에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 개념적 모델에 정의된 함수를 호출하는 방법에 대해 설명합니다.  
  
 다음 절차에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 모델에 정의된 함수를 호출하는 방법에 대해 간단히 설명합니다. 절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다. 이 절차에서는 사용자가 개념적 모델에서 함수를 정의했다고 가정합니다. 자세한 내용은 참조 [하는 방법: 사용자 지정 함수를 개념적 모델에 정의](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)합니다.  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>개념적 모델에 정의된 함수를 호출하려면  
  
1.  개념적 모델에 정의된 함수로 매핑되는 CLR(공용 언어 런타임) 메서드를 응용 프로그램에 추가합니다. 메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다. 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 및 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 각각 개념적 모델의 네임스페이스 이름과 함수 이름입니다. LINQ에서 함수 이름을 확인할 때는 대/소문자가 구분됩니다.  
  
2.  [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서 이 함수를 호출합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 개념적 모델에 정의된 함수를 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 호출하는 방법을 보여 줍니다. 이 예제에서는 School 모델을 사용합니다. School 모델에 대 한 정보를 참조 하십시오. [School 예제 데이터베이스를 만드는](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) 및 [학교.edmx 파일을 생성](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758)합니다.  
  
 다음의 개념적 모델 함수는 강사가 고용된 이후 경과된 년 수를 반환합니다. 함수를 개념적 모델에 추가 하는 방법에 대 한 내용은 [하는 방법: 사용자 지정 함수를 개념적 모델에 정의](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>예제  
 다음에는 응용 프로그램에 아래 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 개념적 모델 함수에 매핑합니다.  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>예제  
 이제 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 개념적 모델 함수를 호출할 수 있습니다. 다음 코드에서는 고용된 지 10년이 넘은 모든 강사를 표시하는 메서드를 호출합니다.  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [.edmx 파일 개요](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Linq to Entities 쿼리에서 함수를 호출합니다.](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [방법: 개체 메서드로 모델 정의 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
