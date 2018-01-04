---
title: "권한 부여 정책"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
caps.latest.revision: "38"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 98d39bdc366eb6b5d757057c3d0e519d81aedd43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="authorization-policy"></a>권한 부여 정책
이 샘플에서는 사용자 지정 클레임 권한 부여 정책 및 연관된 사용자 지정 서비스 인증 관리자를 구현하는 방법을 보여 줍니다. 이 방법은 서비스에서 서비스 작업에 대해 클레임 기반 액세스 검사를 수행하는 경우에 유용하며 액세스 검사 전에 호출자에게 특정 권한을 부여합니다. 이 샘플에서는 클레임을 추가하는 프로세스와 종료된 클레임 집합에 대해 액세스 검사를 수행하는 방법을 보여 줍니다. 클라이언트와 서버 간의 모든 응용 프로그램 메시지는 서명 및 암호화됩니다. 기본적으로 `wsHttpBinding` 바인딩에서는 클라이언트에서 제공하는 사용자 이름과 암호를 사용하여 유효한 Windows NT 계정에 로그온합니다. 이 샘플에서는 사용자 지정을 활용 하는 방법을 보여 줍니다. <!--zz <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>--> `System.IdentityModel.Selectors.UsernamePasswordValidator` 클라이언트를 인증 합니다. 이 샘플에서는 그 외에도 X.509 인증서를 사용하여 서비스에 대해 클라이언트를 인증하는 방법을 보여 줍니다. 이 샘플에서는 서로의 사이에서 특정 사용자에 대해 서비스의 특정 메서드에 대한 액세스 권한을 부여하는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 및 <xref:System.ServiceModel.ServiceAuthorizationManager> 구현을 보여 줍니다. 이 샘플에 따라는 [메시지 보안 사용자 이름](../../../../docs/framework/wcf/samples/message-security-user-name.md), 없지만 이전에 클레임 변환을 수행 하는 방법을 보여 줍니다.는 <xref:System.ServiceModel.ServiceAuthorizationManager> 호출 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 즉, 이 샘플에서는 다음 방법을 보여 줍니다.  
  
-   사용자 이름 및 암호를 사용하여 클라이언트를 인증하는 방법.  
  
-   X.509 인증서를 사용하여 클라이언트를 인증하는 방법.  
  
-   서버에서 사용자 지정 `UsernamePassword` 유효성 검사기를 기준으로 클라이언트의 유효성을 검증하는 방법.  
  
-   서버의 X.509 인증서를 사용하여 서버를 인증하는 방법  
  
-   서버에서 <xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 서비스에 있는 특정 메서드에 대한 액세스를 제어하는 방법.  
  
