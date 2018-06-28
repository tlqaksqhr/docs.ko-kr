---
title: '방법: 이중 계약을 사용 하 여 서비스에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 6675da079b343b1b80477c65260ee8a1f44df72a
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027904"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="31da8-102">방법: 이중 계약을 사용 하 여 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="31da8-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="31da8-103">Windows Communication Foundation (WCF)의 기능 중 하나는 이중 메시징 패턴을 사용 하는 서비스를 만드는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="31da8-104">이 패턴을 사용하면 서비스에서 콜백을 통해 클라이언트와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="31da8-105">이 항목에서는 콜백 인터페이스를 구현 하는 클라이언트 클래스에는 WCF 클라이언트를 만드는 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="31da8-106">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="31da8-107">클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="31da8-108">기본 WCF 서비스 및 클라이언트를 만드는 방법에 대 한 자습서를 참조 하십시오. [초보자를 위한 자습서](../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="31da8-109">이중 서비스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="31da8-109">To access a duplex service</span></span>

1. <span data-ttu-id="31da8-110">두 인터페이스를 포함하는 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="31da8-111">첫 번째 인터페이스는 서비스에 대한 것이고 두 번째 인터페이스는 콜백에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="31da8-112">이중 서비스를 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: 이중 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="31da8-113">서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-113">Run the service.</span></span>

3. <span data-ttu-id="31da8-114">사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 클라이언트에 대 한 계약 (인터페이스)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="31da8-115">이 작업을 수행 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 클라이언트 만들기](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="31da8-116">다음 예제에 표시된 것처럼 클라이언트 클래스에서 콜백 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.Writeline("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="31da8-117"><xref:System.ServiceModel.InstanceContext> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="31da8-118">생성자에 클라이언트 클래스의 인스턴스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="31da8-119">필요로 하는 생성자를 사용 하 여 WCF 클라이언트의 인스턴스를 만들고는 <xref:System.ServiceModel.InstanceContext> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="31da8-120">생성자의 두 번째 매개 변수는 구성 파일에 있는 끝점의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="31da8-121">필요에 따라 WCF 클라이언트의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="31da8-122">예</span><span class="sxs-lookup"><span data-stu-id="31da8-122">Example</span></span>

<span data-ttu-id="31da8-123">다음 코드 예제에서는 이중 계약에 액세스하는 클라이언트 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31da8-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="31da8-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="31da8-124">See also</span></span>

[<span data-ttu-id="31da8-125">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="31da8-125">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
[<span data-ttu-id="31da8-126">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="31da8-126">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
[<span data-ttu-id="31da8-127">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="31da8-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
[<span data-ttu-id="31da8-128">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="31da8-128">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
[<span data-ttu-id="31da8-129">방법: ChannelFactory 사용</span><span class="sxs-lookup"><span data-stu-id="31da8-129">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
