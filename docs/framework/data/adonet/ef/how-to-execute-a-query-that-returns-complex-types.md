---
title: "방법: 복합 형식을 반환하는 쿼리 실행"
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
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9bdd2ba859e97be12cfc4049c73c33ce1402e355
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="f631c-102">방법: 복합 형식을 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="f631c-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="f631c-103">이 항목에서는 복합 형식의 속성이 포함된 엔터티 형식 개체를 반환하는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="f631c-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f631c-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="f631c-105">추가 [AdventureWorks Sales 모델](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) 프로젝트에 사용 하 여 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="f631c-106">자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="f631c-107">응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="f631c-108">.Edmx 파일에 모델을 표시 하려면 두 번 클릭은 [모델 브라우저 창](http://msdn.microsoft.com/en-us/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) 엔터티 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-108">Double click the .edmx file to display the model in the [Model Browser window](http://msdn.microsoft.com/en-us/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) of the Entity Designer.</span></span> <span data-ttu-id="f631c-109">엔터티 디자이너 화면에서 선택 된 `Email` 및 `Phone` 의 속성은 `Contact` 엔터티 형식에 다음 마우스 오른쪽 **새 복합 형식으로 리팩터링**합니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="f631c-110">선택 된 새 복합 형식을 `Email` 및 `Phone` 속성에 추가 되 고 **모델 브라우저**합니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="f631c-111">복합 형식은 기본 이름이 지정:에 형식 이름 바꾸기 `EmailPhone` 에 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="f631c-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="f631c-112">또한 새 `ComplexProperty` 속성이 `Contact` 엔터티 형식에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="f631c-113">속성의 이름을 `EmailPhoneComplexType.`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="f631c-114">만들기 및 엔터티 데이터 모델 마법사를 사용 하 여 복합 형식을 수정 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 복합 형식 속성에 기존 속성 리팩터링](http://msdn.microsoft.com/en-us/5b2eb3b3-693d-42cb-b43a-405812d677eb) 및 [하는 방법: 만들기 및 수정 복합 형식](http://msdn.microsoft.com/en-us/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span><span class="sxs-lookup"><span data-stu-id="f631c-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](http://msdn.microsoft.com/en-us/5b2eb3b3-693d-42cb-b43a-405812d677eb) and [How to: Create and Modify Complex Types](http://msdn.microsoft.com/en-us/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f631c-115">예</span><span class="sxs-lookup"><span data-stu-id="f631c-115">Example</span></span>  
 <span data-ttu-id="f631c-116">다음 예제에서는 컬렉션을 반환 하는 쿼리를 실행 `Contact` 개체의 두 속성을 표시 하 고는 `Contact` 개체: `ContactID` 의 및 값이는 `EmailPhoneComplexType` 복합 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f631c-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