-   <xref:System.IdentityModel.Policy.IAuthorizationPolicy>를 구현하는 방법.  
  
 서비스는 App.config 구성 파일을 사용하여 정의된, 서비스와의 통신에 사용되는 두 개의 끝점을 노출합니다. 각 끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다. 한 바인딩은 WS-Security 및 클라이언트 사용자 이름 인증을 사용하는 표준 `wsHttpBinding` 바인딩으로 구성됩니다. 다른 바인딩은 WS-Security 및 클라이언트 인증서 인증을 사용하는 표준 `wsHttpBinding` 바인딩으로 구성됩니다. [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 서비스 인증에 사용할 사용자 자격 증명이 지정 합니다. 서버 인증서에 대 한 동일한 값이 있어야 합니다.는 `SubjectName` 속성으로는 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)합니다.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <!-- configure base address provided by host -->  
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>  
        </baseAddresses>  
      </host>  
      <!-- use base address provided by host, provide two endpoints -->  
      <endpoint address="username"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      <endpoint address="certificate"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding2"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Username binding -->  
      <binding name="Binding1">  
        <security mode="Message">  
    <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
      <!-- X509 certificate binding -->  
      <binding name="Binding2">  
        <security mode="Message">  
          <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior" >  
        <serviceDebug includeExceptionDetailInFaults ="true" />  
        <serviceCredentials>  
          <!--   
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.    
          -->  
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />  
          <!--   
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.  
          -->  
          <clientCertificate>  
            <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </clientCertificate>  
          <!--   
          The serviceCredentials behavior allows one to define a service certificate.  
          A service certificate is used by a client to authenticate the service and provide message protection.  
          This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
          <!--   
          The serviceAuthorization behavior allows one to specify custom authorization policies.  
          -->  
          <authorizationPolicies>  
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  
</system.serviceModel>  
```  
  
 각 클라이언트 끝점 구성은 구성 이름, 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다. 클라이언트 바인딩은에서 구성 되어 지정 된 대로 적절 한 보안 모드가 경우에 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 및 `clientCredentialType` 에 지정 된 대로 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- Username based endpoint -->  
      <endpoint name="Username"  
            address="http://localhost:8001/servicemodelsamples/service/username"   
    binding="wsHttpBinding"   
    bindingConfiguration="Binding1"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator" >  
      </endpoint>  
      <!-- X509 certificate based endpoint -->  
      <endpoint name="Certificate"  
                        address="http://localhost:8001/servicemodelsamples/service/certificate"   
                binding="wsHttpBinding"   
            bindingConfiguration="Binding2"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator">  
      </endpoint>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- Username binding -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
        <!-- X509 certificate binding -->  
        <binding name="Binding2">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
    </wsHttpBinding>  
    </bindings>  
  
    <behaviors>  
      <behavior name="ClientCertificateBehavior">  
        <clientCredentials>  
          <serviceCertificate>  
            <!--   
            Setting the certificateValidationMode to PeerOrChainTrust  
            means that if the certificate   
            is in the user's Trusted People store, then it will be   
            trusted without performing a  
            validation of the certificate's issuer chain. This setting   
            is used here for convenience so that the   
            sample can be run without having to have certificates   
            issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust.   
            The security implications of this   
            setting should be carefully considered before using   
            PeerOrChainTrust in production code.   
            -->  
            <authentication certificateValidationMode = "PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 사용자 이름 기반 끝점의 경우 클라이언트 구현에서 사용할 사용자 이름 및 암호를 설정합니다.  
  
```  
// Create a client with Username endpoint configuration  
CalculatorClient client1 = new CalculatorClient("Username");  
  
client1.ClientCredentials.UserName.UserName = "test1";  
client1.ClientCredentials.UserName.Password = "1tset";  
  
try  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client1.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
    ...  
}  
catch (Exception e)  
{  
    Console.WriteLine("Call failed : {0}", e.Message);  
}  
  
client1.Close();  
```  
  
 인증서 기반 끝점의 경우 클라이언트 구현에서 사용할 클라이언트 인증서를 설정합니다.  
  
```  
// Create a client with Certificate endpoint configuration  
CalculatorClient client2 = new CalculatorClient("Certificate");  
  
client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");  
  
try  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client2.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
    ...  
}  
catch (Exception e)  
{  
    Console.WriteLine("Call failed : {0}", e.Message);  
}  
  
client2.Close();  
```  
  
 이 샘플에서는 사용자 지정 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 사용하여 사용자 이름 및 암호의 유효성을 검사합니다. 이 샘플에서는 `MyCustomUserNamePasswordValidator`에서 파생된 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 구현합니다. 자세한 내용은 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에 대한 설명서를 참조하십시오. <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>와의 통합을 보여 주기 위해 이 사용자 지정 유효성 검사기 샘플에서는 다음 코드에 표시된 것과 같이 사용자 이름과 암호가 일치되는 사용자 이름/암호 쌍을 받도록 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 구현합니다.  
  
```  
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator  
{  
  // This method validates users. It allows in two users,   
  // test1 and test2 with passwords 1tset and 2tset respectively.  
  // This code is for illustration purposes only and   
  // MUST NOT be used in a production environment because it   
  // is NOT secure.      
  public override void Validate(string userName, string password)  
  {  
    if (null == userName || null == password)  
    {  
      throw new ArgumentNullException();  
    }  
  
    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))  
    {  
      throw new SecurityTokenException("Unknown Username or Password");  
    }  
  }  
}  
```  
  
 서비스 코드에 유효성 검사기를 구현하고 나면 사용할 유효성 검사기 인스턴스에 대한 정보를 서비스 호스트에 알려야 합니다. 이것은 다음 코드를 사용하여 실행됩니다.  
  
```  
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;  
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();  
```  
  
 또는 구성에서도 같은 작업을 수행할 수 있습니다.  
  
```xml  
<behavior ...>  
    <serviceCredentials>  
      <!--   
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.    
      -->  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />  
    ...  
    </serviceCredentials>  
