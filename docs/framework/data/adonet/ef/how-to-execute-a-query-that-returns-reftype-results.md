---
title: '방법: RefType 결과를 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
ms.openlocfilehash: 53741b8f2c22f8f20ba3a318218fe518b736d1ac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760663"
---
# <a name="how-to-execute-a-query-that-returns-reftype-results"></a><span data-ttu-id="5f0a5-102">방법: RefType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="5f0a5-102">How to: Execute a Query that Returns RefType Results</span></span>
<span data-ttu-id="5f0a5-103">이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.Metadata.Edm.RefType>를 사용하여 <xref:System.Data.EntityClient.EntityDataReader> 결과를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="5f0a5-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5f0a5-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="5f0a5-105">추가 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 프로젝트에 사용 하 여 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="5f0a5-106">자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="5f0a5-107">응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="5f0a5-108">예제</span><span class="sxs-lookup"><span data-stu-id="5f0a5-108">Example</span></span>  
 <span data-ttu-id="5f0a5-109">이 예제에서는 <xref:System.Data.Metadata.Edm.RefType> 결과를 반환하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-109">This example executes a query that returns <xref:System.Data.Metadata.Edm.RefType> results.</span></span> <span data-ttu-id="5f0a5-110">다음 쿼리를 `ExectueRefTypeQuery` 함수에 인수로 전달하면 이 함수는 엔터티에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-110">If you pass the following query as an argument to the `ExectueRefTypeQuery` function, the function returns a reference to the entity:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref2)]  
  
 <span data-ttu-id="5f0a5-111">다음과 같은 매개 변수가 있는 쿼리를 전달하는 경우 <xref:System.Data.EntityClient.EntityParameter> 개체를 <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> 개체의 <xref:System.Data.EntityClient.EntityCommand> 속성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f0a5-111">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## <a name="see-also"></a><span data-ttu-id="5f0a5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f0a5-112">See Also</span></span>  
 [<span data-ttu-id="5f0a5-113">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="5f0a5-113">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="5f0a5-114">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="5f0a5-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
