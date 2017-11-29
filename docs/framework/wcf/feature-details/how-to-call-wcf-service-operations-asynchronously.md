---
title: "방법: 비동기적으로 WCF 서비스 작업 호출"
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
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f8f1419deb60b1f68e47c26c0edd5523a9d23768
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="f7993-102">방법: 비동기적으로 WCF 서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="f7993-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="f7993-103">이 항목에서는 클라이언트에서 서비스 작업에 비동기적으로 액세스하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="f7993-104">이 항목에서 설명하는 서비스에서는 `ICalculator` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="f7993-105">클라이언트는 이벤트 구동 비동기 호출 모델을 사용하여 이 인터페이스에서 작업을 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="f7993-106">(이벤트 기반 비동기 호출 모델에 대 한 자세한 내용은 참조 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="f7993-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="f7993-107">서비스에서 작업을 비동기적으로 구현 하는 방법을 보여 주는 예제를 참조 하십시오. [하는 방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="f7993-108">동기 및 비동기 작업에 대 한 자세한 내용은 참조 [동기 및 비동기 작업](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7993-109"><xref:System.ServiceModel.ChannelFactory%601>를 사용하는 경우 이벤트 구동 비동기 호출 모델이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="f7993-110">사용 하 여 비동기 호출에 대 한 내용은 <xref:System.ServiceModel.ChannelFactory%601>, 참조 [하는 방법: 호출 작업이 비동기적으로 사용 하 여 채널 팩터리](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="f7993-111">프로시저</span><span class="sxs-lookup"><span data-stu-id="f7993-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="f7993-112">WCF 서비스 작업을 비동기적으로 호출하려면</span><span class="sxs-lookup"><span data-stu-id="f7993-112">To call WCF service operations asynchronously</span></span>  
  
1.  <span data-ttu-id="f7993-113">실행의 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 둘 다와 함께 도구는 `/async` 및 `/tcv:Version35` 다음 명령에 표시 된 대로 옵션을 함께 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="f7993-114">이렇게 하면 동기 작업 및 표준 대리자 기반 비동기 작업 이외에 다음을 포함하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class that contains:</span></span>  
  
    -   <span data-ttu-id="f7993-115">두 개의 <`operationName` > `Async` 이벤트 기반 비동기 호출 접근 방식으로 사용 하기 위한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="f7993-116">예:</span><span class="sxs-lookup"><span data-stu-id="f7993-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   <span data-ttu-id="f7993-117">폼의 र ् ण 이벤트가 <`operationName` > `Completed` 이벤트 기반 비동기 호출 접근 방식으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="f7993-118">예:</span><span class="sxs-lookup"><span data-stu-id="f7993-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <span data-ttu-id="f7993-119"><xref:System.EventArgs?displayProperty=nameWithType>각 작업에 대 한 형식 (형식의 <`operationName`>`CompletedEventArgs`) 이벤트 기반 비동기 호출 접근 방식으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="f7993-120">예:</span><span class="sxs-lookup"><span data-stu-id="f7993-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  <span data-ttu-id="f7993-121">호출 응용 프로그램은 다음 샘플 코드에서처럼 비동기 작업이 완료될 때 호출할 콜백 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  <span data-ttu-id="f7993-122">작업을 호출 하기 전에 새 제네릭을 사용 하 여 <xref:System.EventHandler%601?displayProperty=nameWithType> 형식의 <`operationName` > `EventArgs` (이전 단계에서 만든) 처리기 메서드를 추가 하는 <`operationName` > `Completed` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="f7993-123">그런 다음 호출에서 <`operationName` > `Async` 메서드.</span><span class="sxs-lookup"><span data-stu-id="f7993-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="f7993-124">예:</span><span class="sxs-lookup"><span data-stu-id="f7993-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="f7993-125">예제</span><span class="sxs-lookup"><span data-stu-id="f7993-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7993-126">이벤트 기반 비동기 모델에 대한 디자인 지침에 따르면 둘 이상의 값이 반환될 경우 그 중 하나는 `Result` 속성으로 반환되고 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="f7993-127">따라서 클라이언트가 이벤트 기반 비동기 명령 옵션을 사용하여 메타데이터를 가져오고 작업이 둘 이상의 값을 반환할 경우 기본 <xref:System.EventArgs> 개체는 그 중 하나를 `Result` 속성으로 반환하고, 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다. 메시지 개체를 `Result` 속성으로 수신하고 반환된 값을 해당 개체의 속성으로 포함하려면 `/messageContract` 명령 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="f7993-128">이렇게 하면 응답 메시지를 `Result` 개체의 <xref:System.EventArgs> 속성으로 반환하는 서명이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="f7993-129">모든 내부 반환 값은 응답 메시지 개체의 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7993-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f7993-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7993-130">See Also</span></span>  
 [<span data-ttu-id="f7993-131">방법: 비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="f7993-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
