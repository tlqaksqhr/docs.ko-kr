---
title: 사용자 지정 바인딩 전송 및 인코딩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 8f9af42078bd01cc7de0ea33f4f8e4a395cf961a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500908"
---
# <a name="custom-binding-transport-and-encoding"></a>사용자 지정 바인딩 전송 및 인코딩
사용자 지정 바인딩은 개별 바인딩 요소의 순서 있는 목록에 의해 정의됩니다. 이 샘플에서는 다양한 전송 및 메시지 인코딩 요소를 사용하여 사용자 지정 바인딩을 구성하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에 따라는 [자체 호스트](../../../../docs/framework/wcf/samples/self-host.md), 및 사용자 지정 바인딩을 사용 하는 HTTP, TCP 및 명명 된 파이프 전송을 지원 하기 위해 세 개의 끝점을 구성 하도록 수정 되었습니다. 클라이언트 구성도 비슷하게 수정되었으며 클라이언트 코드는 세 끝점 각각과 통신하도록 변경되었습니다.  
  
 이 샘플에서는 특정 전송 및 메시지 인코딩을 지원하는 사용자 지정 바인딩을 구성하는 방법을 보여 줍니다. 그러기 위해 `binding` 요소를 위한 전송 및 메시지 인코딩을 구성합니다. 바인딩 요소의 순서는 각 채널 스택의 계층을 나타내기 때문에 사용자 지정 바인딩을 정의에서 중요 (참조 [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)). 이 샘플에서는 세 개의 사용자 지정 바인딩, 즉 텍스트 인코딩을 사용하는 HTTP 전송, 텍스트 인코딩을 사용하는 TCP 전송 그리고 이진 인코딩을 사용하는 NamedPipe 전송을 구성합니다.  
  
 서비스 구성에서는 다음과 같이 사용자 지정 바인딩을 정의합니다.  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding   
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 샘플을 실행하면 서비스와 클라이언트 콘솔 창에 모두 작업 요청 및 응답이 표시됩니다. 클라이언트는 세 개의 끝점과 각각 통신합니다. 맨 처음에는 HTTP, 그 다음에는 TCP 마지막으로 NamedPipe에 액세스합니다. 서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.  
  
 `namedPipeTransport` 바인딩은 시스템 간 작업을 지원하지 않으며 동일한 시스템에서의 통신에만 사용됩니다. 따라서 여러 시스템으로 구성된 시나리오에서 샘플을 실행할 경우 클라이언트 코드 파일에서 다음 줄을 주석 처리합니다.  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
>  Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  지침에 따라 솔루션의 C#, c + + 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
  
## <a name="see-also"></a>참고 항목
