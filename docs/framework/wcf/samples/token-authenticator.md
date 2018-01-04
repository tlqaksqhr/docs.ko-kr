---
title: Token Authenticator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84382f2c-f6b1-4c32-82fa-aebc8f6064db
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d635a1d5122319e228feb4d8a362b7609129c9de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="token-authenticator"></a>Token Authenticator
이 샘플에서는 사용자 지정 토큰 인증자를 구현하는 방법을 보여 줍니다. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 토큰 인증자는 메시지와 함께 사용된 토큰의 유효성을 검사하여 일관성이 있는지 확인하고 토큰과 연관된 ID를 인증하는 데 사용됩니다.  
  
 사용자 지정 토큰 인증자는 다음과 같은 여러 경우에 유용합니다.  
  
-   토큰과 연관된 기본 인증 메커니즘을 재정의하려는 경우  
  
-   사용자 지정 토큰을 빌드하고 있는 경우  
  
 이 샘플은 다음을 보여 줍니다.  
  
-   클라이언트에서 사용자 이름/암호 쌍을 사용하여 인증하는 방법.  
  
-   서버에서 사용자 지정 토큰 인증자를 사용하여 클라이언트 자격 증명의 유효성을 검사하는 방법  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 코드가 사용자 지정 토큰 인증자와 관련되는 방법  
  
-   서버의 X.509 인증서를 사용하여 서버를 인증하는 방법  
  
 또한 이 샘플에서는 사용자 지정 토큰 인증 프로세스 후에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 호출자의 ID에 액세스할 수 있는 방법을 보여 줍니다.  
  
 서비스에서는 서비스와의 통신에 사용할 수 있는 단일 끝점을 노출하며, 이 끝점은 App.config 구성 파일을 사용하여 정의합니다. 끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다. 바인딩은 `wsHttpBinding`의 기본 모드인 message로 설정된 보안 모드가 있는 표준 `wsHttpBinding`을 사용하여 구성됩니다. 이 샘플에서는 클라이언트 사용자 이름 인증을 사용하도록 표준 `wsHttpBinding`를 설정합니다. 또한 서비스는 `serviceCredentials` 동작을 사용하여 서비스 인증서를 구성합니다. `securityCredentials` 동작을 통해 서비스 인증서를 지정할 수 있습니다. 서비스 인증서는 클라이언트에서 서비스를 인증하고 메시지 보호를 제공하는 데 사용됩니다. 다음 구성에서는 뒤에 나오는 설치 지침에 설명된 대로 샘플 설치 중에 설치되는 localhost 인증서를 참조합니다.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <!-- configure base address provided by host -->  
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service" />  
          </baseAddresses>  
        </host>  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
    </services>  
  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
          The serviceCredentials behavior allows one to define a service certificate.  
          A service certificate is used by a client to authenticate the service and provide message protection.  
          This configuration references the "localhost" certificate installed during the setup instructions.  
....        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 클라이언트 끝점 구성은 구성 이름, 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다. 클라이언트 바인딩은 적절한 `Mode` 및 `clientCredentialType`를 사용하여 구성됩니다.  
  
```xml  
<system.serviceModel>  
    <client>  
      <endpoint name=""  
                address="http://localhost:8000/servicemodelsamples/service"   
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator">  
      </endpoint>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
```  
  
 클라이언트 구현에서는 사용할 사용자 이름과 암호를 설정합니다.  
  
```  
static void Main()  
{  
     ...  
     client.ClientCredentials.UserNamePassword.UserName = username;  
     client.ClientCredentials.UserNamePassword.Password = password;  
     ...  
}  
```  
  
## <a name="custom-token-authenticator"></a>사용자 지정 토큰 인증자  
 다음 단계에 따라 사용자 지정 토큰 인증자를 만듭니다.  
  
1.  사용자 지정 토큰 인증자를 작성합니다.  
  
     샘플에서는 사용자 이름에 유효한 전자 메일 형식이 있는지 유효성을 검사하는 사용자 지정 토큰 인증자를 구현합니다. <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>가 파생됩니다. 이 클래스에서 가장 중요한 메서드는 <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>입니다. 이 메서드에서 인증자는 사용자 이름 형식의 유효성을 검사하고 호스트 이름이 악의적인 도메인의 것이 아닌지 확인합니다. 두 조건을 모두 충족할 경우 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 인스턴스의 읽기 전용 컬렉션이 반환되며 이 컬렉션은 사용자 이름 토큰에 저장된 정보를 나타내는 클레임을 제공하는 데 사용됩니다.  
  
    ```  
    protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateUserNamePasswordCore(string userName, string password)  
    {  
        if (!ValidateUserNameFormat(userName))  
            throw new SecurityTokenValidationException("Incorrect UserName format");  
  
        ClaimSet claimSet = new DefaultClaimSet(ClaimSet.System, new Claim(ClaimTypes.Name, userName, Rights.PossessProperty));  
        List<IIdentity> identities = new List<IIdentity>(1);  
        identities.Add(new GenericIdentity(userName));  
        List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);  
        policies.Add(new UnconditionalPolicy(ClaimSet.System, claimSet, DateTime.MaxValue.ToUniversalTime(), identities));  
        return policies.AsReadOnly();  
    }  
    ```  
  
