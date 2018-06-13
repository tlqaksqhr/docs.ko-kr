---
title: WS 2007 페더레이션 HTTP 바인딩
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 0fe4c0e62dbff3ae7f99f3a6dde34940abf90ae9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33507083"
---
# <a name="ws-2007-federation-http-binding"></a>WS 2007 페더레이션 HTTP 바인딩
이 샘플에서는 버전 1.3의 WS-Trust 사양을 지원하는 페더레이션 시나리오를 작성하는 데 사용할 수 있는 표준 바인딩인 <xref:System.ServiceModel.WS2007FederationHttpBinding>을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플은 콘솔 기반 클라이언트 프로그램(Client.exe), 콘솔 기반 보안 토큰 서비스 프로그램(Securitytokenservice.exe) 및 콘솔 기반 서비스 프로그램(Service.exe)으로 구성됩니다. 서비스는 요청/회신 통신 패턴을 정의하는 계약을 구현합니다. 계약은 수학 연산(`ICalculator`, `Add`, `Subtract` 및 `Multiply`)을 노출하는 `Divide` 인터페이스에 의해 정의됩니다. 클라이언트가 STS(보안 토큰 서비스)에서 보안 토큰을 가져오고 지정된 수학 연산을 서비스에 동기적으로 요청하면 서비스에서 결과로 회신합니다. 콘솔 창에는 클라이언트 동작이 표시됩니다.  
  
 이 샘플에서는 `ICalculator` 요소를 사용하여 `ws2007FederationHttpBinding` 계약을 사용할 수 있게 만듭니다. 다음 코드에서는 클라이언트에서의 바인딩 구성을 보여 줍니다.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 에 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` 값 사용 해야 하는 보안 모드를 지정 합니다. 이 샘플에서는 `message` 보안을 사용 하는 이유는 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 내에서 지정 된 된 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)합니다. [ \<발급자 >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) 요소 안에 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 주소와 클라이언트 수 있도록 클라이언트에 보안 토큰을 발급 하는 STS에 대 한 바인딩을 지정 인증 하는 `ICalculator` 서비스입니다.  
  
 서비스에서 이 바인딩의 구성은 다음 코드와 같습니다.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 에 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` 값 사용 해야 하는 보안 모드를 지정 합니다. 이 샘플에서는 `message` 보안을 사용 하는 이유는 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 내에서 지정 된 된 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)합니다. [ \<issuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) 요소의 `ws2007FederationHttpBinding` 내는 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 주소 및 검색에 사용할 수 있는 끝점에 대 한 id를 지정 합니다. STS에 대 한 메타 데이터입니다.  
  
 다음 코드에서는 서비스의 동작을 보여 줍니다.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 [ \<a u t h >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> 서비스 클라이언트가 인증 하는 동안 제시할 수 있는 허용 토큰에 대 한 제약 조건을 지정할 수 있습니다. 이 구성은 주체 이름이 CN=STS인 인증서에 의해 서명된 토큰을 서비스에서 수락하도록 지정합니다.  
  
 STS는 표준 <xref:System.ServiceModel.WS2007HttpBinding>을 사용하여 단일 끝점을 사용할 수 있게 만듭니다. 서비스는 토큰에 대한 클라이언트의 요청에 응답합니다. 클라이언트가 Windows 계정을 사용하여 인증될 경우 서비스는 클라이언트의 사용자 이름을 클레임으로 포함하는 토큰을 발급합니다. 토큰을 만드는 도중에 STS는 CN=STS 인증서와 연관된 개인 키를 사용하여 토큰에 서명합니다. 또한 대칭 키를 만들고 CN=localhost 인증서와 연관된 공개 키를 사용하여 이를 암호화합니다. 토큰을 클라이언트에게 반환할 때 STS는 대칭 키도 반환합니다. 클라이언트는 발급된 토큰을 `ICalculator` 서비스에 제공하고 대칭 키로 메시지에 서명하여 해당 키를 알고 있음을 증명합니다.  
  
 샘플을 실행하면 보안 토큰에 대한 요청이 STS 콘솔 창에 표시되고 작업의 요청과 응답이 클라이언트 및 서비스 콘솔 창에 표시됩니다. 응용 프로그램을 종료하려면 아무 콘솔 창에서나 Enter 키를 누릅니다.  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 이 샘플에 포함된 Setup.bat 파일을 사용하면 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버 및 STS를 구성할 수 있습니다. 배치 파일은 LocalMachine/TrustedPeople 인증서 저장소에서 두 개의 인증서를 만듭니다. 주체 이름 CN=STS를 가지는 첫 번째 인증서는 클라이언트에 발급되는 보안 토큰에 서명하기 위해 STS에 사용됩니다. 주체 이름 CN=localhost를 가지는 두 번째 인증서는 서비스에서 해독할 수 있도록 STS에서 키를 암호화할 때 사용됩니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  관리자 권한으로 Visual Studio 명령 프롬프트를 열고 Setup.bat 파일을 실행하여 필요한 인증서를 만듭니다.  
  
 이 배치 파일은 Windows SDK와 함께 배포되는 Certmgr.exe 및 Makecert.exe를 사용합니다. 그러나 스크립트에서 이러한 도구를 찾을 수 있게 하려면 Visual Studio 명령 프롬프트 내에서 Setup.bat를 실행해야 합니다.  
  
1.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
2.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다. 사용 중인 경우 [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], Service.exe, Client.exe를 실행 해야 및 SecurityTokenService.exe로 상승 된 권한을 (파일을 마우스 오른쪽 단추로 누른 **관리자 권한으로 실행**).  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
  
## <a name="see-also"></a>참고 항목
