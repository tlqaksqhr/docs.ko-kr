---
title: "방법: 다형 쿼리 실행"
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
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 587428830cd6a2c4870b4f63a64b3566a2dae148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="39ca7-102">방법: 다형 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="39ca7-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="39ca7-103">이 항목에서는 다형를 실행 하는 방법을 보여 줍니다. [!INCLUDE[esql](../../../../../includes/esql-md.md)] 사용 하 여 쿼리는 [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="39ca7-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="39ca7-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="39ca7-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="39ca7-105">추가 [School 모델](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) 프로젝트에 Entity Framework를 사용 하 여 프로젝트를 구성 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ca7-105">Add the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="39ca7-106">자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.</span><span class="sxs-lookup"><span data-stu-id="39ca7-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="39ca7-107">응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39ca7-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="39ca7-108">개념적 모델의 단계를 수행 하 여 hierrachy 당 테이블 상속을 포함을 수정 [연습: 매핑 상속-계층-테이블](http://msdn.microsoft.com/en-us/49b685cf-9db8-4d6d-b885-8837ed238f55)합니다.</span><span class="sxs-lookup"><span data-stu-id="39ca7-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](http://msdn.microsoft.com/en-us/49b685cf-9db8-4d6d-b885-8837ed238f55).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39ca7-109">예</span><span class="sxs-lookup"><span data-stu-id="39ca7-109">Example</span></span>  
 <span data-ttu-id="39ca7-110">다음 예제에서는 OFTYPE 연산자를 사용하여 `OnsiteCourses` 컬렉션의 `Courses`만으로 구성된 컬렉션을 가져와서 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="39ca7-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="39ca7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39ca7-111">See Also</span></span>  
 [<span data-ttu-id="39ca7-112">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="39ca7-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [<span data-ttu-id="39ca7-113">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="39ca7-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
