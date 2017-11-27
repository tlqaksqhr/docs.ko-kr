---
title: "방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1531e18a6be3e7ab5c0cec4f19f33692fd04383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="7dc7c-102">방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="7dc7c-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="7dc7c-103">이 항목에서는 실행 하는 방법을 보여 줍니다.는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 를 사용 하 여 매개 변수가 있는 쿼리는 <xref:System.Data.EntityClient.EntityCommand> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="7dc7c-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="7dc7c-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="7dc7c-105">추가 [AdventureWorks Sales 모델](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) 프로젝트에 사용 하 여 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="7dc7c-106">자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="7dc7c-107">응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="7dc7c-108">예제</span><span class="sxs-lookup"><span data-stu-id="7dc7c-108">Example</span></span>  
 <span data-ttu-id="7dc7c-109">다음 예제에서는 두 개의 매개 변수가 있는 쿼리 문자열을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="7dc7c-110">그런 다음 <xref:System.Data.EntityClient.EntityCommand>를 만들고 두 매개 변수를 이 <xref:System.Data.EntityClient.EntityParameter>의 <xref:System.Data.EntityClient.EntityCommand> 컬렉션에 추가한 후 `Contact` 항목 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="7dc7c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dc7c-111">See Also</span></span>  
 [<span data-ttu-id="7dc7c-112">방법: 매개 변수가 있는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc7c-112">How to: Execute a Parameterized Query</span></span>](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
 [<span data-ttu-id="7dc7c-113">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="7dc7c-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
