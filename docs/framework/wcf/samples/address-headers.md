---
title: "주소 헤더"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19a7291ce13221e85b49c6ef97c6b375b8b71014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="address-headers"></a>주소 헤더
Address Headers 샘플은 클라이언트가 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 참조 매개 변수를 서비스에 전달할 수 있는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 WS-Addressing 사양은 특성 웹 서비스 끝점의 주소를 지정하는 방법으로 끝점 참조의 개념을 정의합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 끝점 참조는 `EndpointAddress` 클래스를 사용하여 모델링됩니다. `EndpointAddress`는 `ServiceEndpoint` 클래스의 주소 필드 형식입니다.  
  
 끝점 참조 모델의 일부에서 각 참조는 추가 식별 정보를 추가하는 일부 참조 매개 변수를 전달할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이러한 참조 매개 변수는 `AddressHeader` 클래스의 인스턴스로 모델링됩니다.  
  
 이 샘플에서 클라이언트는 클라이언트 끝점의 `EndpointAddress`에 참조 매개 변수를 추가합니다. 서비스는 이 참조 매개 변수를 찾아서 "Hello" 서비스 작업의 논리에 해당 값을 사용합니다.  
  
## <a name="client"></a>클라이언트  
 클라이언트는 참조 매개 변수를 보내려면 `AddressHeader`의 `EndpointAddress`에 `ServiceEndpoint`를 추가해야 합니다. `EndpointAddress` 클래스를 변경할 수 없으므로 끝점 주소 수정은 `EndpointAddressBuilder` 클래스를 사용하여 수행해야 합니다. 다음 코드에서는 해당 메시지의 일부로 참조 매개 변수를 보내도록 클라이언트를 초기화합니다.  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 이 코드는 원래 `EndpointAddressBuilder`를 초기 값으로 사용하여 `EndpointAddress`를 만듭니다. 그런 다음 새로 만든 주소 헤더를 추가합니다. `CreateAddressHeadercreates`를 호출하면 특정 이름, 네임스페이스 및 값을 가진 헤더가 만들어집니다. 여기서 값은 "John"입니다. 헤더가 작성기에 추가되고 나면 `ToEndpointAddress()` 메서드는 변경할 수 있는 작성기를 변경할 수 없는 끝점 주소로 다시 변환하고 이 주소는 클라이언트 끝점의 주소 필드에 할당됩니다.  
  
 이제 클라이언트가 `Console.WriteLine(client.Hello());`를 호출하면 클라이언트의 결과 출력에 나온 것처럼 서비스는 이 주소 매개 변수의 값을 가져올 수 있습니다.  
  
 `Hello, John`  
  
## <a name="server"></a>서버  
 서비스 작업 `Hello()`의 구현에서는 현재 `OperationContext`를 사용하여 들어오는 메시지에서 헤더 값을 검사합니다.  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 이 코드는 들어오는 메시지의 모든 헤더를 반복하여 특정 이름을 가진 참조 매개 변수인 헤더를 찾습니다. 매개 변수가 발견되면 매개 변수의 값을 읽고 "id" 변수에 저장합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a>참고 항목
