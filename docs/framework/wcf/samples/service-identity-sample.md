---
title: "Service Identity 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cde8966e89a22b19109688d5da0ff5b45eee55ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="service-identity-sample"></a>Service Identity 샘플
이 Service Identity 샘플에서는 서비스의 ID를 설정하는 방법을 보여 줍니다. 클라이언트는 디자인 타임에 서비스의 메타데이터를 사용하여 ID를 검색한 다음 런타임에 서비스의 ID를 인증할 수 있습니다. 서비스 ID의 개념을 사용하면 클라이언트가 작업을 호출하기 전에 서비스를 인증함으로써 인증되지 않은 호출로부터 클라이언트를 보호할 수 있습니다. 보안 연결에서는 또한 서비스가 클라이언트의 액세스를 허용하기 전에 클라이언트의 자격 증명을 인증하는데, 이 부분은 샘플에서 다루지 않습니다. 예제를 참조 [클라이언트](../../../../docs/framework/wcf/samples/client.md) 서버 인증을 보여 주는 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서는 다음 기능을 보여 줍니다.  
  
-   서비스의 여러 끝점에서 서로 다른 형식의 ID를 설정하는 방법. 각 ID 형식은 서로 다른 기능을 갖습니다. 사용할 ID 형식은 끝점의 바인딩에 사용되는 보안 자격 증명의 형식에 따라 달라집니다.  
  
-   ID는 구성에서 선언을 통해 또는 코드에서 명령을 통해 설정할 수 있습니다. 클라이언트와 서버 모두 구성을 사용하여 ID를 설정하는 것이 일반적입니다.  
  
-   클라이언트에서 사용자 지정 ID를 설정하는 방법. 사용자 지정 ID는 일반적으로 기존 ID 형식을 사용자 지정한 것으로서, 이를 통해 클라이언트가 서비스의 자격 증명에 제공된 다른 클레임 정보를 검사하여 서비스 호출에 앞서 권한 부여 결정을 내릴 수 있습니다.  
  
    > [!NOTE]
    >  이 샘플에서는 identity.com이라는 특정 인증서의 ID와 이 인증서 내부에 포함된 RSA 키를 검사합니다. 클라이언트의 구성에서 인증서 및 RSA ID 형식을 사용할 경우 이 값이 serialize되는 서비스에서 WSDL을 검사하면 이 값을 손쉽게 얻을 수 있습니다.  
  
 다음 샘플 코드에서는 WSHttpBinding을 사용하여 인증서의 DNS(도메인 이름 서버)로 서비스 끝점의 ID를 구성하는 방법을 보여 줍니다.  
  
```  
//Create a service endpoint and set its identity to the certificate's DNS                 
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);  
// Client are Anonymous to the service  
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;  
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);  
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));  
ep.Address = epa;  
```  
  
 또한 이 ID는 App.config 파일의 구성에서 지정할 수도 있습니다. 다음 예제에서는 서비스 끝점에 대해 UPN(User Principal Name) ID를 설정하는 방법을 보여 줍니다.  
  
```xml  
<endpoint address="upnidentity"  
        behaviorConfiguration=""  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_Windows"  
        name="WSHttpBinding_ICalculator_Windows"  
        contract="Microsoft.ServiceModel.Samples.ICalculator">  
  <!-- Set the UPN identity for this endpoint -->  
  <identity>  
      <userPrincipalName value="host\myservice.com" />  
  </identity >  
</endpoint>  
```  
  
 사용자 지정 ID는 <xref:System.ServiceModel.EndpointIdentity> 및 <xref:System.ServiceModel.Security.IdentityVerifier> 클래스에서 파생하여 클라이언트에 설정할 수 있습니다. 개념적으로 <xref:System.ServiceModel.Security.IdentityVerifier> 클래스는 서비스의 `AuthorizationManager` 클래스와 동등한 클라이언트로 간주할 수 있습니다. 다음 코드 예제에서는 `OrgEndpointIdentity`의 구현을 보여 주는데, 이는 서버 인증서의 주체 이름에 일치시킬 조직 이름을 저장합니다. 조직 이름에 대한 권한 부여 검사는 `CheckAccess` 클래스의 `CustomIdentityVerifier` 메서드에서 이루어집니다.  
  
