---
title: 클라이언트 런타임 동작 지정
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fb6ba82af23f51e43da57adb0e65c77ee3436676
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="specifying-client-run-time-behavior"></a><span data-ttu-id="82a76-102">클라이언트 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="82a76-102">Specifying Client Run-Time Behavior</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="82a76-103"> 클라이언트는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스와 마찬가지로 클라이언트 응용 프로그램에 맞게 런타임 동작을 수정하도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-103"> clients, like [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] services, can be configured to modify the run-time behavior to suit the client application.</span></span> <span data-ttu-id="82a76-104">세 가지 특성을 사용하여 클라이언트 런타임 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-104">Three attributes are available for specifying client run-time behavior.</span></span> <span data-ttu-id="82a76-105">이중 클라이언트 콜백 개체는 <xref:System.ServiceModel.CallbackBehaviorAttribute> 및 <xref:System.ServiceModel.Description.CallbackDebugBehavior> 특성을 사용하여 런타임 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-105">Duplex client callback objects can use the <xref:System.ServiceModel.CallbackBehaviorAttribute> and <xref:System.ServiceModel.Description.CallbackDebugBehavior> attributes to modify their run-time behavior.</span></span> <span data-ttu-id="82a76-106">다른 특성인 <xref:System.ServiceModel.Description.ClientViaBehavior>는 논리 대상과 직접 네트워크 대상을 구분하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-106">The other attribute, <xref:System.ServiceModel.Description.ClientViaBehavior>, can be used to separate the logical destination from the immediate network destination.</span></span> <span data-ttu-id="82a76-107">또한 이중 클라이언트 콜백 형식은 서비스측 동작 중 일부를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-107">In addition, duplex client callback types can use some of the service-side behaviors.</span></span> <span data-ttu-id="82a76-108">자세한 내용은 참조 [서비스 런타임 동작 지정](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-108">For more information, see [Specifying Service Run-Time Behavior](../../../docs/framework/wcf/specifying-service-run-time-behavior.md).</span></span>  
  
