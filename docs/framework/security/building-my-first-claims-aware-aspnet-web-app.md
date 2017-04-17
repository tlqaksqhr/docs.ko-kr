---
title: "내 첫 번째 클레임 인식 ASP.NET 웹 응용 프로그램 구축 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# 내 첫 번째 클레임 인식 ASP.NET 웹 응용 프로그램 구축
## 적용 대상  
  
-   WIF\(Windows Identity Foundation\)  
  
-   ASP.NET  
  
 이 항목에서는 WIF를 사용하여 클레임 인식 ASP.NET 웹 응용 프로그램을 구축하는 시나리오에 대해 간략하게 설명합니다.  일반적으로 클레임 인식 응용 프로그램 시나리오에는 응용 프로그램, 최종 사용자 및 STS\(보안 토큰 서비스\)와 같은 세 가지 참가 요소가 있습니다.  다음 그림은 이 시나리오를 보여줍니다.  
  
 ![WIF 기본 웹 앱](../../../docs/framework/security/media/wifbasicwebapp.png "WIFBasicWebApp")  
  
1.  클레임 인식 응용 프로그램은 WIF를 사용하여 인증되지 않은 요청을 식별하고 STS로 리디렉션합니다.  
  
2.  최종 사용자가 STS에 자격 증명을 제공하고, 성공적으로 인증되면 STS에서 해당 사용자에게 토큰을 발급합니다.  
  
3.  사용자가 요청에서 STS 발급 토큰을 사용해 STS에서 클레임 인식 응용 프로그램으로 리디렉션됩니다.  
  
4.  클레임 인식 응용 프로그램은 STS 및 발급되는 토큰을 신뢰하도록 구성됩니다.  클레임 인식 응용 프로그램은 WIF를 사용하여 토큰의 유효성을 검사하고 구문 분석합니다.  개발자가 인증 구현과 같이 응용 프로그램의 요구에 맞는 적절한 WIF API 및 형식\(예: **ClaimsPrincpal**\)을 사용합니다.  
  
 .NET 4.5부터 WIF가 .NET Framework 패키지의 일부로 제공됩니다.  WIF 클래스를 프레임워크 자체에서 직접 사용할 수 있도록 하면 .NET 플랫폼에 클레임 기반 ID를 더욱 심층적으로 통합하여 클레임을 더욱 쉽게 사용하도록 할 수 있습니다.  WIF 4.5를 사용하면 클레임 인식 웹 응용 프로그램 개발을 시작하기 위해 대역 외 구성 요소를 설치할 필요가 없습니다.  현재 WIF 클래스가 다양한 어셈블리에 분산되어 있으며, 주요 클래스는 System.Security.Claims, System.IdentityModel 및 System.IdentityModel.Services입니다.  
  
 STS는 성공적으로 인증되면 토큰을 발급하는 서비스입니다.  Microsoft는 다음과 같은 두 가지 업계 표준 STS를 제공합니다.  
  
-   [ADFS\(Active Directory Federation Services\) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516)\(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247516\)  
  
-   [Microsoft Azure ACS\(액세스 제어 서비스\)](http://go.microsoft.com/fwlink/?LinkID=247517)\(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247517\).  
  
 ADFS 2.0은 Windows Server R2에 속하며, 온\-프레미스 시나리오의 STS로 사용할 수 있습니다.  ACS는 Microsoft Azure 플랫폼의 일부로 제공되는 클라우드 서비스입니다.  테스트 또는 교육용으로 클레임 인식 응용 프로그램을 작성하기 위해 다른 STS를 사용할 수도 있습니다.  예를 들어, 온라인에서 무료로 제공되는 [Visual Studio용 ID 및 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849)\(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=245849\)에 속하는 로컬 개발 STS를 사용할 수 있습니다.  
  
 WIF를 사용하여 첫 번째 클레임 인식 ASP.NET 응용 프로그램을 작성하려면 다음 중 하나의 지침을 따르십시오.  
  
-   [방법: WIF를 사용하여 클레임 인식 ASP.NET MVC 웹 응용 프로그램 빌드](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [방법: 양식 기반 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## 참고 항목  
 [WIF 시작](../../../docs/framework/security/getting-started-with-wif.md)