```  
// This custom EndpointIdentity stores an organization name   
public class OrgEndpointIdentity : EndpointIdentity  
{  
    private string orgClaim;  
    public OrgEndpointIdentity(string orgName)  
    {  
        orgClaim = orgName;  
    }  
    public string OrganizationClaim  
    {  
        get { return orgClaim; }  
        set { orgClaim = value; }  
    }  
}  
  
//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to  
//check that X.509 certificate's distinguished name claim contains  
//the organization name e.g. the string value "O=Contoso"   
class CustomIdentityVerifier : IdentityVerifier  
{  
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)  
    {  
        bool returnvalue = false;  
        foreach (ClaimSet claimset in authContext.ClaimSets)  
        {  
            foreach (Claim claim in claimset)  
            {  
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")  
                {  
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;  
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))  
                    {  
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);  
                        Console.WriteLine("Right: {0}", claim.Right);  
                        Console.WriteLine("Resource: {0}",claim.Resource);  
                        Console.WriteLine();  
                        returnvalue = true;  
                    }  
                }  
            }  
        }  
        return returnvalue;  
    }  
}  
```  
  
 이 샘플에서는 언어별 ID 솔루션 폴더에 있는 identity.com이라는 인증서를 사용합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 또는 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 MMC 스냅인 도구를 사용하여 ID 솔루션 폴더의 Identity.pfx 인증서 파일을 LocalMachine/My(개인) 인증서 저장소로 가져옵니다. 이 파일은 암호로 보호됩니다. 가져오는 동안 암호를 묻는 메시지가 나타납니다. 형식 `xyz` 암호 상자에 있습니다. 자세한 내용은 참조는 [하는 방법: MMC 스냅인을 사용 하 여 보기 인증서](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) 항목입니다. 이 작업을 마쳤으면 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 Setup.bat를 실행하여 이 인증서를 CurrentUser/Trusted People 저장소로 복사하여 클라이언트에서 사용할 수 있게 합니다.  
  
2.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
    > [!NOTE]
    >  Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다. [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다. 샘플 사용을 마쳤으면 Cleanup.bat를 실행하여 인증서를 제거해야 합니다. 다른 보안 샘플에도 동일한 인증서가 사용됩니다.  
  
3.  \service\bin 디렉터리에서 Service.exe를 시작합니다. 준비를 눌러야 하는 프롬프트를 표시 하는 서비스에 표시 되는지 확인 \<Enter > 서비스를 종료 합니다.  
  
4.  빌드하고 실행하려면 \client\bin 디렉터리에서 Client.exe를 시작하거나 Visual Studio에서 F5 키를 누릅니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
5.  클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  샘플의 클라이언트 부분을 빌드하기 전에 Client.cs 파일의 `CallServiceCustomClientIdentity` 메서드에서 서비스의 끝점 주소 값을 변경해야 합니다. 그런 다음 샘플을 빌드합니다.  
  
2.  서비스 컴퓨터에 디렉터리를 만듭니다.  
  
3.  서비스 프로그램 파일을 service\bin에서 서비스 컴퓨터에 있는 디렉터리에 복사합니다. Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.  
  
4.  클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.  
  
5.  클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다. Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.  
  
6.  서비스에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다. 실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.  
  
7.  서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
8.  클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다. 여러 개의 인스턴스를 변경해야 합니다.  
  
9. 클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
10. 서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.  
  
11. 클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다. 클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
-   샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
    > [!NOTE]
    >  다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다. 다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다. 이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).  
  
## <a name="see-also"></a>참고 항목