</behavior>  
```  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 액세스 검사 수행에 사용할 수 있는 풍부한 클레임 기반 모델을 제공합니다. <xref:System.ServiceModel.ServiceAuthorizationManager> 개체는 액세스 검사를 수행하는 데 사용되며 클라이언트에 연결된 클레임이 서비스 메서드에 액세스하는 데 필요한 요구 사항을 충족시키는지 여부를 확인합니다.  
  
 이 샘플에서는 데모용으로 <xref:System.ServiceModel.ServiceAuthorizationManager> 메서드를 구현하여 호출이 허용되는 작업의 동작 URI가 값으로 지정된 http://example.com/claims/allowedoperation 형식의 클레임을 기반으로 사용자의 메서드에 대한 액세스를 허용하는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>의 구현을 보여 줍니다.  
  
```  
public class MyServiceAuthorizationManager : ServiceAuthorizationManager  
{  
  protected override bool CheckAccessCore(OperationContext operationContext)  
  {                  
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;  
    Console.WriteLine("action: {0}", action);  
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)  
    {  
      if ( cs.Issuer == ClaimSet.System )  
      {  
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))  
        {  
          Console.WriteLine("resource: {0}", c.Resource.ToString());  
          if (action == c.Resource.ToString())  
            return true;  
        }  
      }  
    }  
    return false;                   
  }  
}  
```  
  
 사용자 지정 <xref:System.ServiceModel.ServiceAuthorizationManager>가 구현되면 사용할 <xref:System.ServiceModel.ServiceAuthorizationManager>에 대한 정보를 서비스 호스트에 알려야 합니다. 이 작업은 다음 코드에 표시된 것과 같이 수행됩니다.  
  
```xml  
<behavior ...>  
    ...  
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
        ...  
    </serviceAuthorization>  
</behavior>  
```  
  
 구현할 중요한 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 메서드는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드입니다.  
  
```  
public class MyAuthorizationPolicy : IAuthorizationPolicy  
{  
    string id;  
  
    public MyAuthorizationPolicy()  
    {  
    id =  Guid.NewGuid().ToString();  
    }  
  
    public bool Evaluate(EvaluationContext evaluationContext,   
                                            ref object state)  
    {  
        bool bRet = false;  
        CustomAuthState customstate = null;  
  
        if (state == null)  
        {  
            customstate = new CustomAuthState();  
            state = customstate;  
        }  
        else  
            customstate = (CustomAuthState)state;  
        Console.WriteLine("In Evaluate");  
        if (!customstate.ClaimsAdded)  
        {  
           IList<Claim> claims = new List<Claim>();  
  
           foreach (ClaimSet cs in evaluationContext.ClaimSets)  
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,   
                                         Rights.PossessProperty))  
                  foreach (string s in   
                        GetAllowedOpList(c.Resource.ToString()))  
                  {  
                       claims.Add(new  
               Claim("http://example.com/claims/allowedoperation",   
                                    s, Rights.PossessProperty));  
                            Console.WriteLine("Claim added {0}", s);  
                      }  
                   evaluationContext.AddClaimSet(this,   
                           new DefaultClaimSet(this.Issuer,claims));  
                   customstate.ClaimsAdded = true;  
                   bRet = true;  
                }  
         else  
         {  
              bRet = true;  
         }  
         return bRet;  
     }  
...  
}  
```  
  
 이전 코드에서는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드가 처리에 영향을 주는 새 클레임이 추가되지 않았는지 확인하고 특정 클레임을 추가하는 방법을 보여 줍니다. 허용되는 클레임은 사용자가 수행할 수 있는 작업의 특정 목록을 반환하도록 구현된 `GetAllowedOpList` 메서드를 통해 가져옵니다. 권한 부여 정책에서는 특정 작업에 액세스하기 위한 클레임을 추가합니다. 이 값은 나중에 <xref:System.ServiceModel.ServiceAuthorizationManager>에서 액세스 확인 여부를 확인하는 데 사용됩니다.  
  
 사용자 지정 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>가 구현되면 사용할 권한 부여 정책에 대한 정보를 서비스 호스트에 알려야 합니다.  
  
```xml  
<serviceAuthorization ...>  
       <authorizationPolicies>   
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />  
       </authorizationPolicies>   
