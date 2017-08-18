---
title: "연습: 클라이언트 응용 프로그램 서비스 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application services host [client application services]
- client application services, walkthroughs
ms.assetid: bb7c8950-4517-4dae-b705-b74a14059b26
caps.latest.revision: 47
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 64a27269ee6f3711f0c51f2c97cd8876c3ea6103
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-using-client-application-services"></a>연습: 클라이언트 응용 프로그램 서비스 사용
이 항목에서는 클라이언트 응용 프로그램 서비스를 사용하여 사용자를 인증하고 사용자 역할 및 설정을 검색하는 Windows 응용 프로그램을 만드는 방법을 설명합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Windows Forms 응용 프로그램을 만들고 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 디자이너를 통해 클라이언트 응용 프로그램 서비스를 사용하도록 설정 및 구성합니다.  
  
-   응용 프로그램 서비스를 호스트하고 클라이언트 구성을 테스트할 단순한 ASP.NET 웹 서비스 응용 프로그램을 만듭니다.  
  
-   응용 프로그램에 폼 인증을 추가합니다. 먼저 하드 코드된 사용자 이름 및 암호를 사용하여 서비스를 테스트합니다. 그런 다음 응용 프로그램 구성에서 자격 증명 공급자로 지정하여 로그인 폼을 추가합니다.  
  
-   역할 기반 기능을 추가하고 "manager" 역할의 사용자에 대해서만 단추를 사용하도록 설정 및 표시합니다.  
  
-   웹 설정에 액세스합니다. 먼저 프로젝트 디자이너의 **설정** 페이지에서 인증된(테스트) 사용자에 대한 웹 설정을 로드합니다. 그런 다음 Windows Forms 디자이너를 사용하여 텍스트 상자를 웹 설정에 바인딩합니다. 끝으로, 수정된 값을 서버에 다시 저장합니다.  
  
-   로그아웃을 구현합니다. 로그아웃 옵션을 폼에 추가하고 로그아웃 메서드를 호출합니다.  
  
-   오프라인 모드를 사용하도록 설정합니다. 사용자가 연결 상태를 지정할 수 있도록 확인란을 제공합니다. 그런 다음 이 값을 사용하여 클라이언트 응용 프로그램 서비스 공급자가 해당 웹 서비스에 액세스하는 대신 로컬에 캐시된 데이터를 사용할지 여부를 지정합니다. 끝으로, 응용 프로그램이 온라인 모드로 돌아가면 현재 사용자를 다시 인증합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-client-application"></a>클라이언트 응용 프로그램 만들기  
 먼저 Windows Forms 프로젝트를 만듭니다. 이 연습에서는 익숙한 사용자가 더 많기 때문에 Windows Forms를 사용하지만 WPF(Windows Presentation Foundation) 프로젝트에 대한 프로세스는 유사합니다.  
  
#### <a name="to-create-a-client-application-and-enable-client-application-services"></a>클라이언트 응용 프로그램을 만들고 클라이언트 응용 프로그램 서비스를 사용하도록 설정하려면  
  
1.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 **파일 &#124; 새로 만들기 &#124; 프로젝트** 메뉴 옵션을 선택합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic** 또는 **Visual C#** 노드를 확장하고 **Windows** 프로젝트 형식을 선택합니다.  
  
3.  **.NET Framework 3.5** 가 선택되었는지 확인하고 **Windows Forms 응용 프로그램** 템플릿을 선택합니다.  
  
4.  프로젝트 **이름** 을 `ClientAppServicesDemo`로 변경하고 **확인**을 클릭합니다.  
  
     새 Windows Forms 프로젝트가 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 열립니다.  
  
5.  **프로젝트** 메뉴에서 **ClientAppServicesDemo 속성**을 선택합니다.  
  
     프로젝트 디자이너가 나타납니다.  
  
6.  **서비스** 탭에서 **클라이언트 응용 프로그램 서비스 사용**을 선택합니다.  
  
7.  **폼 인증 사용** 이 선택되었는지 확인하고 **인증 서비스 위치**, **역할 서비스 위치**및 **웹 설정 서비스 위치** 를 `http://localhost:55555/AppServices`로 설정합니다.  
  