2.  사용자 지정 토큰 인증자에 의해 반환되는 권한 부여 정책을 제공합니다.  
  
     이 샘플에서는 생성자를 통해 전달된 클레임 및 ID 집합을 반환하는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>라는 `UnconditionalPolicy`의 고유한 구현을 제공합니다.  
  
    ```  
    class UnconditionalPolicy : IAuthorizationPolicy  
    {  
        String id = Guid.NewGuid().ToString();  
        ClaimSet issuer;  
        ClaimSet issuance;  
        DateTime expirationTime;  
        IList<IIdentity> identities;  
  
        public UnconditionalPolicy(ClaimSet issuer, ClaimSet issuance, DateTime expirationTime, IList<IIdentity> identities)  
        {  
            if (issuer == null)  
                throw new ArgumentNullException("issuer");  
            if (issuance == null)  
                throw new ArgumentNullException("issuance");  
  
            this.issuer = issuer;  
            this.issuance = issuance;  
            this.identities = identities;  
            this.expirationTime = expirationTime;  
        }  
  
        public string Id  
        {  
            get { return this.id; }  
        }  
  
        public ClaimSet Issuer  
        {  
            get { return this.issuer; }  
        }  
  
        public DateTime ExpirationTime  
        {  
            get { return this.expirationTime; }  
        }  
  
        public bool Evaluate(EvaluationContext evaluationContext, ref object state)  
        {  
            evaluationContext.AddToTarget(this, this.issuance);  
  
            if (this.identities != null)  
            {  
                object value;  
                IList<IIdentity> contextIdentities;  
                if (!evaluationContext.Properties.TryGetValue("Identities", out value))  
                {  
                    contextIdentities = new List<IIdentity>(this.identities.Count);  
                    evaluationContext.Properties.Add("Identities", contextIdentities);  
                }  
                else  
                {  
                    contextIdentities = value as IList<IIdentity>;  
                }  
                foreach (IIdentity identity in this.identities)  
                {  
                    contextIdentities.Add(identity);  
                }  
            }  
  
            evaluationContext.RecordExpirationTime(this.expirationTime);  
            return true;  
        }  
    }  
    ```  
  
3.  사용자 지정 보안 토큰 관리자를 작성합니다.  
  
     <xref:System.IdentityModel.Selectors.SecurityTokenManager>는 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> 메서드를 통해 전달되는 특정 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> 개체에 대한 `CreateSecurityTokenAuthenticator`를 만드는 데 사용됩니다. 또한 보안 토큰 관리자는 토큰 공급자와 토큰 serializer를 만드는 데 사용되지만 이 샘플에서는 설명하지 않습니다. 이 샘플에서 사용자 지정 보안 토큰 관리자는 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 클래스에서 상속되며 `CreateSecurityTokenAuthenticator` 메서드를 재정의하여 전달된 토큰 요구 사항에서 사용자 이름 인증자가 요청됨을 나타낼 때 사용자 지정 사용자 이름 토큰 인증자를 반환합니다.  
  
    ```  
    public class MySecurityTokenManager : ServiceCredentialsSecurityTokenManager  
    {  
        MyUserNameCredential myUserNameCredential;  
  
        public MySecurityTokenManager(MyUserNameCredential myUserNameCredential)  
            : base(myUserNameCredential)  
        {  
            this.myUserNameCredential = myUserNameCredential;  
        }  
  
        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)  
        {  
            if (tokenRequirement.TokenType ==  SecurityTokenTypes.UserName)  
            {  
                outOfBandTokenResolver = null;  
                return new MyTokenAuthenticator();  
            }  
            else  
            {  
                return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);  
            }  
        }  
    }  
    ```  
  
