---
title: "데이터 멤버 순서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06b311f0ca8e9b0a298cd1d9a5e87ff96d13a787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-member-order"></a><span data-ttu-id="b6e0d-102">데이터 멤버 순서</span><span class="sxs-lookup"><span data-stu-id="b6e0d-102">Data Member Order</span></span>
<span data-ttu-id="b6e0d-103">일부 응용 프로그램에서는 serialize된 XML로 표시되는 데이터 순서와 같이 여러 데이터 멤버로부터 데이터가 전송 또는 수신되는 순서를 알고 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="b6e0d-104">이 순서는 경우에 따라 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="b6e0d-105">이 항목에서는 순서 지정 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="b6e0d-106">기본 규칙</span><span class="sxs-lookup"><span data-stu-id="b6e0d-106">Basic Rules</span></span>  
 <span data-ttu-id="b6e0d-107">데이터의 순서를 지정하는 기본 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-107">The basic rules for data ordering include:</span></span>  
  
-   <span data-ttu-id="b6e0d-108">데이터 계약 형식이 상속 계층 구조의 일부이면 기본 형식의 데이터 멤버가 항상 첫 번째 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
-   <span data-ttu-id="b6e0d-109">그 다음 순서는 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> 특성 집합의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 갖고 있지 않은 현재 형식의 데이터 멤버(사전순)입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
-   <span data-ttu-id="b6e0d-110">그리고 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> 특성 집합의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 가진 데이터 멤버가 그 다음 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="b6e0d-111">이러한 멤버의 순서는 먼저 `Order` 속성 값으로 지정되고, 둘 이상의 멤버가 특정 `Order` 값을 갖고 있으면 사전순으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="b6e0d-112">순서 값을 무시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="b6e0d-113">사전순은 <xref:System.String.CompareOrdinal%2A> 메서드 호출로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b6e0d-114">예제</span><span class="sxs-lookup"><span data-stu-id="b6e0d-114">Examples</span></span>  
 <span data-ttu-id="b6e0d-115">다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="b6e0d-116">XML은 다음과 유사하게 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e0d-116">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>   
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>   
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>   
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6e0d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6e0d-117">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 [<span data-ttu-id="b6e0d-118">데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="b6e0d-118">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="b6e0d-119">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="b6e0d-119">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