</serviceAuthorization>  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트에서는 Add, Subtract 및 Multiple 메서드를 성공적으로 호출하며 Divide 메서드를 호출하려 하면 "액세스가 거부되었습니다." 메시지가 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
## <a name="setup-batch-file"></a>설치 배치 파일  
 이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.  
  
 다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.  
  
-   서버 인증서 만들기  
  
     Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다. %SERVER_NAME% 변수는 서버 이름을 지정합니다. 이 변수를 변경하여 고유의 서버 이름을 지정합니다. 기본값은 localhost입니다.  
  
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
  
     Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다. 이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 시스템에서 암시적으로 신뢰하지는 않기 때문에 필요합니다. Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   클라이언트 인증서 만들기  
  
     Setup.bat 배치 파일에서 다음 줄은 사용할 클라이언트 인증서를 만듭니다. %USER_NAME% 변수는 서버 이름을 지정합니다. 이 값은 `IAuthorizationPolicy`에서 찾는 이름이기 때문에 "test1"으로 설정됩니다. %USER_NAME% 값을 변경하는 경우 `IAuthorizationPolicy.Evaluate` 메서드에서 해당 값을 변경해야 합니다.  
  
     인증서는 CurrentUser 저장소 위치에 있는 My (Personal) 저장소에 저장됩니다.  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치  
  
     Setup.bat 배치 파일에서 다음 줄은 신뢰할 수 있는 사용자 저장소로 클라이언트 인증서를 복사합니다. 이 단계는 Makecert.exe에서 생성한 인증서를 서버 시스템에서 암시적으로 신뢰하지는 않기 때문에 필요합니다. Microsoft에서 발급한 인증서와 같이 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 서버 인증서 저장소를 클라이언트 인증서로 채우는 이 단계는 필요하지 않습니다.  
  
    ```  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-and-build-the-sample"></a>샘플을 설치하고 빌드하려면  
  
1.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
2.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 다음 지침을 사용합니다.  
  
> [!NOTE]
>  Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트 창을 열고 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
    > [!NOTE]
    >  Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다. [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.  
  
2.  관리자 권한으로 연 Visual Studio 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
3.  service\bin에서 Service.exe를 실행합니다.  
  
4.  \client\bin에서 Client.exe를 실행합니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
5.  클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
#### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스 컴퓨터에 디렉터리를 만듭니다.  
  
2.  서비스 프로그램 파일을 \service\bin에서 서비스 컴퓨터에 있는 디렉터리에 복사합니다. Setup.bat, Cleanup.bat, GetComputerName.vbs 및 ImportClientCert.bat 파일도 서비스 컴퓨터에 복사합니다.  
  
3.  클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.  
  
4.  클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다. Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.  
  
5.  서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다. 실행 `setup.bat` 와 `service` 인수 서비스 인증서를 만듭니다 computerand 내보내기의 정규화 된 도메인 이름 서비스 인증서를 Service.cer 이라는 파일로 내보내집니다.  
  
6.  새 인증서 이름을 반영 하도록 Service.exe.config 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 컴퓨터의 정규화 된 도메인 이름과 같습니다. 컴퓨터 이름을 변경할 수도 \<서비스 > /\<baseAddresses > localhost에서 서비스 컴퓨터의 정규화 된 이름으로 요소입니다.  
  
7.  서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
8.  클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat client`를 실행합니다. 실행 `setup.bat` 와 `client` 인수 test1 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.  
  
9. 클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다. 이렇게 하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.  
  
10. 클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.  
  
11. 클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
12. 서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportClientCert.bat를 실행합니다. 이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.  
  
13. 서버 컴퓨터의 명령 프롬프트 창에서 Service.exe를 실행합니다.  
  
14. 클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다. 클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
#### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
1.  샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다. 그러면 인증서 저장소에서 서버 및 클라이언트 인증서가 제거됩니다.  
  
> [!NOTE]
>  다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다. 다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다. 이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).  
  
## <a name="see-also"></a>참고 항목
