---
title: "방법: 클래스 또는 구조체에 대한 기본 데이터 계약 만들기"
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
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6241df0fd5a0b6ee532691eee2279f618be25a56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="b6f2d-102">방법: 클래스 또는 구조체에 대한 기본 데이터 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="b6f2d-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="b6f2d-103">이 항목에서는 클래스 또는 구조를 사용하여 데이터 계약을 만드는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b6f2d-104">데이터 계약의 계약 및 사용 하는 참조 [를 사용 하 여 데이터 계약](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-104"> data contracts and how they are used, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="b6f2d-105">만드는 기본 단계를 안내 하는 자습서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 및 클라이언트, 참조는 [초보자를 위한 자습서](../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-105">For a tutorial that walks through the steps of creating a basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client, see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="b6f2d-106">기본 서비스와 클라이언트로 구성 된 작업 예제 응용 프로그램을 참조 하십시오. [기본 데이터 계약](../../../../docs/framework/wcf/samples/basic-data-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="b6f2d-107">클래스 또는 구조체에 대한 기본 데이터 계약을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b6f2d-107">To create a basic data contract for a class or structure</span></span>  
  
1.  <span data-ttu-id="b6f2d-108"><xref:System.Runtime.Serialization.DataContractAttribute> 특성을 클래스에 적용하여 형식에 데이터 계약이 있음을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="b6f2d-109">특성이 없는 경우를 비롯한 모든 public 형식을 serialize할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="b6f2d-110"><xref:System.Runtime.Serialization.DataContractSerializer> 특성이 없는 경우 <xref:System.Runtime.Serialization.DataContractAttribute>는 데이터 계약을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="b6f2d-111">[Serializable 형식](../../../../docs/framework/wcf/feature-details/serializable-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-111"> [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
2.  <span data-ttu-id="b6f2d-112"><xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 각 멤버에 적용하여 serialize되는 멤버(속성, 필드 또는 이벤트)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="b6f2d-113">이러한 멤버를 데이터 멤버라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-113">These members are called data members.</span></span> <span data-ttu-id="b6f2d-114">기본적으로 모든 public 형식을 serialize할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-114">By default, all public types are serializable.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="b6f2d-115">[Serializable 형식](../../../../docs/framework/wcf/feature-details/serializable-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-115"> [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6f2d-116"><xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 private 필드에 적용하여 데이터가 다른 사용자에게 노출되게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="b6f2d-117">멤버에 중요한 데이터가 포함되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6f2d-118">예</span><span class="sxs-lookup"><span data-stu-id="b6f2d-118">Example</span></span>  
 <span data-ttu-id="b6f2d-119">다음 예제에서는 클래스 및 해당 멤버에 `Person` 및 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하여 <xref:System.Runtime.Serialization.DataMemberAttribute> 형식의 데이터 계약을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6f2d-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b6f2d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6f2d-120">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="b6f2d-121">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="b6f2d-121">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="b6f2d-122">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="b6f2d-122">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="b6f2d-123">시작</span><span class="sxs-lookup"><span data-stu-id="b6f2d-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
