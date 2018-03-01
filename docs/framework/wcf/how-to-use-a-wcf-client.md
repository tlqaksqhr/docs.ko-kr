---
title: "방법: Windows Communication Foundation 클라이언트 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0330c386730c6b0436196bb5b85162bc4621c214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>방법: Windows Communication Foundation 클라이언트 사용
이 작업은 기본 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 필요한 6가지 작업 중 마지막 작업입니다. 모든 6 가지 작업의 개요를 참조 하십시오.는 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목입니다.  
  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 프록시를 만들고 구성한 후에는 클라이언트 인스턴스를 만들고 클라이언트 응용 프로그램을 컴파일하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와 통신하는 데 사용할 수 있습니다. 이 항목에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 인스턴스화하고 사용하는 절차에 대해 설명합니다. 이 절차에서는 다음과 같은 세 작업을 수행합니다.  
  
1.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 인스턴스화합니다.  
  
2.  생성된 프록시에서 서비스 작업 호출  
  
3.  작업 호출이 완료되면 클라이언트 닫기  
  
### <a name="to-use-a-windows-communication-foundation-client"></a>Windows Communication Foundation 클라이언트를 사용하려면  
  
1.  GettingStartedClient 프로젝트에서 코드 편집기에서 Program.cs 또는 Program.vb 파일을 열고 기존 코드를 다음 코드로 바꿉니다.  
  
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
  
     GettingStartedClient.ServiceReference1을 가져오는 문 사용 또는 가져오기를 참조하십시오. 이는 Visual Studio에서 서비스 참조 추가에서 생성하는 코드를 가져옵니다. 이 코드는 WCF 프록시를 인스턴스화한 다음 계산기 서비스가 노출한 각 서비스 작업을 호출하고 프록시를 닫고 종료합니다.  
  
 이것으로 초보자를 위한 자습서를 완료했습니다. 서비스 계약을 정의했고 서비스 계약을 구현했으며 WCF 프록시를 생성했고 WCF 클라이언트 응용 프로그램을 구성한 다음 서비스 작업을 호출하기 위해 프록시를 사용했습니다. 응용 프로그램을 테스트하려면 먼저 GettingStartedHost를 실행하여 서비스를 시작한 다음 GettingStartedClient를 실행합니다. GettingStartedHost의 출력은 다음과 같아야 합니다.  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 GettingStartedClient의 출력은 다음과 같아야 합니다.  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a>참고 항목  
 [클라이언트 빌드](../../../docs/framework/wcf/building-clients.md)  
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [기본 WCF 프로그래밍](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [방법: 이중 계약 만들기](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [방법: 이중 계약을 사용하여 서비스 액세스](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [시작](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [자체 호스팅](../../../docs/framework/wcf/samples/self-host.md)
