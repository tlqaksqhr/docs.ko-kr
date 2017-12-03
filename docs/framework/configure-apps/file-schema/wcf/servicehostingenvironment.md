---
title: '&lt;serviceHostingEnvironment&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3951c52a5bc510cc288b1289f2f6cc9c39255db
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicehostingenvironmentgt"></a>&lt;serviceHostingEnvironment&gt;
이 요소는 특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다. 이 요소가 비어 있으면 기본 형식이 사용됩니다. 이 요소는 응용 프로그램이나 컴퓨터 수준 구성 파일에서만 사용할 수 있습니다.  
  
 \<시스템입니다. ServiceModel >  
\<ServiceHostingEnvironment >  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean" 
                           minFreeMemoryPercentageToActivateService="Integer" 
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String" service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String" transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|현재 응용 프로그램에 ASP.NET 호환 모드를 설정했는지 여부를 나타내는 부울 값입니다. 기본값은 `false`입니다.<br /><br /> 이 특성이 `true`로 설정되면 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스에 대한 요청이 ASP.NET HTTP 파이프라인을 통해 전달되며 HTTP가 아닌 프로토콜을 통한 통신이 허용되지 않습니다. 자세한 내용은 참조 [WCF 서비스 및 ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)합니다.|  
|minFreeMemoryPercentageToActivateService|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 활성화하기 전에 시스템에서 사용할 수 있는 최소 메모리를 지정하는 정수입니다. **주의:** 의 web.config 파일에서 부분 신뢰와 함께이 특성을 지정 하는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스 됩니다는 <xref:System.Security.SecurityException> 서비스가 실행 되는 경우.|  
|multipleSiteBindingsEnabled|사이트별로 여러 IIS 바인딩을 사용할 수 있는지 여부를 지정하는 부울 값입니다.<br /><br /> IIS는 가상 디렉터리를 포함하는 가상 응용 프로그램의 컨테이너인 웹 사이트로 구성됩니다. 사이트의 응용 프로그램은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다. 하나의 IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다. 바인딩 프로토콜은 통신이 이루어지는 체계를 정의하며, 바인딩 정보는 사이트에 액세스하는 데 사용되는 정보입니다. 바인딩 프로토콜의 예로는 HTTP가 있으며 바인딩 정보에는 IP 주소, 포트, 호스트 헤더 등이 포함될 수 있습니다.<br /><br /> IIS에서는 사이트별로 여러 개의 IIS 바인딩을 지정할 수 있으므로, 체계별로 여러 개의 기본 주소가 생성됩니다. 하지만 사이트에서 호스트되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스에서는 체계별로 하나의 baseAddress에만 바인딩할 수 있습니다.<br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스에 대해 사이트별로 여러 IIS 바인딩을 사용할 수 있도록 하려면 이 특성을 `true`로 설정합니다. 여러 사이트 바인딩은 HTTP 프로토콜에 대해서만 지원됩니다. 구성 파일의 끝점 주소는 전체 URI여야 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|서비스 호스트에서 사용하는 기본 주소에 대한 접두사 필터를 지정하는 구성 요소 컬렉션입니다.|  
|[\<serviceActivations >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|활성화 설정을 설명하는 구성 섹션입니다.|  
|[\<transportConfigurationTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|특정 전송의 형식을 식별하는 구성 요소의 컬렉션입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|serviceModel|모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 WCF 서비스는 호스트된 응용프로그램 도메인(AppDomain)에서 ASP.NET과 함께 실행됩니다. 동일한 AppDomain에서 WCF와 ASP.NET을 함께 사용할 수 있더라도 WCF 요청은 기본적으로 ASP.NET HTTP 파이프라인에 의해 처리되지 않습니다. 따라서 ASP.NET 응용 프로그램 플랫폼의 여러 요소를 WCF 서비스에 사용할 수 없습니다. 이러한 요소는 다음과 같습니다.  
  
-   ASP.NET 파일/URL 권한 부여  
  
-   ASP.NET 가장  
  
-   쿠키 기반 세션 상태  
  
-   HttpContext.Current  
  
-   사용자 지정 HttpModule을 통한 파이프라인 확장성  
  
 WCF 서비스가 ASP.NET 컨텍스트에서 작동해야 하고 이 서비스가 HTTP를 통해서만 통신하는 경우 WCF의 ASP.NET 호환 모드를 사용할 수 있습니다. 이 모드는 응용 프로그램 수준에서 `aspNetCompatibilityEnabled` 특성이 `true`로 설정되면 사용하도록 설정됩니다. 서비스 구현에서는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> 클래스를 사용하여 호환 모드에서 실행되는 기능을 선언해야 합니다. 호환 모드를 사용하는 경우 다음과 같습니다.  
  
-   ASP.NET 파일/URL 권한 부여가 WCF 인증 전에 적용됩니다. 권한 부여 결정은 요청의 전송 수준 ID에 따라 달라집니다. 메시지 수준의 ID가 무시됩니다.  
  
-   WCF 서비스 작업이 ASP.NET 가장 컨텍스트에서 실행되기 시작합니다. ASP.NET 가장 및 WCF 가장이 모두 특정 서비스에 사용하도록 설정되면 WCF 가장 컨텍스트가 적용됩니다.  
  
-   HttpContext.Current는 WCF 서비스 코드에서 사용할 수 있으며, 서비스에서 HTTP가 아닌 끝점을 노출할 수 없습니다.  
  
-   WCF 요청은 ASP.NET 파이프라인에서 처리됩니다. 들어오는 요청에서 동작하도록 구성된 HttpModule에서는 WCF 요청도 처리할 수 있습니다. 여기에는 사용자 지정 타사 모듈뿐만 아니라 <xref:System.Web.SessionState.SessionStateModule>과 같은 ASP.NET 플랫폼 구성 요소가 포함될 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 샘플에서는 ASP 호환 모드를 사용하도록 설정하는 방법을 보여 줍니다.  
  
## <a name="code"></a>코드  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [호스팅](../../../../../docs/framework/wcf/feature-details/hosting.md)  
 [WCF 서비스 및 ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
