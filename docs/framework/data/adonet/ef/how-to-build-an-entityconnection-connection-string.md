---
title: '방법: EntityConnection 연결 문자열 작성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 0ff1e2b00895232b9310ea44ffd1b100b7b9cfc3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759961"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="56c89-102">방법: EntityConnection 연결 문자열 작성</span><span class="sxs-lookup"><span data-stu-id="56c89-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="56c89-103">이 항목에서는 <xref:System.Data.EntityClient.EntityConnection>을 작성하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56c89-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="56c89-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="56c89-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="56c89-105">추가 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 프로젝트에 사용 하 여 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="56c89-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="56c89-106">자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.</span><span class="sxs-lookup"><span data-stu-id="56c89-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="56c89-107">응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56c89-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="56c89-108">예제</span><span class="sxs-lookup"><span data-stu-id="56c89-108">Example</span></span>  
 <span data-ttu-id="56c89-109">다음 예제에서는 기본 공급자에 대한 <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>를 초기화한 다음 <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> 개체를 초기화하고 이 개체를 <xref:System.Data.EntityClient.EntityConnection>의 생성자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="56c89-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="56c89-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56c89-110">See Also</span></span>  
 [<span data-ttu-id="56c89-111">방법: EntityConnection을 사용 하 여 개체 컨텍스트의</span><span class="sxs-lookup"><span data-stu-id="56c89-111">How to: Use EntityConnection with an Object Context</span></span>](http://msdn.microsoft.com/library/2140fe7b-b88b-47c8-a749-d7f142eb1080)  
 [<span data-ttu-id="56c89-112">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="56c89-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