## <a name="using-the-callbackbehaviorattribute"></a><span data-ttu-id="82a76-109">CallbackBehaviorAttribute 사용</span><span class="sxs-lookup"><span data-stu-id="82a76-109">Using the CallbackBehaviorAttribute</span></span>  
 <span data-ttu-id="82a76-110"><xref:System.ServiceModel.CallbackBehaviorAttribute> 클래스를 사용하여 클라이언트 응용 프로그램에서 콜백 계약 구현의 실행 동작을 구성하거나 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-110">You can configure or extend the execution behavior of a callback contract implementation in a client application by using the <xref:System.ServiceModel.CallbackBehaviorAttribute> class.</span></span> <span data-ttu-id="82a76-111">이 특성은 인스턴스 동작과 트랜잭션 설정을 제외하고 <xref:System.ServiceModel.ServiceBehaviorAttribute> 클래스와 유사한 기능을 콜백 클래스에 대해 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-111">This attribute performs a similar function for the callback class as the <xref:System.ServiceModel.ServiceBehaviorAttribute> class, with the exception of instancing behavior and transaction settings.</span></span>  
  
 <span data-ttu-id="82a76-112"><xref:System.ServiceModel.CallbackBehaviorAttribute> 클래스는 콜백 계약을 구현하는 클래스에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-112">The <xref:System.ServiceModel.CallbackBehaviorAttribute> class must be applied to the class that implements the callback contract.</span></span> <span data-ttu-id="82a76-113">비이중 계약 구현에 적용하면 런타임에 <xref:System.InvalidOperationException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-113">If applied to a nonduplex contract implementation, an <xref:System.InvalidOperationException> exception is thrown at run time.</span></span> <span data-ttu-id="82a76-114">다음 코드 예제에서는 <xref:System.ServiceModel.CallbackBehaviorAttribute> 개체를 사용하여 마샬링할 스레드를 확인하고, <xref:System.Threading.SynchronizationContext> 속성을 사용하여 메시지 유효성 검사를 적용하고, <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> 속성을 사용하여 디버깅 목적으로 서비스에 대한 <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> 개체로 예외를 반환하는 콜백 개체의 <xref:System.ServiceModel.FaultException> 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-114">The following code example shows a <xref:System.ServiceModel.CallbackBehaviorAttribute> class on a callback object that uses the <xref:System.Threading.SynchronizationContext> object to determine the thread to marshal to, the <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> property to enforce message validation, and the <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> property to return exceptions as <xref:System.ServiceModel.FaultException> objects to the service for debugging purposes.</span></span>  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a><span data-ttu-id="82a76-115">CallbackDebugBehavior를 사용하여 관리되는 예외 정보의 흐름 활성화</span><span class="sxs-lookup"><span data-stu-id="82a76-115">Using CallbackDebugBehavior to Enable the Flow of Managed Exception Information</span></span>  
 <span data-ttu-id="82a76-116">프로그래밍 방식으로 또는 응용 프로그램 구성 파일에서 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 속성을 `true`로 설정하여 디버깅 목적으로 클라이언트 콜백 개체에 있는 관리되는 예외 정보 흐름을 다시 서비스로 이동되게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-116">You can enable the flow of managed exception information in a client callback object back to the service for debugging purposes by setting the <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> property to `true` either programmatically or from an application configuration file.</span></span>  
  
 <span data-ttu-id="82a76-117">관리되는 예외 정보를 서비스로 이동하면 예외 정보가 내부 클라이언트 구현 정보를 노출하여 권한이 없는 서비스에서 사용할 수 있으므로 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-117">Returning managed exception information to services can be a security risk because exception details expose information about the internal client implementation that  unauthorized services could use.</span></span> <span data-ttu-id="82a76-118">또한 프로그래밍 방식으로 <xref:System.ServiceModel.Description.CallbackDebugBehavior> 속성을 설정할 수도 있지만 배포 시 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 비활성화를 잊기 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-118">In addition, although the <xref:System.ServiceModel.Description.CallbackDebugBehavior> properties can also be set programmatically, it can be easy to forget to disable <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> when deploying.</span></span>  
  
 <span data-ttu-id="82a76-119">보안 문제와 관련이 있으므로 다음 작업을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-119">Because of the security issues involved, it is strongly recommended that:</span></span>  
  
-   <span data-ttu-id="82a76-120">응용 프로그램 구성 파일을 사용하여 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-120">You use an application configuration file to set the value of the <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="82a76-121">제어된 디버깅 시나리오에서만 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-121">You do so only in controlled debugging scenarios.</span></span>  
  
 <span data-ttu-id="82a76-122">다음 코드 예제에서는 클라이언트 콜백 개체의 관리되는 예외 정보를 SOAP 메시지에 반환하도록 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에 지시하는 클라이언트 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-122">The following code example shows a client configuration file that instructs [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] to return managed exception information from a client callback object in SOAP messages.</span></span>  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  
 
## <a name="using-the-clientviabehavior-behavior"></a><span data-ttu-id="82a76-123">ClientViaBehavior 동작 사용</span><span class="sxs-lookup"><span data-stu-id="82a76-123">Using the ClientViaBehavior Behavior</span></span>  
 <span data-ttu-id="82a76-124"><xref:System.ServiceModel.Description.ClientViaBehavior> 동작을 사용하여 전송 채널을 만들어야 하는 Uniform Resource Identifier를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-124">You can use the <xref:System.ServiceModel.Description.ClientViaBehavior> behavior to specify the Uniform Resource Identifier for which the transport channel should be created.</span></span> <span data-ttu-id="82a76-125">직접 네트워크 대상이 메시지의 의도된 프로세서가 아닌 경우 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-125">Use this behavior when the immediate network destination is not the intended processor of the message.</span></span> <span data-ttu-id="82a76-126">이 경우 호출 응용 프로그램에서 최종 대상을 알 필요가 없거나 대상 `Via` 헤더가 주소가 아닌 경우에 다중 홉 대화가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="82a76-126">This enables multiple-hop conversations when the calling application does not necessarily know the ultimate destination or when the destination `Via` header is not an address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a76-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82a76-127">See Also</span></span>  
 [<span data-ttu-id="82a76-128">서비스 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="82a76-128">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
