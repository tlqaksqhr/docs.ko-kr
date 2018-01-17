---
title: "클라이언트 응용 프로그램 서비스 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client application services, classes
- client application services, about client application services
ms.assetid: f0a2da13-e282-4fd7-88a1-f9102c9aeab1
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55b4ab154f9f3a9b17274697c30ca826218322ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="client-application-services-overview"></a>클라이언트 응용 프로그램 서비스 개요
클라이언트 응용 프로그램 서비스를 통해 Windows Forms 및 WPF(Windows Presentation Foundation) 응용 프로그램에서 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 로그인, 역할 및 프로필 서비스에 간편하게 액세스할 수 있습니다. [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 응용 프로그램 서비스는 [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)] 및 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)]에 포함된 Microsoft ASP.NET 2.0 AJAX 확장에 들어 있습니다. 이 서비스를 통해 여러 웹 응용 프로그램과 Windows 기반 응용 프로그램이 단일 서버에서 사용자 정보와 사용자 관리 기능을 공유할 수 있습니다.  
  
 클라이언트 응용 프로그램 서비스에는 Windows 기반 응용 프로그램에서 다음 기능을 사용할 수 있도록 웹 서비스 확장성 모델에 연결하는 클라이언트 서비스 공급자가 포함됩니다.  
  
