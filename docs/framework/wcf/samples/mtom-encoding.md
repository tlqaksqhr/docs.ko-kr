---
title: MTOM 인코딩
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d826b5f2973ac451b3943fd78b661093906c72ad
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="mtom-encoding"></a>MTOM 인코딩
이 샘플에서는 WSHttpBinding과 함께 MTOM(Message Transmission Optimization Mechanism) 메시지 인코딩을 사용하는 것을 보여 줍니다. MTOM은 SOAP 메시지와 함께 큰 이진 첨부 파일을 원시 바이트로 전송함으로써 더 작은 크기의 메시지를 허용하는 메커니즘입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 기본적으로 WSHttpBinding은 메시지를 일반 텍스트 XML로 보내고 받습니다. MTOM 메시지를 보내고 받을 수 있도록 다음 예제 코드에서 보여 주는 것처럼 바인딩의 구성에서 또는 `messageEncoding` 속성을 사용하여 직접 바인딩에서 `MessageEncoding` 특성을 설정합니다. 이제 서비스 또는 클라이언트에서 MTOM 메시지를 보내고 받을 수 있습니다.  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 MTOM 인코더는 바이트 및 스트림의 배열을 최적화할 수 있습니다. 이 샘플의 작업에서는 `Stream` 매개 변수를 사용하므로 최적화될 수 있습니다.  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 이 샘플에서 선택된 계약은 이진 데이터를 서비스에 전송하고 업로드된 바이트 수를 반환 값으로 받습니다. 서비스가 설치되고 클라이언트가 실행될 때 숫자 1000을 출력하는데, 이는 총 1000바이트를 수신했음을 나타냅니다. 출력의 나머지에서는 다양한 페이로드에 대해 최적화되고 최적화되지 않은 메시지 크기를 나열합니다.  
  
```  
Output:  
1000  
  
Text encoding with a 100 byte payload: 433  
MTOM encoding with a 100 byte payload: 912  
  
Text encoding with a 1000 byte payload: 1633  
MTOM encoding with a 1000 byte payload: 2080  
  
Text encoding with a 10000 byte payload: 13633  
MTOM encoding with a 10000 byte payload: 11080  
  
Text encoding with a 100000 byte payload: 133633  
MTOM encoding with a 100000 byte payload: 101080  
  
Text encoding with a 1000000 byte payload: 1333633  
MTOM encoding with a 1000000 byte payload: 1001080  
  
Press <ENTER> to terminate client.  
```  
  
 MTOM을 사용하는 목적은 큰 이진 페이로드의 전송을 최적화하는 것입니다. MTOM을 사용하여 SOAP 메시지를 보낼 경우 작은 이진 페이로드에서는 상당한 오버헤드가 되지만, 몇 천 바이트 이상으로 늘어날 경우 상당한 절감 효과를 얻을 수 있습니다. 일반 텍스트 XML이 3바이트마다 4개의 문자가 필요한 Base64를 사용하여 이진 데이터를 인코딩하므로 데이터의 크기가 1/3 증가하기 때문입니다. MTOM에서는 이진 데이터를 원시 바이트로 전송할 수 있으므로 인코딩/디코딩 시간 및 메시지 크기가 줄어듭니다. 오늘날의 비즈니스 문서 및 디지털 사진에 비하면 몇 천 바이트 임계값은 작습니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
3.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
4.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목
