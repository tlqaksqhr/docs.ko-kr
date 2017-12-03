---
title: "WCF Data Services에 보안 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- securing application [WCF Data Services]
- WCF Data Services, security
ms.assetid: 99fc2baa-a040-4549-bc4d-f683d60298af
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93638fc9287b3b44ec066c51b9599d991f9b046d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="securing-wcf-data-services"></a>WCF Data Services에 보안 설정
이 항목에서는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]을 지원하는 서비스에 액세스하는 응용 프로그램 및 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]의 개발, 배포 및 실행과 관련된 보안 고려 사항에 대해 설명합니다. 또한 보안 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램을 만들기 위한 권장 사항도 따라야 합니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 기반 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스의 보안을 유지하는 방법을 계획할 때는 보안 주체의 ID를 검색하고 확인하는 프로세스인 인증과 인증된 보안 주체에서 요청된 리소스에 액세스할 수 있는지 여부를 확인하는 프로세스인 권한 부여를 처리해야 합니다. SSL을 사용하여 메시지를 암호화할지 여부도 고려해야 합니다.  
  
## <a name="authenticating-client-requests"></a>클라이언트 요청 인증  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 자체 인증을 구현하지 않고 데이터 서비스 호스트의 인증 프로비전을 사용합니다. 즉, 서비스는 서비스에서 받는 요청이 이미 네트워크 호스트에 의해 인증되었고 호스트가 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 제공하는 인터페이스를 통해 요청에 대한 보안 주체를 올바르게 식별했다고 가정합니다. 이러한 인증 옵션과 접근 방식에 자세히 설명 되어 [OData 및 인증 시리즈](http://go.microsoft.com/fwlink/?LinkId=200381)합니다.  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>WCF Data Services의 인증 옵션  
 다음 표에서는 WCF Data Services에 대한 요청을 인증하는 데 사용할 수 있는 몇 가지 인증 메커니즘을 보여 줍니다.  
  
