---
title: "클라이언트 응용 프로그램 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 설정, 클라이언트 응용 프로그램 서비스"
  - "ASP.NET 서비스, 클라이언트 응용 프로그램 서비스"
  - "인증[ASP.NET], 클라이언트 응용 프로그램 서비스"
  - "클라이언트 응용 프로그램 서비스"
  - "클라이언트 응용 프로그램 서비스, 클라이언트 응용 프로그램 서비스 정보"
  - "클라이언트 응용 프로그램, ASP.NET 서비스"
  - "자격 증명[.NET Framework]"
  - "로그인[클라이언트 응용 프로그램 서비스]"
  - "프로필[ASP.NET], 클라이언트 응용 프로그램 서비스"
  - "역할 기반 보안[.NET Framework], 클라이언트 응용 프로그램 서비스"
  - "역할[.NET Framework], 클라이언트 응용 프로그램 서비스"
  - "정보 및 기능 공유[클라이언트 응용 프로그램 서비스]"
  - "웹 설정[클라이언트 응용 프로그램 서비스]"
  - "Windows 기반 응용 프로그램, 클라이언트 응용 프로그램 서비스"
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 클라이언트 응용 프로그램 서비스
클라이언트 응용 프로그램 서비스를 통해 Microsoft ASP.NET 2.0 AJAX 확장에 포함된 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 로그인, 역할 및 프로필 응용 프로그램 서비스를 사용하는 Windows 기반 응용 프로그램을 쉽게 만들 수 있습니다.  이 서비스를 통해 여러 웹 응용 프로그램과 Windows 기반 응용 프로그램이 단일 서버에서 사용자 정보와 사용자 관리 기능을 공유할 수 있습니다.  예를 들어 이 서비스를 통해 다음 작업을 수행할 수 있습니다.  
  
-   사용자를 인증합니다.  인증 서비스를 통해 사용자 ID를 확인할 수 있습니다.  
  
-   인증된 사용자의 역할을 확인합니다.  역할 서비스를 통해 사용자 역할에 따라 응용 프로그램의 사용자 인터페이스를 변경할 수 있습니다.  예를 들어 관리자 역할에 있는 사용자에게 추가 기능을 제공할 수 있습니다.  
  
-   서버에 있는 사용자별 응용 프로그램 설정을 저장하고 액세스합니다.  웹 설정 서비스\(프로필 서비스라고도 함\)를 통해 여러 응용 프로그램과 위치에서 설정을 공유할 수 있습니다.  
  
 클라이언트 응용 프로그램 서비스는 응용 프로그램 구성 파일에서 지정할 수 있는 클라이언트 서비스 공급자를 통해 웹 서비스 확장성 모델을 활용합니다.  이 서비스는 네트워크 연결을 사용할 수 없는 경우 인증, 역할 및 설정 데이터를 위해 로컬 캐시를 사용하는 오프라인 기능을 포함합니다.  
  
 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 응용 프로그램 서비스에 대한 자세한 내용은 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)를 참조하세요.  
  
## 단원 내용  
 [클라이언트 응용 프로그램 서비스 개요](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 클라이언트 응용 프로그램 서비스 공급자를 통해 제공되는 기능을 설명합니다.  
  
 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 디자이너를 사용하여 응용 프로그램 서비스를 사용하도록 설정하고 구성하는 방법을 설명합니다.  또한 App.config 파일에 대한 해당 변경 내용을 설명합니다.  
  
 [방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 응용 프로그램이 클라이언트 인증 서비스 공급자를 사용하도록 구성된 경우 사용자의 유효성을 검사하는 방법을 설명합니다.  
  
 [연습: 클라이언트 응용 프로그램 서비스 사용](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 모든 클라이언트 응용 프로그램 서비스 기능을 단일 응용 프로그램에 결합하는 방법을 설명합니다.  이 연습에서는 완벽한 지침을 제공합니다.  예를 들어 클라이언트 응용 프로그램 서비스를 테스트하는 데 사용할 수 있는 ASP.NET 웹 서비스 응용 프로그램을 만드는 방법에 대한 지침을 포함합니다.  
  
## 참조  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## 참고 항목  
 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)   
 [Using Roles Information with Microsoft Ajax](../Topic/Using%20Roles%20Information%20with%20Microsoft%20Ajax.md)   
 [Using Profile Information with Microsoft Ajax](../Topic/Using%20Profile%20Information%20with%20Microsoft%20Ajax.md)   
 [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md)   
 [Managing Authorization Using Roles](../Topic/Managing%20Authorization%20Using%20Roles.md)   
 [OLD NIB: Managing Application Settings](http://msdn.microsoft.com/ko-kr/7de3c3bd-e0dc-4e75-a1aa-7b0ecfaac4fc)   
 [응용 프로그램 설정 개요](../../../docs/framework/winforms/advanced/application-settings-overview.md)