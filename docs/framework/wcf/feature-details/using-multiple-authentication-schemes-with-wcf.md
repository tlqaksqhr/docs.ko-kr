---
title: "WCF와 함께 여러 인증 스키마 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf74b38c15cf8dc68218c39246c8999c4ec44493
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>WCF와 함께 여러 인증 스키마 사용
이제 WCF를 사용하여 단일 끝점에 여러 인증 체계를 지정할 수 있습니다. 또한 웹 호스팅 서비스가 IIS에서 직접 인증 설정을 상속할 수 있습니다. 자체 호스팅 서비스는 사용할 수 있는 인증 체계를 지정할 수 있습니다. IIS에서 인증 설정을 설정 하는 방법에 대 한 자세한 내용은 참조 [IIS 인증](http://go.microsoft.com/fwlink/?LinkId=232458)  
  
## <a name="iis-hosted-services"></a>IIS에서 호스트되는 서비스  
 IIS에서 호스트되는 서비스의 경우 IIS에서 사용할 인증 체계를 설정합니다. 그런 다음 서비스의 web.config 파일 바인딩 구성에서 clientCredential 형식을 "InheritedFromHost"로 지정 다음 XML 조각에 나와:  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 ServiceAuthenticationBehavior를 사용 하 여 서비스에 사용할 인증 체계의 하위 집합 에서만 되도록 지정할 수 있습니다 또는 \<a g e r > 요소입니다. 이를 코드로 구성할 때는 다음 코드 조각에서와 같이 ServiceAuthenticationBehavior를 사용합니다.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 이 구성 파일에서 구성할 때 사용 하 여는 \<a g e r > 요소는 다음 XML 조각에 나와 있는 것 처럼 합니다.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 그러면 IIS에서 선택된 항목에 따라 여기에 나열된 인증 체계의 하위 집합만 서비스 끝점에 적용되는 것으로 간주됩니다. 즉, 개발자는 serviceAuthenticationManager 목록에서 기본 인증을 생략하여 목록에서 기본 인증을 제외할 수 있으며, IIS에서 사용할 수 있는 인증의 경우에도 서비스 끝점에 적용되지 않습니다.  
  
## <a name="self-hosted-services"></a>자체 호스팅 서비스  
 자체 호스팅 서비스는 설정을 상속할 IIS가 없으므로 약간 다르게 구성됩니다. 사용 하는 여기에서 \<a g e r > 요소 또는 ServiceAuthenticationBehavior은 상속 하는 인증 설정을 지정 합니다. 코드는 다음과 비슷합니다.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 구성은 다음과 비슷합니다.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 그런 다음, 아래 XML 조각에 나와 있는 것처럼 바인딩 설정에 InheritFromHost를 지정할 수 있습니다.  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 또는 다음 구성 조각에서와 같이 HTTP 전송 바인딩 요소에 인증 체계를 설정하여 사용자 지정 바인딩에 인증 체계를 지정할 수 있습니다.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>참고 항목  
 [바인딩 및 보안](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [끝점: 주소, 바인딩 및 계약](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [시스템 제공 바인딩 구성](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [사용자 지정 바인딩 사용 하는 보안 기능](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [바인딩](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [바인딩](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)
