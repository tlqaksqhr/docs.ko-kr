---
title: "방법: 서비스 인스턴스 만들기 제어"
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
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c77cae35abacb780aec86750c37c6ecd91ff370
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="2fbdc-102">방법: 서비스 인스턴스 만들기 제어</span><span class="sxs-lookup"><span data-stu-id="2fbdc-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="2fbdc-103">서비스의 인스턴스 모드를 설정하면 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>(및 연결된 사용자 정의 서비스 개체)가 만들어지는 시기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="2fbdc-104">가능한 모드에 대해서는 <xref:System.ServiceModel.InstanceContextMode> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="2fbdc-105">동작 참조 [구성 하 고 런타임 동작을 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-105"> behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="2fbdc-106">작업 예제를 보려면 [동작](../../../../docs/framework/wcf/samples/behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="2fbdc-107">코드를 사용하여 서비스 인스턴스 수명을 제어하려면</span><span class="sxs-lookup"><span data-stu-id="2fbdc-107">To control the service instance lifetime using code</span></span>  
  
1.  <span data-ttu-id="2fbdc-108">서비스 클래스에 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2.  <span data-ttu-id="2fbdc-109"><xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> 또는 <xref:System.ServiceModel.InstanceContextMode.Single> 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="2fbdc-110">예</span><span class="sxs-lookup"><span data-stu-id="2fbdc-110">Example</span></span>  
 <span data-ttu-id="2fbdc-111">다음 코드 예제에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 특성의 <xref:System.ServiceModel.ServiceBehaviorAttribute> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbdc-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2fbdc-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fbdc-112">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [<span data-ttu-id="2fbdc-113">서비스: 동작 샘플</span><span class="sxs-lookup"><span data-stu-id="2fbdc-113">Service: Behaviors Samples</span></span>](http://msdn.microsoft.com/library/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
