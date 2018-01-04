---
title: "방법: 코드에서 클라이언트 바인딩 지정"
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
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6c44bc03642eb83a28497b320a77b2f9f8c6fb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="d57ff-102">방법: 코드에서 클라이언트 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="d57ff-102">How to: Specify a Client Binding in Code</span></span>
<span data-ttu-id="d57ff-103">이 예제에서는 계산기 서비스를 사용할 클라이언트를 만들고 해당 클라이언트에 대한 바인딩을 코드를 사용하여 명령적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-103">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="d57ff-104">클라이언트는 `CalculatorService` 인터페이스를 구현하는 `ICalculator`에 액세스하고, 서비스 및 클라이언트 모두 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="d57ff-105">이 절차에서는 계산기 서비스를 실행 중인 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-105">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="d57ff-106">서비스를 작성 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 구성에서 서비스 바인딩 지정](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-106">For information about building the service, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="d57ff-107">또한 사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 클라이언트 구성 요소를 자동으로 생성 하도록 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] provides to automatically generate the client components.</span></span> <span data-ttu-id="d57ff-108">이 도구는 서비스에 액세스하기 위한 클라이언트 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-108">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="d57ff-109">클라이언트는 두 가지 부분에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-109">The client is built in two parts.</span></span> <span data-ttu-id="d57ff-110">Svcutil.exe는 `ClientCalculator` 인터페이스를 구현하는 `ICalculator`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="d57ff-111">그런 다음 `ClientCalculator`의 인스턴스를 구성한 후 코드를 사용하여 서비스에 대한 주소와 바인딩을 지정하여 이 클라이언트 응용 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-111">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="d57ff-112">이 예의 원본 사본을 대 한 참조는 [한 기본 바인딩](../../../docs/framework/wcf/samples/basicbinding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="d57ff-112">For the source copy of this example, see the [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="d57ff-113">코드에서 사용자 지정 바인딩을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="d57ff-113">To specify a custom binding in code</span></span>  
  
1.  <span data-ttu-id="d57ff-114">명령줄에서 Svcutil.exe를 사용하여 서비스 메타데이터에서 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-114">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  <span data-ttu-id="d57ff-115">생성된 클라이언트에는 클라이언트 구현에서 충족해야 하는 서비스 계약을 정의하는 `ICalculator` 인터페이스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-115">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3.  <span data-ttu-id="d57ff-116">또한 생성된 클라이언트에는 `ClientCalculator`의 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-116">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4.  <span data-ttu-id="d57ff-117">클라이언트 응용 프로그램에서 `ClientCalculator` 클래스를 사용하는 <xref:System.ServiceModel.BasicHttpBinding>의 인스턴스를 만든 다음 지정된 주소에서 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-117">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5.  <span data-ttu-id="d57ff-118">클라이언트를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d57ff-118">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d57ff-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d57ff-119">See Also</span></span>  
 [<span data-ttu-id="d57ff-120">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d57ff-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