-   단일 클라이언트 구성. [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 디자이너를 사용하거나 프로젝트의 App.config 파일에서 클라이언트 서비스 공급자를 지정하여 로그인, 역할 및 프로필 서비스를 사용하도록 설정하고 구성할 수 있습니다. 자세한 내용은 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하세요.  
  
-   단순한 프로그래밍. 클라이언트 응용 프로그램 서비스를 사용하도록 설정하고 구성하면 기존 [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] 멤버 자격, 역할 및 응용 프로그램 설정 클래스를 통해 간접적으로 서비스 공급자에 액세스할 수 있습니다. 클라이언트 응용 프로그램 서비스를 구현하는 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 클래스에 직접 액세스할 수도 있습니다. 그러나 대부분의 경우 직접 액세스할 필요는 없습니다. 클라이언트 응용 프로그램 서비스 클래스에 대한 자세한 내용은 이 항목의 "클라이언트 응용 프로그램 서비스 클래스" 섹션을 참조하세요.  
  
-   오프라인 지원. Windows 기반 응용 프로그램이 간헐적으로 연결되는 환경에서 작동해야 하는 경우도 많습니다. 응용 프로그램이 온라인 상태인 경우 클라이언트 서비스 공급자는 응용 프로그램이 오프라인 상태일 때 사용하기 위해 서버에서 검색된 값을 캐시합니다.  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 응용 프로그램 설정 디자이너와의 통합. [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 프로젝트에 설정을 추가할 때 클라이언트 설정 서비스 공급자를 통해 액세스할 설정을 지정할 수 있습니다.  
  
 다음 섹션에서는 이러한 기능에 대해 자세히 설명합니다. [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 응용 프로그램 서비스에 대한 자세한 내용은 [ASP.NET 응용 프로그램 서비스 개요](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)를 참조하세요.  
  
## <a name="authentication"></a>인증  
 클라이언트 응용 프로그램 서비스를 사용하면 기존의 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 인증 서비스를 통해 사용자의 유효성을 검사할 수 있습니다. Windows 인증이나 폼 인증을 통해 사용자의 유효성을 검사할 수 있습니다. Windows 인증은 사용자 ID가 사용자가 컴퓨터 또는 도메인에 로그온할 때 운영 체제에서 제공한 ID임을 의미합니다. 일반적으로 Windows 인증은 회사 인트라넷에 배포된 응용 프로그램에서 사용합니다. 폼 인증은 응용 프로그램에 로그인 컨트롤을 포함하고 얻은 자격 증명을 인증 공급자에게 전달해야 함을 의미합니다. 일반적으로 양식 인증은 인터넷에 배포된 응용 프로그램에서 사용합니다.  
  
 사용자의 유효성을 검사하려면 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드를 호출합니다. 이 메서드는 응용 프로그램에 대해 구성된 클라이언트 서비스 공급자에 액세스하고 사용자가 유효한지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 자세한 내용은 [방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)을 참조하세요.  
  
 Windows 인증을 사용하는 경우 빈 문자열이나 `null`을 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드의 매개 변수로 전달해야 합니다. Windows 인증을 사용하는 경우 이 메서드 호출은 항상 `true`를 반환합니다.  
  
 폼 인증을 사용하는 경우 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드는 원격 서비스에서 사용자를 인증했는지 여부를 나타내는 값을 반환합니다. 유효성 검사에 성공하면 인증 쿠키가 로컬 하드 디스크에 저장됩니다. 이 쿠키는 역할 및 설정 서비스에 액세스할 때 유효성 검사를 확인하는 데 사용됩니다.  
  
 폼 인증을 사용하는 경우 사용자 이름 및 암호를 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드에 전달할 수 있습니다. 자격 증명 공급자를 사용하기 위해 빈 문자열이나 `null`을 매개 변수로 전달할 수도 있습니다. 자격 증명 공급자는 응용 프로그램 구성에서 제공하고 지정하는 클래스입니다. 자격 증명 공급자 클래스는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>라는 단일 메서드가 들어 있는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현해야 합니다. 자격 증명 공급자를 사용하면 여러 응용 프로그램에서 단일 로그인 대화 상자를 공유할 수 있습니다. 자세한 내용은 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하세요.  
  
 폼 인증과 함께 자격 증명 공급자를 사용하도록 응용 프로그램을 구성하는 경우 빈 문자열이나 `null`을 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드의 매개 변수로 전달해야 합니다. 그러면 서비스 공급자가 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> 메서드 구현을 호출합니다. 일반적으로 이 메서드는 대화 상자를 표시하고 채워진 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> 개체를 반환하기 위해 구현합니다.  
  
 인증에 대한 자세한 내용은 [ASP.NET 인증](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)을 참조하세요. [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 인증 서비스를 설정하는 방법에 대한 자세한 내용은 [ASP.NET AJAX와 함께 양식 인증 사용](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)을 참조하세요.  
  
## <a name="roles"></a>역할  
 클라이언트 응용 프로그램 서비스를 사용하여 기존의 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 역할 서비스에서 역할 정보를 검색할 수 있습니다. 현재 인증된 사용자가 특정 역할에 있는지 여부를 확인하려면 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성에서 검색된 <xref:System.Security.Principal.IPrincipal> 참조의 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 호출합니다. <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드는 역할 이름을 매개 변수로 받아서 현재 사용자가 지정된 역할에 있는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 사용자가 인증되지 않았거나 지정된 역할에 없는 경우 이 메서드는 `false`를 반환합니다.  
  
 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 역할 서비스를 설정하는 방법에 대한 자세한 내용은 [ASP.NET AJAX와 함께 역할 정보 사용](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)을 참조하세요.  
  
## <a name="settings"></a>설정  
 클라이언트 응용 프로그램 서비스를 사용하여 기존의 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 프로필 서비스에서 사용자 응용 프로그램 설정을 검색할 수 있습니다. 클라이언트 응용 프로그램 서비스 웹 설정 기능은 [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)]에서 제공하는 응용 프로그램 설정 기능과 통합됩니다. 웹 설정을 검색하려면 먼저 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 디자이너의 **설정** 탭을 사용하여 프로젝트에 대한 `Settings` 클래스(C#에서는 `Properties.Settings.Default`로 액세스되고 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 `My.Settings`로 액세스됨)를 생성합니다. **설정** 탭에서 **웹 설정 로드 단추**를 사용하여 웹 설정을 검색하고 생성된 `Settings` 클래스에 추가할 수 있습니다. 모든 인증된 사용자가 사용하거나 모든 익명 사용자가 사용하도록 구성된 웹 설정을 사용할 수 있습니다.  
  
 응용 프로그램 설정에 대한 자세한 내용은 [응용 프로그램 설정 개요](../../../docs/framework/winforms/advanced/application-settings-overview.md)를 참조하세요. [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 설정 클래스를 생성하는 대신 고유한 설정 클래스를 구현하는 방법에 대한 자세한 내용은 [방법: 응용 프로그램 설정 만들](../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)를 참조하세요. [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 프로필 서비스를 설정하는 방법에 대한 자세한 내용은 [ASP.NET AJAX와 함께 프로필 정보 사용](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)을 참조하세요.  
  
## <a name="client-application-services-classes"></a>클라이언트 응용 프로그램 서비스 클래스  
 다음 표에서는 클라이언트 응용 프로그램 서비스 기능을 구현하는 클래스에 대해 설명합니다.  
  
 기본 인증, 역할 및 설정 기능만 사용하는 응용 프로그램은 이러한 클래스에 직접 액세스할 필요가 없습니다. 대신, 이러한 응용 프로그램은 이전 섹션에서 설명한 응용 프로그램 구성 및 API를 사용하여 간접적으로 클라이언트 응용 프로그램 서비스 공급자에 액세스합니다. 사용자 로그아웃 및 오프라인 기능과 같은 추가 기능을 구현하려면 해당 클래스에 직접 액세스합니다.  
  
> [!NOTE]
>  모든 클라이언트 응용 프로그램 서비스 API는 동기입니다. 클라이언트 응용 프로그램 서비스는 비동기 동작을 직접 지원하지 않습니다.  
  
 클라이언트 응용 프로그램 서비스 공급자는 표준 [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] 형식을 구현하거나 확장하지만 이러한 형식에서 정의된 모든 멤버와 기능을 구현하지는 않습니다. 예를 들어 클라이언트 응용 프로그램 서비스 공급자를 사용하여 새 사용자를 만들고 역할 멤버 자격을 관리하기 위한 사용자 관리 응용 프로그램을 구현할 수는 없습니다. 이 기능을 구현하려면 현재 웹 응용 프로그램과 서버 쪽 코드를 사용해야 합니다. 구현되지 않는 멤버를 확인하려면 이 표의 링크를 통해 액세스할 수 있는 참조 설명서를 참조하세요.  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.Web.ClientServices.ClientFormsIdentity>|이 클래스는 폼 인증을 위한 사용자 ID 및 인증 쿠키를 관리합니다.<br /><br /> 이 클래스에 직접 액세스하는 주된 이유는 자동으로 사용자의 유효성을 다시 평가하는 <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> 메서드를 호출하기 위한 것입니다(예: 오프라인 모드에서 온라인 모드로 전환하는 경우).<br /><br /> 폼 인증을 통해 사용자가 인증된 후 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 통해 검색된 <xref:System.Security.Principal.IPrincipal> 참조의 <xref:System.Security.Principal.IPrincipal.Identity%2A> 속성을 통해 이 클래스의 인스턴스를 검색할 수 있습니다.|  
|<xref:System.Web.ClientServices.ClientRolePrincipal>|이 클래스는 사용자 역할을 관리합니다.<br /><br /> 이 클래스에는 간접적으로 액세스할 수 없는 멤버가 없습니다. 그러나 사용자가 인증되고 나면 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 통해 이 클래스의 인스턴스에 액세스할 수 있습니다.|  
|<xref:System.Web.ClientServices.ConnectivityStatus>|이 클래스는 응용 프로그램을 오프라인 모드로 전환하는 데 사용하는 `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> 속성을 제공합니다.|  
|<xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>|이 클래스는 사용자 자격 증명을 나타냅니다.<br /><br /> 이 클래스는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현할 때 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 메서드의 반환 값 형식으로만 사용합니다.|  
|<xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>|이 클래스는 폼 인증을 위한 원격 인증 서비스에 대한 액세스를 관리합니다.<br /><br /> 이 클래스에 직접 액세스하는 주된 이유는 기본 <xref:System.Web.Security.MembershipProvider> 클래스에서 구현하지 않는 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> 및 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.UserValidated> 멤버를 사용하기 위한 것입니다. <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.ServiceUri%2A> 속성을 사용하여 프로그래밍 방식으로 서비스 위치를 설정할 수도 있습니다.<br /><br /> `static` <xref:System.Web.Security.Membership.Provider%2A?displayProperty=nameWithType> 속성을 통해 이 클래스의 인스턴스를 검색할 수 있습니다.|  
|<xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>|이 클래스는 Windows 인증을 관리합니다.<br /><br /> 이 클래스에 직접 액세스하는 주된 이유는 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider.Logout%2A> 메서드를 호출하기 위한 것입니다. 로그아웃한 후에는 사용자가 여전히 Windows에 대해 인증되지만 원격 응용 프로그램 서비스에 액세스할 수 없습니다.<br /><br /> `static` <xref:System.Web.Security.Membership.Provider%2A?displayProperty=nameWithType> 속성을 통해 이 클래스의 인스턴스를 검색할 수 있습니다.|  
|<xref:System.Web.ClientServices.Providers.ClientRoleProvider>|이 클래스는 원격 역할 서비스에 대한 액세스를 관리합니다.<br /><br /> 이 클래스에 액세스하는 주된 이유는 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A> 메서드를 호출하기 위한 것입니다. 이 클래스는 응용 프로그램이 0이 아닌 역할 서비스 캐시 제한 시간 값을 사용하도록 구성된 경우에 유용할 수 있습니다. 자세한 내용은 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하세요. <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ServiceUri%2A> 속성을 사용하여 프로그래밍 방식으로 서비스 위치를 설정할 수도 있습니다.<br /><br /> `static` <xref:System.Web.Security.Roles.Provider%2A?displayProperty=nameWithType> 속성을 통해 이 클래스의 인스턴스를 검색할 수 있습니다.|  
|<xref:System.Web.ClientServices.Providers.ClientSettingsProvider>|이 클래스는 원격 웹 설정 서비스에 대한 액세스를 관리합니다.<br /><br /> 이 클래스에 액세스하는 주된 이유는 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트를 처리하기 위한 것입니다. <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.ServiceUri%2A> 속성을 사용하여 프로그래밍 방식으로 서비스 위치를 설정할 수도 있습니다.|  
|<xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>|이 항목의 앞부분에 있는 인증 섹션에서 설명한 대로, 이 인터페이스는 응용 프로그램이 유효성 검사를 위해 사용자 자격 증명을 얻는 간접적인 방법을 제공합니다. 자세한 내용은 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하세요.|  
|<xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>|이 클래스는 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> 이벤트 처리기 내에서 사용하기 위한 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs.FailedSettingsList%2A> 속성을 제공합니다.|  
|<xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>|이 클래스는 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.UserValidated> 이벤트 처리기 내에서 사용하기 위한 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs.UserName%2A> 속성을 제공합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [클라이언트 응용 프로그램 서비스](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 [연습: 클라이언트 응용 프로그램 서비스 사용](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [응용 프로그램 설정 개요](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [ASP.NET 응용 프로그램 서비스 개요](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [Microsoft Ajax에서 양식 인증 사용](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [Microsoft Ajax에서 역할 정보 사용](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [Microsoft Ajax에서 프로필 정보 사용](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [ASP.NET 인증](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 [역할을 사용하여 인증 관리](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  
 [SQL Server에 대한 응용 프로그램 서비스 데이터베이스 만들기 및 구성](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)