|인증 옵션|설명|  
|----------------------------|-----------------|  
|익명 인증|HTTP 익명 인증을 사용하도록 설정되어 있는 경우 임의의 보안 주체에서 데이터 서비스에 연결할 수 있습니다. 익명 액세스를 위해서 자격 증명이 필요하지는 않습니다. 누구나 데이터 서비스에 액세스할 수 있도록 하려는 경우에만 이 옵션을 사용하세요.|  
|기본 인증 및 다이제스트 인증|인증을 위해서는 사용자 이름 및 암호로 구성된 자격 증명이 필요합니다. Windows 클라이언트가 아닌 클라이언트의 인증을 지원합니다. **보안 정보:** 기본 인증 자격 증명 (사용자 이름 및 암호) 보안 되지 않은 상태로 전송 되 고, 노출 될 수 있습니다. 다이제스트 인증은 제공된 자격 증명을 기반으로 한 해시를 보내므로 기본 인증보다 안전합니다. 두 인증 모두 메시지 가로채기(man in the middle) 공격을 받기 쉽습니다. 이 인증 방법을 사용할 때는 SSL(Secure Sockets Layer)을 사용하여 클라이언트와 데이터 서비스 간 통신을 암호화하는 것이 좋습니다. <br /><br /> Microsoft IIS(인터넷 정보 서비스)는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램의 HTTP 요청에 대해 기본 인증 및 다이제스트 인증 구현을 모두 제공합니다. 이 Windows 인증 공급자 구현을 통해 .NET Framework 클라이언트 응용 프로그램에서 요청의 HTTP 헤더에 있는 자격 증명을 데이터 서비스에 제공하여 Windows 사용자의 인증을 원활하게 협상할 수 있습니다. 자세한 내용은 참조 [다이제스트 인증 기술 참조](http://go.microsoft.com/fwlink/?LinkId=200408)합니다.<br /><br /> 데이터 서비스에서 Windows 자격 증명이 아닌 사용자 지정 인증 서비스를 기반으로 하는 기본 인증을 사용하도록 하려는 경우에는 인증에 대한 사용자 지정 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] HTTP 모듈을 구현해야 합니다.<br /><br /> [!INCLUDE[crexample](../../../../includes/crexample-md.md)]와 사용자 지정 기본 인증 체계를 사용 하는 방법 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], 게시물을 참조 [기본 사용자 지정 인증](http://go.microsoft.com/fwlink/?LinkID=200388) 에 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 및 인증 시리즈 합니다.|  
|Windows 인증|Windows 기반 자격 증명은 NTLM 또는 Kerberos를 사용하여 교환됩니다. 이 메커니즘은 기본 인증 또는 다이제스트 인증보다 안전하지만 클라이언트가 Windows 기반 응용 프로그램이어야 합니다. 또한 IIS에서는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램의 HTTP 요청에 대한 Windows 인증 구현을 제공합니다. 자세한 내용은 참조 [ASP.NET 폼 인증 개요](http://msdn.microsoft.com/library/099c1587-6934-476e-ac95-28f534bc9708)합니다.<br /><br /> [!INCLUDE[crexample](../../../../includes/crexample-md.md)]와 함께 Windows 인증을 사용 하는 방법 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], 게시물을 참조 [Windows 인증](http://go.microsoft.com/fwlink/?LinkID=200384) 에 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 및 인증 시리즈 합니다.|  
|[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 폼 인증|폼 인증을 사용하면 직접 작성한 코드로 사용자를 인증한 다음 인증 토큰을 쿠키나 페이지 URL에 유지할 수 있습니다. 만든 로그인 폼을 사용하여 사용자의 사용자 이름과 암호를 인증할 수 있습니다. 인증되지 않은 요청은 로그인 페이지로 리디렉션되고 여기서 사용자는 자격 증명을 제공한 후 폼을 제출합니다. 응용 프로그램에서 요청을 인증하는 경우 시스템에서는 이후 요청에 사용할 ID를 다시 설정하기 위한 키가 포함된 티켓을 발급합니다. 자세한 내용은 참조 [폼 인증 공급자](http://msdn.microsoft.com/library/77e21ba2-bad1-4967-a8ec-74942dea7e47)합니다. **보안 정보:** 기본적으로 폼 인증 티켓을 포함 하는 쿠키 보안이 설정 되지 않은에서 폼 인증을 사용 하는 경우는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램입니다. SSL을 사용하여 인증 티켓과 초기 로그인 자격 증명을 모두 보호하는 것이 좋습니다. <br /><br /> [!INCLUDE[crexample](../../../../includes/crexample-md.md)]폼으로 인증을 사용 하는 방법 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], 게시물을 참조 [폼 인증](http://go.microsoft.com/fwlink/?LinkID=200389) 에 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 및 인증 시리즈 합니다.|  
|클레임 기반 인증|클레임 기반 인증 일 경우 데이터 서비스에 의존 하 여 사용자를 인증 하기 위해 신뢰할 수 있는 "타사" id 공급자 서비스입니다. ID 공급자는 데이터 서비스 리소스에 대한 액세스를 요청하는 사용자를 긍정적으로 인증하고 요청된 리소스에 대한 액세스 권한을 부여하는 토큰을 발급합니다. 그런 다음 이 토큰이 데이터 서비스에 제공되며 이후에는 이 토큰을 통해 액세스 토큰을 발급한 ID 서비스와의 트러스트 관계를 기반으로 사용자에게 액세스 권한이 부여됩니다.<br /><br /> 클레임 기반 인증 공급자를 사용하여 얻을 수 있는 이점은 이 공급자를 사용하여 트러스트 도메인 간에 다양한 종류의 클라이언트를 인증할 수 있다는 사실입니다. 이러한 타사 공급자를 사용하면 데이터 서비스에서 사용자를 유지 관리하고 인증하기 위한 요구 사항을 줄일 수 있습니다. OAuth 2.0은 Microsoft Azure AppFabric 액세스 제어에서 페더레이션 권한 부여를 위해 서비스로 지원하는 클레임 기반 인증 프로토콜입니다. 이 프로토콜은 REST 기반 서비스를 지원합니다. [!INCLUDE[crexample](../../../../includes/crexample-md.md)]OAuth 2.0을 사용 하는 방법 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], 게시물을 참조 [OData 및 OAuth](http://go.microsoft.com/fwlink/?LinkId=200514) 에 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 및 인증 시리즈 합니다.|  
  
<a name="clientAuthentication"></a>   
### <a name="authentication-in-the-client-library"></a>클라이언트 라이브러리의 인증  
 기본적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스에 요청할 때 자격 증명을 제공하지 않습니다. 데이터 서비스에서 사용자를 인증하는 데 로그인 자격 증명이 필요한 경우, 다음 예와 같이 <xref:System.Net.NetworkCredential>의 <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> 속성에서 액세스하는 <xref:System.Data.Services.Client.DataServiceContext>에 이러한 자격 증명이 제공될 수 있습니다.  
  
```csharp  
// Set the client authentication credentials.  
context.Credentials =  
    new NetworkCredential(userName, password, domain);  
```  
  
```vb  
' Set the client authentication credentials.  
context.Credentials = _  
    New NetworkCredential(userName, password, domain)  
```  
  
 자세한 내용은 참조 [하는 방법: 데이터 서비스 요청에 대 한 클라이언트 자격 증명 지정](../../../../docs/framework/data/wcf/specify-client-creds-for-a-data-service-request-wcf.md)합니다.  
  
 데이터 서비스에 클레임 기반 토큰 또는 쿠키와 같은 <xref:System.Net.NetworkCredential> 개체를 사용하여 지정할 수 없는 로그인 자격 증명이 필요한 경우에는 HTTP 요청에 헤더(일반적으로 `Authorization` 및 `Cookie` 헤더)를 수동으로 설정해야 합니다. 이러한 종류의 인증 시나리오에 대 한 자세한 내용은 게시물을 참조 하십시오. [OData 및 인증: 클라이언트 쪽 후크](http://go.microsoft.com/fwlink/?LinkID=200385)합니다. 요청 메시지의 HTTP 헤더를 설정 하는 방법의 예제를 보려면 [하는 방법: 클라이언트 요청의 헤더 설정](../../../../docs/framework/data/wcf/how-to-set-headers-in-the-client-request-wcf-data-services.md)합니다.  
  
## <a name="impersonation"></a>가장  
 일반적으로 데이터 서비스는 데이터 서비스를 호스트하는 작업자 프로세스의 자격 증명을 사용하여 서버 또는 데이터베이스 파일과 같은 필요한 리소스에 액세스합니다. 가장을 사용하는 경우 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램은 요청하는 사용자의 Windows ID(사용자 계정)를 사용하여 실행될 수 있습니다. 가장은 IIS를 통해 사용자를 인증하는 응용 프로그램에서 주로 사용되며, 이 원칙의 자격 증명은 필요한 리소스에 액세스하는 데 사용됩니다. 자세한 내용은 참조 [ASP.NET 가장](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d)합니다.  
  
## <a name="configuring-data-service-authorization"></a>데이터 서비스 권한 부여 구성  
 권한 부여는 이전에 성공적으로 이루어진 인증을 기반으로 식별된 프로세스 또는 원칙에 응용 프로그램 리소스에 대한 액세스 권한을 부여하는 과정입니다. 일반적으로 클라이언트 응용 프로그램에 필요한 작업을 수행하기에 충분한 권한만 데이터 서비스 사용자에게 부여해야 합니다.  
  
### <a name="restrict-access-to-data-service-resources"></a>데이터 서비스 리소스에 대한 액세스 제한  
 기본적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 데이터 서비스에 액세스할 수 있는 사용자에게 데이터 서비스 리소스(엔터티 집합 및 서비스 작업)에 대한 일반적인 읽기 및 쓰기 액세스 권한을 부여할 수 있습니다. 읽기 및 쓰기 액세스 권한을 정의하는 규칙은 데이터 서비스에서 노출하는 각 엔터티 집합뿐 아니라 서비스 작업에 대해 개별적으로 정의할 수 있습니다. 읽기 및 쓰기 액세스 권한은 클라이언트 응용 프로그램에 필요한 리소스로만 제한하는 것이 좋습니다. 자세한 내용은 참조 [최소 리소스 액세스 요구 사항](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md#accessRequirements)합니다.  
  
### <a name="implement-role-based-interceptors"></a>역할 기반 인터셉터 구현  
 인터셉터를 사용하면 데이터 서비스 리소스에 대한 요청이 데이터 서비스에 의해 실행되기 전에 이 요청을 가로챌 수 있습니다. 자세한 내용은 참조 [인터셉터](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)합니다. 인터셉터를 사용하면 요청을 하는 인증된 사용자를 기준으로 권한 부여 결정을 수행할 수 있습니다. [!INCLUDE[crexample](../../../../includes/crexample-md.md)]인증 된 사용자 id를 기반으로 데이터 서비스 리소스에 대 한 액세스를 제한 하는 방법을 참조 하십시오. [하는 방법: 데이터 서비스 메시지 가로채기](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)합니다.  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>지속형 데이터 저장소 및 로컬 리소스에 대한 액세스 제한  
 지속형 저장소에 액세스하는 데 사용되는 계정에는 데이터베이스 또는 파일 시스템에서 데이터 서비스의 요구 사항을 지원하기에 충분한 권한만 부여해야 합니다. 익명 인증을 사용하는 경우 이 계정은 호스팅 응용 프로그램을 실행하는 데 사용되는 계정입니다. 자세한 내용은 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하십시오. 가장을 사용하는 경우에는 인증된 사용자에게 일반적으로 Windows 그룹의 일부인 이러한 리소스에 대한 액세스 권한을 부여해야 합니다.  
  
## <a name="other-security-considerations"></a>기타 보안 고려 사항  
  
### <a name="secure-the-data-in-the-payload"></a>페이로드 데이터 보안 설정  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]는 HTTP 프로토콜을 기반으로 합니다. HTTP 메시지의 헤더에는 데이터 서비스에서 구현하는 인증에 따라 중요한 사용자 자격 증명이 포함될 수 있습니다. 메시지 본문에는 보호해야 하는 중요한 고객 데이터가 포함될 수도 있습니다. 이 두 경우 모두 SSL을 사용하여 네트워크에서 이 정보를 보호하는 것이 좋습니다.  
  
### <a name="ignored-message-headers-and-cookies"></a>무시되는 메시지 헤더 및 쿠키  
 콘텐츠 형식 및 리소스 위치를 선언하는 헤더를 제외한 HTTP 요청 헤더는 무시되며 데이터 서비스에서 설정되지 않습니다.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 폼 인증에서와 같이 쿠키를 인증 체계의 일부로 사용할 수 있습니다. 그러나 들어오는 요청에 설정된 HTTP 쿠키는 모두 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 무시됩니다. 데이터 서비스의 호스트가 쿠키를 처리할 수 있지만 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 런타임에서는 쿠키를 분석하거나 반환하지 않습니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리에서도 응답에 보내지는 쿠키를 처리하지 않습니다.  
  
### <a name="custom-hosting-requirements"></a>사용자 지정 호스팅 요구 사항  
 기본적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 IIS에서 호스트되는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램으로 만들어집니다. 따라서 데이터 서비스에서 이 플랫폼의 보안 동작을 활용할 수 있습니다. 사용자 지정 호스트에서 호스트되는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 정의할 수 있습니다. 자세한 내용은 참조 [데이터 서비스 호스팅](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)합니다. 데이터 서비스를 호스트하는 구성 요소 및 플랫폼에서는 다음 보안 동작을 통해 데이터 서비스에 대한 공격을 방지해야 합니다.  
  
-   가능한 모든 작업에 대한 데이터 서비스 요청에서 수락되는 URI의 길이를 제한합니다.  
  
-   들어오고 나가는 HTTP 메시지의 크기를 제한합니다.  
  
-   주어진 시간에 처리되지 않는 요청의 총 개수를 제한합니다.  
  
-   HTTP 헤더와 헤더 값의 크기를 제한하고 헤더 데이터에 대한 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 액세스 권한을 제공합니다.  
  
-   TCP SYN 및 메시지 재생 공격과 같은 알려진 공격을 검색하여 대처합니다.  
  
### <a name="values-are-not-further-encoded"></a>값이 더 이상 인코딩되지 않음  
 데이터 서비스에 보내지는 속성 값은 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 런타임에서 더 이상 인코딩되지 않습니다. 예를 들어, 엔터티의 문자열 속성에 서식이 지정된 HTML 콘텐츠가 포함되어 있는 경우 데이터 서비스에서 태그를 HTML로 인코딩하지 않습니다. 또한 데이터 서비스에서 응답의 속성 값을 더 이상 인코딩하지 않습니다. 그리고 클라이언트 라이브러리에서도 추가 인코딩을 수행하지 않습니다.  
  
### <a name="considerations-for-client-applications"></a>클라이언트 응용 프로그램에 대한 고려 사항  
 다음 보안 고려 사항은 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트를 사용하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스에 액세스하는 응용 프로그램에 적용됩니다.  
  
-   클라이언트 라이브러리는 데이터 서비스에 액세스하는 데 사용되는 프로토콜에서 적절한 수준의 보안을 제공한다고 가정합니다.  
  
-   클라이언트 라이브러리에서는 기본 플랫폼 제공 전송 스택의 시간 제한 및 구문 분석 옵션에 대해 모든 기본값을 사용합니다.  
  
-   클라이언트 라이브러리는 응용 프로그램 구성 파일에서 설정을 읽지 않습니다.  
  
-   클라이언트 라이브러리는 도메인 간 액세스 메커니즘을 구현하지 않고 기본 HTTP 스택에서 제공하는 메커니즘을 사용합니다.  
  
-   클라이언트 라이브러리는 사용자 인터페이스 요소를 포함하고 있지 않으며 보내거나 받는 데이터를 표시하거나 렌더링하지 않습니다.  
  
-   클라이언트 응용 프로그램에서는 신뢰할 수 없는 서비스에서 수락하는 데이터뿐 아니라 사용자 입력의 유효성을 항상 검사하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
