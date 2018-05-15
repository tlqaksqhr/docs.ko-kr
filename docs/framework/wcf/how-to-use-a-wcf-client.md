---
title: '방법: Windows Communication Foundation 클라이언트 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 79431588e27b02a40d5898929f1bdf644c8a79cd
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="0b552-102">방법: Windows Communication Foundation 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="0b552-102">How to: Use a Windows Communication Foundation Client</span></span>
<span data-ttu-id="0b552-103">이 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 6 가지 작업 중 마지막 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-103">This is the last of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="0b552-104">모든 6 가지 작업의 개요를 참조 하십시오.는 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="0b552-105">Windows Communication Foundation (WCF) 프록시를 생성 하 고 구성 된 된 클라이언트 인스턴스를 만들 수 있으며 클라이언트 응용 프로그램 컴파일 후 WCF 서비스와 통신 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-105">Once a Windows Communication Foundation (WCF) proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the WCF service.</span></span> <span data-ttu-id="0b552-106">이 항목에서는 인스턴스화 및 WCF 클라이언트를 사용 하 여 절차를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-106">This topic describes procedures for instantiating and using a WCF client.</span></span> <span data-ttu-id="0b552-107">이 절차에서는 다음과 같은 세 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-107">This procedure does three things:</span></span>  
  
1.  <span data-ttu-id="0b552-108">WCF 클라이언트를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-108">Instantiates a WCF client.</span></span>  
  
2.  <span data-ttu-id="0b552-109">생성된 프록시에서 서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="0b552-109">Calls the service operations from the generated proxy.</span></span>  
  
3.  <span data-ttu-id="0b552-110">작업 호출이 완료되면 클라이언트 닫기</span><span class="sxs-lookup"><span data-stu-id="0b552-110">Closes the client once the operation call is completed.</span></span>  
  
### <a name="to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="0b552-111">Windows Communication Foundation 클라이언트를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0b552-111">To use a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="0b552-112">GettingStartedClient 프로젝트에서 코드 편집기에서 Program.cs 또는 Program.vb 파일을 열고 기존 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using GettingStartedClient.ServiceReference1;  
  
    namespace GettingStartedClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                //Step 1: Create an instance of the WCF proxy.  
                CalculatorClient client = new CalculatorClient();  
  
                // Step 2: Call the service operations.  
                // Call the Add service operation.  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Subtract service operation.  
                value1 = 145.00D;  
                value2 = 76.54D;  
                result = client.Subtract(value1, value2);  
                Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Multiply service operation.  
                value1 = 9.00D;  
                value2 = 81.25D;  
                result = client.Multiply(value1, value2);  
                Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Divide service operation.  
                value1 = 22.00D;  
                value2 = 7.00D;  
                result = client.Divide(value1, value2);  
                Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
                //Step 3: Closing the client gracefully closes the connection and cleans up resources.  
                client.Close();  
            }  
        }  
    }  
    ```  
  
    ```  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.Text  
    Imports System.ServiceModel  
    Imports GettingStartedClientVB2.ServiceReference1  
  
    Module Module1  
  
        Sub Main()  
            ' Step 1: Create an instance of the WCF proxy  
            Dim Client As New CalculatorClient()  
  
            'Step 2: Call the service operations.  
            'Call the Add service operation.  
            Dim value1 As Double = 100D  
            Dim value2 As Double = 15.99D  
            Dim result As Double = Client.Add(value1, value2)  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Subtract service operation.  
            value1 = 145D  
            value2 = 76.54D  
            result = Client.Subtract(value1, value2)  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Multiply service operation.  
            value1 = 9D  
            value2 = 81.25D  
            result = Client.Multiply(value1, value2)  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Divide service operation.  
            value1 = 22D  
            value2 = 7D  
            result = Client.Divide(value1, value2)  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
            ' Step 3: Closing the client gracefully closes the connection and cleans up resources.  
            Client.Close()  
  
            Console.WriteLine()  
            Console.WriteLine("Press <ENTER> to terminate client.")  
            Console.ReadLine()  
  
        End Sub  
  
    End Module  
    ```  
  
     <span data-ttu-id="0b552-113">GettingStartedClient.ServiceReference1을 가져오는 문 사용 또는 가져오기를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0b552-113">Notice the using or imports statement that imports the GettingStartedClient.ServiceReference1.</span></span> <span data-ttu-id="0b552-114">이는 Visual Studio에서 서비스 참조 추가에서 생성하는 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-114">This imports the code generated by Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="0b552-115">이 코드는 WCF 프록시를 인스턴스화한 다음 계산기 서비스가 노출한 각 서비스 작업을 호출하고 프록시를 닫고 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy and terminates.</span></span>  
  
 <span data-ttu-id="0b552-116">이것으로 초보자를 위한 자습서를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-116">You have now completed the tutorial.</span></span> <span data-ttu-id="0b552-117">서비스 계약을 정의했고 서비스 계약을 구현했으며 WCF 프록시를 생성했고 WCF 클라이언트 응용 프로그램을 구성한 다음 서비스 작업을 호출하기 위해 프록시를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="0b552-118">응용 프로그램을 테스트하려면 먼저 GettingStartedHost를 실행하여 서비스를 시작한 다음 GettingStartedClient를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-118">To test out the application first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span> <span data-ttu-id="0b552-119">GettingStartedHost의 출력은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-119">The output from GettingStartedHost should look like this:</span></span>  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 <span data-ttu-id="0b552-120">GettingStartedClient의 출력은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b552-120">The output from GettingStartedClient should look like this:</span></span>  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b552-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b552-121">See Also</span></span>  
 [<span data-ttu-id="0b552-122">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="0b552-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 [<span data-ttu-id="0b552-123">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0b552-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="0b552-124">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="0b552-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="0b552-125">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="0b552-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="0b552-126">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="0b552-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="0b552-127">방법: 이중 계약을 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="0b552-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="0b552-128">시작</span><span class="sxs-lookup"><span data-stu-id="0b552-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="0b552-129">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="0b552-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