4.  사용자 지정 서비스 자격 증명을 작성합니다.  
  
     서비스 자격 증명 클래스는 서비스에 대해 구성된 자격 증명을 나타내는 데 사용되며 토큰 인증자, 토큰 공급자 및 토큰 serializer를 가져오는 데 사용되는 보안 토큰 관리자를 만듭니다.  
  
    ```  
    public class MyUserNameCredential : ServiceCredentials  
    {  
  
        public MyUserNameCredential()  
            : base()  
        {  
        }  
  
        protected override ServiceCredentials CloneCore()  
        {  
            return new MyUserNameCredential();  
        }  
  
        public override SecurityTokenManager CreateSecurityTokenManager()  
        {  
            return new MySecurityTokenManager(this);  
        }  
  
    }  
    ```  
  
5.  사용자 지정 서비스 자격 증명을 사용하도록 서비스를 구성합니다.  
  
     서비스에서 사용자 지정 서비스 자격 증명을 사용할 수 있도록 여기서는 이미 기본 서비스 자격 증명에 미리 구성된 서비스 인증서를 캡처한 후 기본 서비스 자격 증명 클래스를 삭제합니다. 그런 다음 미리 구성된 서비스 인증서를 사용하도록 새 서비스 자격 증명 인스턴스를 구성하고 이 서비스 자격 증명 인스턴스를 서비스 동작에 추가합니다.  
  
    ```  
    ServiceCredentials sc = serviceHost.Credentials;  
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;  
    MyUserNameCredential serviceCredential = new MyUserNameCredential();  
    serviceCredential.ServiceCertificate.Certificate = cert;  
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));  
    serviceHost.Description.Behaviors.Add(serviceCredential);  
    ```  
  
 호출자의 정보를 표시하려면 다음 코드와 같이 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>를 사용합니다. <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>에는 현재 호출자에 대한 클레임 정보가 포함됩니다.  
  
```  
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tSecurity context identity  :  {0}",   
            ServiceSecurityContext.Current.PrimaryIdentity.Name);  
     return;  
}  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
## <a name="setup-batch-file"></a>설치 배치 파일  
 이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다. 다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.  
  
 다음 부분에는 적절한 구성에서 실행할 수 있게 배치 파일을 수정하는 데에 도움이 되는 여러 섹션의 간략한 개요가 소개되어 있습니다.  
  
-   서버 인증서 만들기  
  
     Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다. `%SERVER_NAME%`변수는 서버 이름을 지정합니다. 이 변수를 변경하여 고유의 서버 이름을 지정합니다. 이 배치 파일에서의 기본값은 localhost입니다.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치  
  
     Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다. 이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다. Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
    > [!NOTE]
    >  설치 배치 파일은 Windows SDK 명령 프롬프트에서 실행하도록 설계되었습니다. MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다. 이 환경 변수는 Windows SDK 명령 프롬프트 내에서 자동으로 설정됩니다.  
  
#### <a name="to-set-up-and-build-the-sample"></a>샘플을 설치하고 빌드하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  관리자 권한으로 연 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
    > [!NOTE]
    >  Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다. [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.  
  
2.  service\bin에서 service.exe를 실행합니다.  
  
3.  \client\bin에서 client.exe를 실행합니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
4.  클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
#### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스 컴퓨터에 서비스 이진 파일용 디렉터리를 만듭니다.  
  
2.  서비스 프로그램 파일을 서비스 컴퓨터의 서비스 디렉터리에 복사합니다. Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.  
  
3.  컴퓨터의 정규화된 도메인 이름을 포함하는 주체 이름을 가진 서버 인증서가 있어야 합니다. 이 새로운 인증서 이름을 반영하도록 서비스 App.config 파일을 업데이트해야 합니다. `%SERVER_NAME%` 변수를 서비스가 실행되는 컴퓨터의 정규화된 호스트 이름으로 설정할 경우 Setup.bat를 사용하여 만들 수 있습니다. 관리자 권한으로 연 Visual Studio 명령 프롬프트에서 Setup.bat 파일을 실행해야 합니다.  
  
4.  서버 인증서를 클라이언트의 CurrentUser-TrustedPeople 저장소에 복사합니다. 서버 인증서가 클라이언트의 신뢰할 수 있는 발급자에 의해 발급된 경우를 제외하고는 이 작업을 수행할 필요가 없습니다.  
  
5.  서비스 컴퓨터의 App.config 파일에서 기본 주소 값을 변경하여 localhost 대신 정규화된 컴퓨터 이름을 지정합니다.  
  
6.  서비스 컴퓨터의 명령 프롬프트에서 service.exe를 실행합니다.  
  
7.  언어별 폴더의 \client\bin\ 폴더에서 클라이언트 프로그램 파일을 클라이언트 컴퓨터로 복사합니다.  
  
8.  클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.  
  
9. 클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.  
  
10. 클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
#### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
1.  샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
## <a name="see-also"></a>참고 항목