8.  [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 **응용 프로그램** 탭에서 **인증 모드** 를 **응용 프로그램 정의**로 설정합니다.  
  
 디자이너가 응용 프로그램의 app.config 파일에 지정된 설정을 저장합니다.  
  
 지금은 응용 프로그램이 동일한 호스트에서 세 서비스에 모두 액세스하도록 구성되어 있습니다. 다음 섹션에서는 호스트를 단순한 웹 서비스 응용 프로그램으로 만들어 클라이언트 구성을 테스트할 수 있게 합니다.  
  
## <a name="creating-the-application-services-host"></a>응용 프로그램 서비스 호스트 만들기  
 이 섹션에서는 로컬 SQL Server Compact 데이터베이스 파일에서 사용자 데이터에 액세스하는 단순한 웹 서비스 응용 프로그램을 만듭니다. 그런 다음 [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)를 사용하여 데이터베이스를 채웁니다. 이 간단한 구성을 통해 클라이언트 응용 프로그램을 신속하게 테스트할 수 있습니다. 또는 전체 SQL Server 데이터베이스 또는 사용자 지정 <xref:System.Web.Security.MembershipProvider> 및 <xref:System.Web.Security.RoleProvider> 클래스를 통해 사용자 데이터에 액세스하도록 웹 서비스 호스트를 구성할 수 있습니다. 자세한 내용은 [Creating and Configuring the Application Services Database for SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)을 참조하십시오.  
  
 다음 절차에서는 AppServices 웹 서비스를 만들고 구성합니다.  
  
#### <a name="to-create-and-configure-the-application-services-host"></a>응용 프로그램 서비스 호스트를 만들고 구성하려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 솔루션을 선택한 다음 **파일** 메뉴에서 **추가 &#124; 새 프로젝트**를 선택합니다.  
  
2.  **새 프로젝트 추가** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic** 또는 **Visual C#** 노드를 확장하고 **웹** 프로젝트 형식을 선택합니다.  
  
3.  **.NET Framework 3.5** 가 선택되었는지 확인하고 **ASP.NET 웹 서비스 응용 프로그램** 템플릿을 선택합니다.  
  
4.  프로젝트 **이름** 을 `AppServices` 로 변경하고 **확인**을 클릭합니다.  
  
     새 ASP.NET 웹 서비스 응용 프로그램 프로젝트가 솔루션에 추가되고 Service1.asmx.vb 또는 service1.asmx.cs 파일이 편집기에 나타납니다.  
  
    > [!NOTE]
    >  이 예제에서는 Service1.asmx.vb 또는 service1.asmx.cs 파일이 사용되지 않습니다. 작업 환경을 깔끔하게 유지하려는 경우 파일을 닫고 **솔루션 탐색기**에서 삭제할 수 있습니다.  
  
5.  **솔루션 탐색기**에서 AppServices 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **AppServices 속성**을 선택합니다.  
  
     프로젝트 디자이너가 나타납니다.  
  
6.  **웹** 탭에서 **Visual Studio 개발 서버 사용** 이 선택되었는지 확인합니다.  
  
7.  **특정 포트**를 선택하고 값 `55555`를 지정한 다음 **가상 경로** 를 `/AppServices`로 설정합니다.  
  
8.  모든 파일을 저장합니다.  
  
9. **솔루션 탐색기**에서 Web.config를 열고 `<system.web>` 여는 태그를 찾습니다.  
  
10. 다음 태그를 `<system.web>` 태그 앞에 추가합니다.  
  
     이 태그의 `authenticationService`, `profileService`및 `roleService` 요소는 응용 프로그램 서비스를 사용하도록 설정하고 구성합니다. 테스트 목적으로 `requireSSL` 요소의 `authenticationService` 특성이 "false"로 설정되었습니다. `readAccessProperties` 요소의 `writeAccessProperties` 및 `profileService` 특성은 `WebSettingsTestText` 속성이 읽기/쓰기임을 나타냅니다.  
  
    > [!NOTE]
    >  프로덕션 코드에서는 항상 SSL(Secure Sockets Layer, HTTPS 프로토콜 사용)을 통해 인증 서비스에 액세스해야 합니다. SSL을 설정하는 방법에 대한 자세한 내용은 [SSL(Secure Sockets Layer) 구성(IIS 6.0 운영 가이드)](http://go.microsoft.com/fwlink/?LinkId=91844)을 참조하세요.  
  
    ```xml  
    <system.web.extensions>  
      <scripting>  
        <webServices>  
          <authenticationService enabled="true" requireSSL = "false"/>  
          <profileService enabled="true"  
            readAccessProperties="WebSettingsTestText"  
            writeAccessProperties="WebSettingsTestText" />  
          <roleService enabled="true"/>  
        </webServices>  
      </scripting>  
    </system.web.extensions>  
    ```  
  
11. `<system.web>` 요소 내에 있도록 다음 태그를 `<system.web>` 여는 태그 뒤에 추가합니다.  
  
     `profile` 요소는 `WebSettingsTestText`라는 단일 웹 설정을 구성합니다.  
  
    ```xml  
    <profile enabled="true" >  
      <properties>  
        <add name="WebSettingsTestText" type="string"   
          readOnly="false" defaultValue="DefaultText"   
          serializeAs="String" allowAnonymous="false" />  
      </properties>  
    </profile>  
    ```  
  
 다음 절차에서는 ASP.NET 웹 사이트 관리 도구를 사용하여 서비스 구성을 완료하고 로컬 데이터베이스 파일을 채웁니다. 같은 이름의 두 역할에 속하는 `employee` 및 `manager` 라는 두 명의 사용자를 추가합니다. 사용자 암호는 각각 `employee!` 및 `manager!` 입니다.  
  
#### <a name="to-configure-membership-and-roles"></a>멤버 자격 및 역할을 구성하려면  
  
1.  **솔루션 탐색기**에서 AppServices 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **ASP.NET 구성**을 선택합니다.  
  
     **ASP.NET 웹 사이트 관리 도구** 가 나타납니다.  
  
2.  **보안** 탭에서 **보안 설정 마법사를 사용하여 보안을 단계별로 구성**을 클릭합니다.  
  
     **보안 설정 마법사** 가 나타나고 **시작** 단계를 표시합니다.  
  
3.  **다음**을 클릭합니다.  
  
     **액세스 방법 선택** 단계가 나타납니다.  
  
4.  **인터넷에서**를 선택합니다. 이렇게 하면 Windows 인증 대신 폼 인증을 사용하도록 서비스가 구성됩니다.  
  
5.  **다음** 을 두 번 클릭합니다.  
  
     **역할 정의** 단계가 나타납니다.  
  
6.  **이 웹 사이트에 역할 사용**을 선택합니다.  
  
7.  **다음**을 클릭합니다. **새 역할 만들기** 폼이 나타납니다.  
  
8.  **새 역할 이름** 텍스트 상자에 `manager` 를 입력하고 **역할 추가**를 클릭합니다.  
  
     **기존 역할** 테이블이 지정된 값으로 나타납니다.  
  
9. **새 역할 이름** 텍스트 상자에서 `manager` 를 `employee` 로 바꾸고 **역할 추가**를 클릭합니다.  
  
     새 값이 **기존 역할** 테이블에 나타납니다.  
  
10. **다음**을 클릭합니다.  
  
     **새 사용자 추가** 단계가 나타납니다.  
  
11. **사용자 만들기** 폼에서 다음 값을 지정합니다.  
  
  	|||  
  	|-|-|  
  	|**사용자 이름**|`manager`|  
  	|**암호**|`manager!`|  
  	|**암호 확인**|`manager!`|  
  	|**전자 메일**|`manager@contoso.com`|  
  	|**보안 질문**|`manager`|  
  	|**보안 대답**|`manager`|  
  
12. **사용자 만들기**를 클릭합니다.  
  
     성공 메시지가 나타납니다.  
  
    > [!NOTE]
    >  **메일**, **보안 질문**및 **보안 대답** 값은 폼에 필요하지만 이 예제에서는 사용되지 않습니다.  
  
13. **계속**을 클릭합니다.  
  
     **사용자 만들기** 폼이 다시 나타납니다.  
  
14. **사용자 만들기** 폼에서 다음 값을 지정합니다.  
  
  	|||  
  	|-|-|  
  	|**사용자 이름**|`employee`|  
  	|**암호**|`employee!`|  
  	|**암호 확인**|`employee!`|  
  	|**전자 메일**|`employee@contoso.com`|  
  	|**보안 질문**|`Employee`|  
  	|**보안 대답**|`employee`|  
  
15. **사용자 만들기**를 클릭합니다.  
  
     성공 메시지가 나타납니다.  
  
16. **마침**을 클릭합니다.  
  
     **웹 사이트 관리 도구** 가 다시 나타납니다.  
  
17. **사용자 관리**를 클릭합니다.  
  
     사용자 목록이 나타납니다.  
  
18. **employee** 사용자에 대해 **역할 편집** 을 클릭하고 **employee** 역할을 선택합니다.  
  
19. **manager** 사용자에 대해 **역할 편집** 을 클릭하고 **manager** 역할을 선택합니다.  
  
20. **웹 사이트 관리 도구**를 호스트하는 브라우저 창을 닫습니다.  
  
21. 수정된 Web.config 파일을 다시 로드할지 여부를 묻는 메시지 상자가 나타나면 **예**를 클릭합니다.  
  
 이제 웹 서비스 설정이 완료되었습니다. 이제 F5 키를 눌러 클라이언트 응용 프로그램을 실행할 수 있으며, **ASP.NET 개발 서버** 가 클라이언트 응용 프로그램과 함께 자동으로 시작됩니다. 응용 프로그램을 종료하면 서버가 계속 실행되지만 응용 프로그램을 다시 시작하면 서버가 다시 시작됩니다. 이렇게 하면 Web.config에 대한 변경 내용을 검색할 수 있습니다.  
  
 서버를 수동으로 중지하려면 작업 표시줄의 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **중지**를 클릭합니다. 때때로 이 기능은 새로 다시 시작되는지 확인하는 데 유용합니다.  
  
## <a name="adding-forms-authentication"></a>폼 인증 추가  
 다음 절차에서는 사용자의 유효성을 검사하고 사용자가 잘못된 자격 증명을 제공하는 경우 액세스를 거부하는 코드를 기본 폼에 추가합니다. 하드 코드된 사용자 이름 및 암호를 사용하여 서비스를 테스트합니다.  
  
#### <a name="to-validate-the-user-in-your-application-code"></a>응용 프로그램 코드에서 사용자의 유효성을 검사하려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트에 System.Web 어셈블리에 대한 참조를 추가합니다.  
  
2.  Form1 파일을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 코드**를 선택합니다.  
  
3.  코드 편집기에서 Form1 파일의 맨 위에 다음 문을 추가합니다.  
  
     [!code-csharp[ClientApplicationServices#001](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#001)]  [!code-vb[ClientApplicationServices#001](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#001)]  
  
4.  **솔루션 탐색기**에서 Form1을 두 번 클릭하여 디자이너를 표시합니다.  
  
5.  디자이너에서 폼 화면을 두 번 클릭하여 <xref:System.Windows.Forms.Form.Load?displayProperty=fullName> 라는 `Form1_Load`이벤트 처리기를 생성합니다.  
  
     코드 편집기가 나타나고 커서가 `Form1_Load` 메서드에 있습니다.  
  
6.  `Form1_Load` 메서드에 다음 코드를 추가합니다.  
  
     이 코드는 응용 프로그램을 종료하여 인증되지 않은 사용자의 액세스를 거부합니다. 또는 인증되지 않은 사용자가 폼에 액세스할 수 있게 하지만 특정 기능에 대한 액세스를 거부할 수 있습니다. 일반적으로 사용자 이름 및 암호를 이렇게 하드 코드하지는 않지만 테스트 목적으로 유용합니다. 다음 섹션에서는 로그인 대화 상자를 표시하고 예외 처리를 포함하는 보다 강력한 코드로 이 코드를 바꿉니다.  
  
     `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> 메서드는 [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]에 있습니다. 이 메서드는 해당 작업을 구성된 인증 공급자에게 위임하고 인증에 성공하면 `true` 를 반환합니다. 응용 프로그램에 클라이언트 인증 공급자에 대한 직접 참조가 필요하지는 않습니다.  
  
     [!code-csharp[ClientApplicationServices#300](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#300)]  [!code-vb[ClientApplicationServices#300](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#300)]  
  
 이제 F5 키를 눌러 응용 프로그램을 실행할 수 있으며, 올바른 사용자 이름 및 암호를 제공하기 때문에 폼이 표시됩니다.  
  
> [!NOTE]
>  응용 프로그램을 실행할 수 없는 경우 ASP.NET 개발 서버를 중지하세요. 서버가 다시 시작되면 포트가 55555로 설정되어 있는지 확인합니다.  
  
 대신 오류 메시지를 확인하려면 <xref:System.Web.Security.Membership.ValidateUser%2A> 매개 변수를 변경합니다. 예를 들어 두 번째 `"manager!"` 매개 변수를 `"MANAGER"`와 같은 잘못된 암호로 바꿉니다.  
  
## <a name="adding-a-login-form-as-a-credentials-provider"></a>자격 증명 공급자로 로그인 폼 추가  
 응용 프로그램 코드에서 사용자 자격 증명을 획득하여 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드에 전달할 수 있습니다. 그러나 나중에 변경하려는 경우를 위해 대체로 자격 증명을 획득하는 코드를 응용 프로그램 코드와 별도로 유지하는 것이 유용합니다.  
  
 다음 절차에서는 자격 증명 공급자를 사용하도록 응용 프로그램을 구성한 다음 두 매개 변수에 대해 모두 <xref:System.Web.Security.Membership.ValidateUser%2A> 를 전달하도록 <xref:System.String.Empty> 메서드 호출을 변경합니다. 빈 문자열은 구성된 자격 증명 공급자의 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드를 호출하는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 메서드를 나타냅니다.  
  
#### <a name="to-configure-your-application-to-use-a-credentials-provider"></a>자격 증명 공급자를 사용하도록 응용 프로그램을 구성하려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **ClientAppServicesDemo 속성**을 선택합니다.  
  
     프로젝트 디자이너가 나타납니다.  
  
2.  **서비스** 탭에서 **선택 사항: 자격 증명 공급자** 를 다음 값으로 설정합니다. 이 값은 정규화된 어셈블리 형식 이름을 나타냅니다.  
  
    ```  
    ClientAppServicesDemo.Login, ClientAppServicesDemo  
    ```  
  
3.  Form1 코드 파일에서 `Form1_Load` 메서드의 코드를 다음 코드로 바꿉니다.  
  
     이 코드는 환영 메시지를 표시한 후 다음 단계에서 추가할 `ValidateUsingCredentialsProvider` 메서드를 호출합니다. 사용자가 인증되지 않은 경우 `ValidateUsingCredentialsProvider` 메서드가 `false` 를 반환하고 `Form1_Load` 메서드가 반환됩니다. 이렇게 하면 응용 프로그램이 종료되기 전에 추가 코드가 실행되지 않습니다. 환영 메시지는 응용 프로그램이 다시 시작될 때 이를 명확히 표시하는 데 유용합니다. 이 연습의 뒷부분에서 로그아웃을 구현할 때 응용 프로그램을 다시 시작하는 코드를 추가합니다.  
  
     [!code-csharp[ClientApplicationServices#011](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#011)]  [!code-vb[ClientApplicationServices#011](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#011)]  
  
4.  다음 메서드를 `Form1_Load` 메서드 뒤에 추가합니다.  
  
     이 메서드는 빈 문자열을 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> 메서드에 전달하여 로그인 대화 상자를 표시합니다. 인증 서비스를 사용할 수 없는 경우 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드에서 <xref:System.Net.WebException>이 발생합니다. 이 경우 `ValidateUsingCredentialsProvider` 메서드는 경고 메시지를 표시하고 사용자에게 오프라인 모드에서 다시 시도할지 여부를 묻습니다. 이 기능을 사용하려면 **How to: Configure Client Application Services** 에 설명된 [오프라인으로 로그인할 수 있도록 로컬에 암호 해시 저장](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)기능이 필요합니다. 이 기능은 기본적으로 새 프로젝트에 대해 사용됩니다.  
  
     사용자의 유효성이 검사되지 않은 경우 `ValidateUsingCredentialsProvider` 메서드는 오류 메시지를 표시하고 응용 프로그램을 종료합니다. 끝으로, 이 메서드는 인증 시도의 결과를 반환합니다.  
  
     [!code-csharp[ClientApplicationServices#020](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#020)]  [!code-vb[ClientApplicationServices#020](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#020)]  
  
### <a name="creating-a-login-form"></a>로그인 폼 만들기  
 자격 증명 공급자는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현하는 클래스입니다. 이 인터페이스에는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 개체를 반환하는 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> 라는 단일 메서드가 있습니다. 다음 절차에서는 표시를 위해 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 를 구현하는 로그인 대화 상자를 만들고 사용자 지정 자격 증명을 반환합니다.  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 에서는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 로그인 폼 **템플릿을 제공하므로** 및 C#의 경우 별도 절차가 제공됩니다. 이렇게 하면 시간과 코딩 활동을 줄일 수 있습니다.  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-visual-basic"></a>Visual Basic에서 자격 증명 공급자로 로그인 대화 상자를 만들려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **로그인 폼** 템플릿을 선택하고 항목 **이름** 을 `Login.vb`로 변경한 다음 **추가**를 클릭합니다.  
  
     Windows Forms 디자이너에서 로그인 대화 상자가 나타납니다.  
  
3.  디자이너에서 **확인** 단추를 선택한 다음 **속성** 창에서 `DialogResult` 를 `OK`로 설정합니다.  
  
4.  디자이너에서 폼의 `CheckBox` 암호 **텍스트 상자 아래에** 컨트롤을 추가합니다.  
  
5.  **속성** 창에서 **(이름)** 값으로 `rememberMeCheckBox`를 지정하고 **텍스트** 값으로 `&Remember me`를 지정합니다.  
  
6.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 코드**를 선택합니다.  
  
7.  코드 편집기에서 파일의 맨 위에 다음 코드를 추가합니다.  
  
     [!code-vb[ClientApplicationServices#101](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#101)]  
  
8.  클래스가 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현하도록 클래스 서명을 수정합니다.  
  
     [!code-vb[ClientApplicationServices#110](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#110)]  
  
9. 커서가 `IClientformsAuthenticationCredentialsProvider`뒤에 있는지 확인하고 Enter 키를 눌러 `GetCredentials` 메서드를 생성합니다.  
  
10. <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 구현을 찾아 다음 코드로 바꿉니다.  
  
     [!code-vb[ClientApplicationServices#120](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#120)]  
  
 다음 C# 절차에서는 단순한 로그인 대화 상자에 대한 전체 코드 목록을 제공합니다. 이 대화 상자의 레이아웃은 다소 조잡하지만 중요한 부분은 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 구현입니다.  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-c"></a>C#에서 자격 증명 공급자로 로그인 대화 상자를 만들려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **클래스 추가**를 선택합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **이름** 을 `Login.cs`로 변경한 다음 **추가**를 클릭합니다.  
  
     Login.cs 파일이 코드 편집기에서 열립니다.  
  
3.  기본 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[ClientApplicationServices#200](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#200)]  
  
 이제 응용 프로그램을 실행하고 로그인 대화 상자가 표시되는 것을 확인할 수 있습니다. 이 코드를 테스트하려면 다른 자격 증명(유효한 자격 증명과 잘못된 자격 증명 둘 다)을 시도하고 유효한 자격 증명으로만 폼에 액세스할 수 있는지 확인합니다. 유효한 사용자 이름은 `employee` 및 `manager` 이고 암호는 각각 `employee!` 및 `manager!` 입니다.  
  
> [!NOTE]
>  지금은 **암호 저장** 을 선택하지 마세요. 그렇지 않으면 이 연습의 뒷부분에서 로그아웃을 구현할 때까지 다른 사용자로 로그인할 수 없습니다.  
  
## <a name="adding-role-based-functionality"></a>역할 기반 기능 추가  
 다음 절차에서는 폼에 단추를 추가하고 manager 역할의 사용자에게만 표시합니다.  
  
#### <a name="to-change-the-user-interface-based-on-user-role"></a>사용자 역할에 따라 사용자 인터페이스를 변경하려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트의 Form1을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 디자이너**를 선택합니다.  
  
2.  디자이너에서 **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 추가합니다.  
  
3.  **속성** 창에서 단추의 다음 속성을 설정합니다.  
  
  	|속성|값|  
  	|--------------|-----------|  
  	|**(이름)**|managerOnlyButton|  
  	|**텍스트**|&Manager task|  
  	|**표시**|`False`|  
  
4.  Form1에 대한 코드 편집기에서 `Form1_Load` 메서드의 끝에 다음 코드를 추가합니다.  
  
     이 코드는 다음 단계에서 추가할 `DisplayButtonForManagerRole` 메서드를 호출합니다.  
  
     [!code-csharp[ClientApplicationServices#012](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#012)]  [!code-vb[ClientApplicationServices#012](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#012)]  
  
5.  Form1 클래스의 끝에 다음 메서드를 추가합니다.  
  
     이 메서드는 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> 속성을 통해 반환된 <xref:System.Security.Principal.IPrincipal>의 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 호출합니다. 클라이언트 응용 프로그램 서비스를 사용하도록 구성된 응용 프로그램에 대해 이 속성은 <xref:System.Web.ClientServices.ClientRolePrincipal>을 반환합니다. 이 클래스는 <xref:System.Security.Principal.IPrincipal> 인터페이스를 구현하기 때문에 명시적으로 참조할 필요가 없습니다.  
  
     사용자가 "manager" 역할인 경우 `DisplayButtonForManagerRole` 메서드는 <xref:System.Windows.Forms.Control.Visible%2A> 의 `managerOnlyButton` 속성을 `true`로 설정합니다. 또한 이 메서드는 <xref:System.Net.WebException> 이 발생하여 역할 서비스를 사용할 수 없음을 나타내는 경우 오류 메시지를 표시합니다.  
  
    > [!NOTE]
    >  <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> 메서드는 사용자 로그인이 만료된 경우 항상 `false` 를 반환합니다. 이 연습에 대한 예제 코드에 표시된 것처럼 응용 프로그램이 인증 후 즉시 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 한 번 호출하는 경우에는 이 문제가 발생하지 않습니다. 다른 시간에 응용 프로그램이 사용자 역할을 검색해야 하는 경우 해당 로그인이 만료된 사용자의 유효성을 다시 검사하는 코드를 추가하는 것이 좋습니다. 모든 유효한 사용자가 역할에 할당되면 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=fullName> 메서드를 호출하여 로그인이 만료되었는지 여부를 확인할 수 있습니다. 역할이 반환되지 않는 경우 로그인이 만료된 것입니다. 이 기능의 예는 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> 메서드를 참조하세요. 이 기능은 응용 프로그램 구성에서 **서버 쿠키가 만료될 때마다 다시 사용자 로그온** 을 선택한 경우에만 필요합니다. 자세한 내용은 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하십시오.  
  
     [!code-csharp[ClientApplicationServices#030](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#030)]  [!code-vb[ClientApplicationServices#030](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#030)]  
  
 인증에 성공하면 클라이언트 인증 공급자가 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> 속성을 <xref:System.Web.ClientServices.ClientRolePrincipal> 클래스의 인스턴스로 설정합니다. 이 클래스는 작업이 구성된 역할 공급자에게 위임되도록 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 구현합니다. 이전처럼 응용 프로그램 코드에 서비스 공급자에 대한 직접 참조는 필요하지 않습니다.  
  
 이제 응용 프로그램을 실행하고 employee로 로그인하여 단추가 표시되지 않는 것을 확인한 다음 manager로 로그인하여 단추를 표시할 수 있습니다.  
  
## <a name="accessing-web-settings"></a>웹 설정 액세스  
 다음 절차에서는 폼에 텍스트 상자를 추가하고 웹 설정에 바인딩합니다. 인증 및 역할을 사용하는 이전 코드와 마찬가지로 설정 코드는 설정 공급자에 직접 액세스하지 않습니다. 대신, `Settings` 에서 프로젝트에 대해 생성된 강력한 형식의 `Properties.Settings.Default` 클래스(C#에서 `My.Settings` 로 액세스, [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]로 액세스)를 사용합니다.  
  
#### <a name="to-use-web-settings-in-your-user-interface"></a>사용자 인터페이스에서 웹 설정을 사용하려면  
  
1.  작업 표시줄의 알림 영역을 검사하여 **ASP.NET 웹 개발 서버** 가 계속 실행되고 있는지 확인합니다. 서버를 중지한 경우 응용 프로그램을 다시 시작(서버가 자동으로 시작됨)한 다음 로그인 대화 상자를 닫습니다.  
  
2.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **ClientAppServicesDemo 속성**을 선택합니다.  
  
     프로젝트 디자이너가 나타납니다.  
  
3.  **설정** 탭에서 **웹 설정 로드**를 클릭합니다.  
  
     **로그인** 대화 상자가 나타납니다.  
  
4.  employee 또는 manager에 대한 자격 증명을 입력하고 **로그인**을 클릭합니다. 인증된 사용자만 액세스할 수 있도록 구성된 웹 설정을 사용하므로 **로그인 건너뛰기** 를 클릭하면 설정이 로드되지 않습니다.  
  
     `WebSettingsTestText` 설정이 기본값 `DefaultText`로 디자이너에 표시됩니다. 또한 `WebSettingsTestText` 속성을 포함하는 `Settings` 클래스가 프로젝트에 대해 생성됩니다.  
  
5.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트의 Form1을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 디자이너**를 선택합니다.  
  
6.  디자이너에서 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼에 추가합니다.  
  
7.  **속성** 창에서 **(이름)** 값으로 `webSettingsTestTextBox`를 지정합니다.  
  
8.  코드 편집기에서 `Form1_Load` 메서드의 끝에 다음 코드를 추가합니다.  
  
     이 코드는 다음 단계에서 추가할 `BindWebSettingsTestTextBox` 메서드를 호출합니다.  
  
     [!code-csharp[ClientApplicationServices#013](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#013)]  [!code-vb[ClientApplicationServices#013](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#013)]  
  
9. Form1 클래스의 끝에 다음 메서드를 추가합니다.  
  
     이 메서드는 <xref:System.Windows.Forms.TextBox.Text%2A> 의 `webSettingsTestTextBox` 속성을 이 절차의 앞부분에서 생성된 `WebSettingsTestText` 클래스의 `Settings` 속성에 바인딩합니다. 또한 이 메서드는 <xref:System.Net.WebException>이 발생하여 웹 설정 서비스를 사용할 수 없음을 나타내는 경우 오류 메시지를 표시합니다.  
  
     [!code-csharp[ClientApplicationServices#040](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#040)]   [!code-vb[ClientApplicationServices#040](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#040)]  
  
    > [!NOTE]
    >  일반적으로 데이터 바인딩을 통해 컨트롤과 웹 설정 간의 자동 양방향 통신을 사용하도록 설정합니다. 그러나 다음 예제와 같이 웹 설정에 직접 액세스할 수도 있습니다.  
  
     [!code-csharp[ClientApplicationServices#322](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#322)]   [!code-vb[ClientApplicationServices#322](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#322)]  
  
10. 디자이너에서 폼을 선택한 다음 **속성** 창에서 **이벤트** 단추를 클릭합니다.  
  
11. <xref:System.Windows.Forms.Form.FormClosing> 이벤트를 선택한 다음 Enter 키를 눌러 이벤트 처리기를 생성합니다.  
  
12. 생성된 메서드를 다음 코드로 바꿉니다.  
  
     <xref:System.Windows.Forms.Form.FormClosing> 이벤트 처리기는 다음 섹션에서 추가할 로그아웃 기능에서도 사용되는 `SaveSettings` 메서드를 호출합니다. `SaveSettings` 메서드는 먼저 사용자가 로그아웃하지 않았음을 확인합니다. 이 작업을 위해 현재 보안 주체가 반환한 <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> 의 <xref:System.Security.Principal.IIdentity> 속성을 검사합니다. 현재 보안 주체는 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> 속성을 통해 검색됩니다. 클라이언트 응용 프로그램 서비스에 대해 사용자가 인증된 경우 인증 형식은 "ClientForms"입니다. 사용자가 로그아웃한 후 유효한 Windows ID를 가지고 있을 수도 있기 때문에 `SaveSettings` 메서드는 단순히 <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=fullName> 속성을 검사할 수 없습니다.  
  
     사용자가 로그아웃하지 않은 경우 `SaveSettings` 메서드는 이 절차의 앞부분에서 생성된 <xref:System.Configuration.ApplicationSettingsBase.Save%2A> 클래스의 `Settings` 메서드를 호출합니다. 인증 쿠키가 만료된 경우 이 메서드에서 <xref:System.Net.WebException> 이 발생할 수 있습니다. 이 문제는 응용 프로그램 구성에서 **서버 쿠키가 만료될 때마다 다시 사용자 로그온** 을 선택한 경우에만 발생합니다. 자세한 내용은 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하십시오. `SaveSettings` 메서드는 <xref:System.Web.Security.Membership.ValidateUser%2A> 호출을 통해 로그인 대화 상자를 표시하여 쿠키 만료를 처리합니다. 사용자가 성공적으로 로그인하는 경우 `SaveSettings` 메서드는 자신을 호출하여 설정을 다시 저장하려고 합니다.  
  
     이전 코드와 같이 `SaveSettings` 메서드는 원격 서비스를 사용할 수 없는 경우 오류 메시지를 표시합니다. 설정 공급자가 원격 서비스에 액세스할 수 없는 경우에도 설정이 로컬 캐시에 저장된 후 응용 프로그램이 다시 시작될 때 다시 로드됩니다.  
  
     [!code-csharp[ClientApplicationServices#050](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#050)]  [!code-vb[ClientApplicationServices#050](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#050)]  
  
13. Form1 클래스의 끝에 다음 메서드를 추가합니다.  
  
     이 코드에서는 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=fullName> 이벤트를 처리하고 설정을 저장할 수 없는 경우 경고를 표시합니다. 설정 서비스를 사용할 수 없거나 인증 쿠키가 만료된 경우에는 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트가 발생하지 않습니다. <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트가 발생하는 경우의 한 가지 예는 사용자가 이미 로그아웃한 경우입니다. `SaveSettings` 메서드에서 <xref:System.Configuration.ApplicationSettingsBase.Save%2A> 메서드 호출 바로 앞에 로그아웃 코드를 추가하여 이 이벤트 처리기를 테스트할 수 있습니다. 사용할 수 있는 로그아웃 코드는 다음 섹션에서 설명합니다.  
  
     [!code-csharp[ClientApplicationServices#090](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#090)]  [!code-vb[ClientApplicationServices#090](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#090)]  
  
14. C#의 경우 `Form1_Load` 메서드의 끝에 다음 코드를 추가합니다. 이 코드는 마지막 단계에서 추가한 메서드를 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트에 연결합니다.  
  
     [!code-csharp[ClientApplicationServices#015](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#015)]  
  
 이 시점에서 응용 프로그램을 테스트하려면 employee 및 manager 둘 다로 여러 번 실행하고 텍스트 상자에 다른 값을 입력합니다. 값은 사용자 단위로 세션 간에 유지됩니다.  
  
## <a name="implementing-logout"></a>로그아웃 구현  
 사용자가 로그인할 때 **암호 저장** 확인란을 선택하는 경우 응용 프로그램이 이후 실행 시 사용자를 자동으로 인증합니다. 응용 프로그램이 오프라인 모드에 있는 동안 또는 인증 쿠키가 만료될 때까지 자동 인증이 계속됩니다. 그러나 때로는 여러 사용자가 응용 프로그램에 액세스해야 하거나 단일 사용자가 다른 자격 증명으로 로그인할 수도 있습니다. 이 시나리오를 사용하려면 다음 절차에 설명된 대로 로그아웃 기능을 구현해야 합니다.  
  
#### <a name="to-implement-logout-functionality"></a>로그아웃 기능을 구현하려면  
  
1.  Form1 디자이너에서 **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 추가합니다.  
  
2.  **속성** 창에서 **(이름)** 값으로 `logoutButton`를 지정하고 **텍스트** 값으로 **&Log Out**을 지정합니다.  
  
3.  `logoutButton`을 두 번 클릭하여 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 생성합니다.  
  
     코드 편집기가 나타나고 커서가 `logoutButton_Click` 메서드에 있습니다.  
  
4.  생성된 `logoutButton_Click` 메서드를 다음 코드로 바꿉니다.  
  
     이 이벤트 처리기는 먼저 이전 섹션에서 추가한 `SaveSettings` 메서드를 호출합니다. 그런 다음 이벤트 처리기에서 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=fullName> 메서드를 호출합니다. 인증 서비스를 사용할 수 없는 경우 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> 메서드에서 <xref:System.Net.WebException>이 발생합니다. 이 경우 `logoutButton_Click` 메서드는 경고 메시지를 표시하고 일시적으로 오프라인 모드로 전환하여 사용자를 로그아웃합니다. 오프라인 모드는 다음 섹션에서 설명합니다.  
  
     로그아웃하면 로컬 인증 쿠키가 삭제되므로 응용 프로그램이 다시 시작될 때 로그인해야 합니다. 로그아웃한 후 이벤트 처리기에서 응용 프로그램을 다시 시작합니다. 응용 프로그램이 다시 시작되면 환영 메시지를 표시한 후 로그인 대화 상자를 표시합니다. 환영 메시지는 응용 프로그램이 다시 시작되었음을 명확히 표시합니다. 이렇게 하면 사용자가 설정을 저장하기 위해 로그인한 다음 응용 프로그램이 다시 시작되어 다시 로그인해야 하는 경우에 잠재적인 혼동을 방지할 수 있습니다.  
  
     [!code-csharp[ClientApplicationServices#070](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#070)]  [!code-vb[ClientApplicationServices#070](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#070)]  
  
 로그아웃 기능을 테스트하려면 응용 프로그램을 실행하고 로그인 대화 상자에서 **암호 저장** 을 선택합니다. 응용 프로그램을 닫은 후 다시 시작하여 더 이상 로그인할 필요가 없음을 확인합니다. 끝으로, 로그아웃을 클릭하여 응용 프로그램을 다시 시작합니다.  
  
## <a name="enabling-offline-mode"></a>오프라인 모드 사용  
 다음 절차에서는 사용자가 오프라인 모드로 전환할 수 있도록 폼에 확인란을 추가합니다. 응용 프로그램은 `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=fullName> 속성을 `true`로 설정하여 오프라인 모드를 나타냅니다. 오프라인 상태는 로컬 하드 디스크에서 <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=fullName> 속성이 나타내는 위치에 저장됩니다. 즉, 오프라인 상태는 사용자 단위 및 응용 프로그램 단위로 저장됩니다.  
  
 오프라인 모드에서는 모든 클라이언트 응용 프로그램 서비스 요청이 서비스에 액세스하는 대신 로컬 캐시에서 데이터를 검색합니다. 기본 구성에서 로컬 데이터는 암호화된 형태의 사용자 암호를 포함합니다. 이렇게 하면 응용 프로그램이 오프라인 모드에 있는 동안 사용자가 로그인할 수 있습니다. 자세한 내용은 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하십시오.  
  
#### <a name="to-enable-offline-mode-in-your-application"></a>응용 프로그램에서 오프라인 모드를 사용하도록 설정하려면  
  
1.  **솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트의 Form1을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 디자이너**를 선택합니다.  
  
2.  디자이너에서 <xref:System.Windows.Forms.CheckBox> 컨트롤을 폼에 추가합니다.  
  
3.  **속성** 창에서 **(이름)** 값으로 `workOfflineCheckBox`를 지정하고 **텍스트** 값으로 **&Work offline**을 지정합니다.  
  
4.  **속성** 창에서 **이벤트** 단추를 클릭합니다.  
  
5.  <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트를 선택한 다음 Enter 키를 눌러 이벤트 처리기를 생성합니다.  
  
6.  생성된 메서드를 다음 코드로 바꿉니다.  
  
     이 코드는 <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> 값을 업데이트하고 온라인 모드로 돌아갈 때 사용자의 유효성을 자동으로 다시 검사합니다. <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=fullName> 메서드는 캐시된 자격 증명을 사용하므로 사용자가 명시적으로 로그인할 필요가 없습니다. 인증 서비스를 사용할 수 없는 경우 경고 메시지가 나타나고 응용 프로그램이 오프라인 상태로 유지됩니다.  
  
    > [!NOTE]
    >  <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> 메서드는 편의상의 목적으로만 사용됩니다. 반환 값이 없기 때문에 유효성 재검사가 실패했는지 여부를 나타낼 수 없습니다. 예를 들어 서버에서 사용자 자격 증명이 변경된 경우 유효성 재검사가 실패할 수 있습니다. 이 경우 서비스 호출이 실패한 후 명시적으로 사용자의 유효성을 검사하는 코드를 포함하는 것이 좋습니다. 자세한 내용은 이 연습의 앞부분에 있는 웹 설정 액세스 섹션을 참조하세요.  
  
     유효성 재검사 후에 이 코드는 이전에 추가한 `SaveSettings` 메서드를 호출하여 변경 내용을 로컬 웹 설정에 저장합니다. 그런 다음 프로젝트 `Settings` 클래스의 <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> 메서드(C#에서는 `Properties.Settings.Default`로 액세스, [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 `My.Settings`로 액세스)를 호출하여 서버에서 새 값을 검색합니다.  
  
     [!code-csharp[ClientApplicationServices#080](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#080)]  [!code-vb[ClientApplicationServices#080](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#080)]  
  
7.  `Form1_Load` 메서드의 끝에 다음 코드를 추가하여 확인란이 현재 연결 상태를 표시하는지 확인합니다.  
  
     [!code-csharp[ClientApplicationServices#014](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#014)]  [!code-vb[ClientApplicationServices#014](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#014)]  
  
 이제 예제 응용 프로그램이 완성되었습니다. 오프라인 기능을 테스트하려면 응용 프로그램을 실행하고 employee 또는 manager로 로그인한 다음 **오프라인으로 작업**을 선택합니다. 텍스트 상자의 값을 수정하고 응용 프로그램을 닫습니다. 응용 프로그램을 다시 시작합니다. 로그인하기 전에 서버를 수동으로 중지하려면 작업 표시줄의 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **중지**를 클릭합니다. 그런 다음 일반적인 방법으로 로그인합니다. 서버가 실행되지 않는 경우에도 로그인할 수 있습니다. 텍스트 상자 값을 수정하고 종료한 후 다시 시작하여 수정된 값을 확인합니다.  
  
## <a name="summary"></a>요약  
 이 연습에서는 Windows Forms 응용 프로그램에서 클라이언트 응용 프로그램 서비스를 사용하도록 설정 및 사용하는 방법을 배웠습니다. 테스트 서버를 설정한 후 사용자를 인증하고 서버에서 사용자 역할 및 응용 프로그램 설정을 검색하는 코드를 응용 프로그램에 추가했습니다. 또한 연결을 사용할 수 없을 때 응용 프로그램에서 원격 서비스 대신 로컬 데이터 캐시를 사용하도록 오프라인 모드를 사용하는 방법을 배웠습니다.  
  
## <a name="next-steps"></a>다음 단계  
 실제 응용 프로그램에서는 사용할 수 없는 경우가 있거나 통지 없이 다운될 수 있는 원격 서버에서 많은 사용자의 데이터에 액세스합니다. 강력한 응용 프로그램을 만들려면 서비스를 사용할 수 없는 상황에 적절하게 대응해야 합니다. 이 연습에서는 try/catch 블록을 포함하여 <xref:System.Net.WebException> 을 catch하고 서비스를 사용할 수 없는 경우 오류 메시지를 표시합니다. 프로덕션 코드에서는 오프라인 모드로 전환하거나, 응용 프로그램을 종료하거나, 특정 기능에 대한 액세스를 거부하여 이러한 경우를 처리하는 것이 좋습니다.  
  
 응용 프로그램 보안을 강화하려면 배포 전에 응용 프로그램과 서버를 철저히 테스트해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클라이언트 응용 프로그램 서비스](../../../docs/framework/common-client-technologies/client-application-services.md)   
 [클라이언트 응용 프로그램 서비스 개요](../../../docs/framework/common-client-technologies/client-application-services-overview.md)   
 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)   
 [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)   
 [SQL Server에 대한 응용 프로그램 서비스 데이터베이스 만들기 및 구성](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)   
 [연습: ASP.NET 응용 프로그램 서비스 사용](http://msdn.microsoft.com/library/f3f394f0-20d6-4361-aa8f-4b21bf4933eb)

