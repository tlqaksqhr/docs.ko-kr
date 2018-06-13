---
title: Message Security Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7bf731c1accd6eefc97c27af58ba139992ae1866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502363"
---
# <a name="message-security-windows"></a>Message Security Windows
이 샘플에서는 Windows 인증과 함께 메시지 수준 보안을 사용하도록 <xref:System.ServiceModel.WSHttpBinding> 바인딩을 구성하는 방법을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다. 이 샘플에서 서비스는 IIS(인터넷 정보 서비스)에서 호스트되고 클라이언트는 콘솔 응용 프로그램(.exe)입니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 에 대 한 기본 보안은 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Windows 인증을 사용 하 여 메시지 보안입니다. 이 샘플의 구성 파일을 명시적으로 설정는 `mode` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 를 `Message` 및 `clientCredentialType` 특성을 `Windows`합니다. 이러한 값은 이 바인딩의 기본값이지만 다음 샘플 구성에서와 같이 실제 사용을 보여 주기 위해 명시적으로 구성되었습니다.  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 클라이언트 끝점 구성은 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다. 클라이언트 바인딩은 적절한 `securityMode` 및 `authenticationMode`를 사용하여 구성됩니다.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      <!--The default security for the WSHttpBinding is-->  
      <!--Message security using Windows authentication. -->  
      <!--This configuration explicitly defines the security mode -->  
      <!--as Message and the clientCredentialType as Windows  -->  
      <!--for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A>를 사용하여 호출자의 ID에 액세스하는 방법을 보여 주기 위해 서비스 소스 코드가 수정되었습니다.  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. `GetCallerIdentity`라는 첫 번째 메서드는 호출자 ID의 이름을 클라이언트에게 반환합니다. 클라이언트를 종료하려면 콘솔 창에서 Enter 키를 누릅니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목
