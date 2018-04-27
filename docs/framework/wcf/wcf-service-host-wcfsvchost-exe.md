---
title: WCF 서비스 호스트(WcfSvcHost.exe)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1da8d7a08e7887e8ba3fd50a8f809e2ff551a7fd
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="wcf-service-host-wcfsvchostexe"></a>WCF 서비스 호스트(WcfSvcHost.exe)
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 호스트 (WcfSvcHost.exe)를 사용 하면 (F5) 자동으로 호스팅하고 테스트할 구현한 서비스를 Visual Studio 디버거를 시작할 수 있습니다. 그런 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트(WcfTestClient.exe) 또는 자체 클라이언트로 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.  
  
## <a name="wcf-service-host"></a>WCF 서비스 호스트  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트의 서비스를 열거하고 프로젝트의 구성을 로드하며 찾은 각 서비스에 대한 호스트를 인스턴스화합니다. 이 도구를 통해 Visual Studio에 통합 되어는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 템플릿 및 프로젝트 디버깅을 시작할 때 호출 됩니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 사용하면 개발하는 동안 추가 코드를 작성하거나 특정 호스트를 커밋하지 않고 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트의 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스트할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 부분 신뢰를 지원하지 않습니다. 사용 하려는 경우는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 부분 신뢰를 사용 하지 않는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 빌드하기 위해 Visual Studio에서 서비스 라이브러리 프로젝트 템플릿을 합니다. Visual Studio에서 선택 하 여 새 웹 사이트를 대신 만듭니다는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 는 WebServer에서 서비스를 호스트할 수 있는 서비스 WebSite 템플릿을 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 부분 신뢰가 지원 되 합니다.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>WCF 서비스 호스트에서 호스팅하는 프로젝트 형식  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리, 순차 워크플로 서비스 라이브러리, 상태 시스템 워크플로 서비스 라이브러리 및 배포 서비스 라이브러리와 같은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트 형식을 호스팅할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트 사용 하 여 서비스 라이브러리 프로젝트에 추가할 수 있는 해당 서비스를 호스트할 수 있습니다는 **항목 추가** 기능입니다. 여기에는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스, WF 상태 시스템 서비스, WF 순차 서비스, XAML WF 상태 시스템 서비스 및 XAML WF 순차 서비스가 포함됩니다.  
  
 그러나 이 도구를 사용하여 호스트를 구성할 수는 없습니다. 이 작업의 경우 App.config 파일을 수동으로 편집해야 합니다. 또한 이 도구는 사용자 정의 구성 파일의 유효성을 검사하지 않습니다.  
  
> [!CAUTION]
>  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 프로덕션 환경에서 서비스를 호스팅할 목적으로 엔지니어링되지는 않았기 때문에 해당 목적으로 사용해서는 안 됩니다.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 이러한 환경의 안정성, 보안성 및 관리 효율성 요구 사항을 지원하지 않습니다. IIS는 우수한 안정성 및 모니터링 기능을 제공하는 호스팅 서비스의 기본 솔루션이므로 대신 IIS를 사용합니다. 서비스 개발이 완료되면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트에서 IIS로 서비스를 마이그레이션해야 합니다.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Visual Studio 내에서 WCF 서비스 호스트를 사용하기 위한 시나리오  
 다음 표에서 모든 매개 변수에 **명령줄 인수** 대화 상자에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 찾을 수 있는 **솔루션 탐색기** 를선택하면VisualStudio에서**속성**, 다음을 선택 하는 **디버그** 탭을 클릭 하 고 **프로젝트 시작**합니다. 이러한 매개 변수는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 구성할 때 유용합니다.  
  
|매개 변수|의미|  
|---------------|-------------|  
|`/client`|서비스가 호스팅된 후에 실행할 실행 파일의 경로를 지정하는 선택적 매개 변수입니다. 이 매개 변수를 사용하면 서비스가 호스팅된 후에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트가 시작됩니다.|  
|`/clientArg`|문자열을 사용자 지정 클라이언트 응용 프로그램에 전달되는 인수로 지정합니다.|  
|`/?`|도움말 텍스트를 표시합니다.|  
  
#### <a name="using-wcf-test-client"></a>WCF 테스트 클라이언트 사용  
 새 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트를 만들고 F5 키를 눌러 디버거를 시작하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 프로젝트에서 찾은 모든 서비스를 호스팅하기 시작합니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트는 구성 파일에 정의된 서비스 끝점 목록을 자동으로 열어 표시합니다. 주 창에서 매개 변수를 테스트하고 서비스를 호출할 수 있습니다.  
  
 고유 하도록 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트 사용 하는 경우에서 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** Visual Studio에서 선택 **속성**을 선택한 후는 **디버그**탭 합니다. 클릭 **프로젝트 시작** 다음에 표시 되는지 확인 하 고는 **명령줄 인수** 대화 상자.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>사용자 지정 클라이언트 사용  
 프로젝트를 마우스 오른쪽 단추로 클릭 한 사용자 지정 클라이언트를 사용 하려면 **솔루션 탐색기** Visual Studio에서 선택 **속성**을 선택한 후는 **디버그** 탭 합니다. 클릭 **프로젝트 시작** 편집 하 고는 `/client` 에서 매개 변수는 **명령줄 인수** 대화 상자는 다음 예제에 표시 된 대로 사용자 지정 클라이언트를 가리키도록 합니다.  
  
 `/client:"path/CustomClient.exe"`  
  
 F5 키를 눌러 서비스를 다시 시작하는 경우 디버거를 시작할 때 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 사용자 지정 클라이언트를 자동으로 시작합니다.  
  
 또한 `/clientArg:` 매개 변수를 사용하여 다음 예제에서처럼 문자열을 사용자 지정 클라이언트 응용 프로그램에 전달되는 인수로 지정할 수 있습니다.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 예를 들어 배포 서비스 라이브러리 템플릿을 사용하는 경우 다음 명령줄 인수를 사용할 수 있습니다.  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>클라이언트 없음 지정  
 클라이언트가 후 사용될지를 지정 하려면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 호스팅 서비스를에서 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** Visual Studio에서 선택 **속성**을 선택한 후는  **디버그** 탭 합니다. 클릭 **프로젝트 시작** 유지는 **명령줄 인수** 대화 상자를 비워 합니다.  
  
#### <a name="using-a-custom-host"></a>사용자 지정 호스트 사용  
 프로젝트를 마우스 오른쪽 단추로 클릭 한 사용자 지정 호스트를 사용 하려면 **솔루션 탐색기** Visual Studio에서 선택 **속성**을 선택한 후는 **디버그** 탭 합니다. 클릭 **시작 외부 프로그램** 고 사용자 지정 호스트에 전체 경로 입력 합니다. 사용할 수도 있습니다는 **명령줄 인수** 대화 상자는 호스트에 전달 될 인수를 지정 합니다.  
  
## <a name="wcf-service-host-user-interface"></a>WCF 서비스 호스트 사용자 인터페이스  
 처음 호출 하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (f5 키를 눌러 Visual Studio 내부), 서비스 호스트는 **WCF 서비스 호스트** 창이 자동으로 열립니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 실행 중이면 프로그램의 아이콘이 알림 영역에 표시됩니다. 아이콘 열을 두 번 클릭 하 여 **WCF 서비스 호스트** 창  
  
 서비스를 호스팅하는 동안 오류가 발생하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트 대화 상자가 열리고 관련 정보가 표시됩니다.  
  
 **WCF 서비스 호스트** 주 창에 다음 두 개의 메뉴가 있습니다.  
  
-   **파일**: 포함 된 **닫기** 및 **종료** 명령입니다. 클릭할 때 **닫기**, **WCF 서비스 호스트** 대화 상자가 닫히지만 서비스는 계속 호스팅됩니다. 클릭할 때 **종료**, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트도 종료 됩니다. 또한 호스팅되는 서비스가 모두 중지됩니다.  
  
-   **도움말**: 포함 된 **에 대 한** 버전 정보를 포함 하는 명령입니다. 또한 포함 되어는 **도움말** 도움말 파일을 열 수 있는 명령입니다.  
  
 주 **WCF 서비스 호스트** 창 두 영역이 포함 되어 있습니다.  
  
-   첫 번째 영역은 **서비스**합니다. 여기에는 모든 서비스의 기본 정보를 표시하는 목록이 있습니다. 이 정보에는 다음과 같은 내용이 포함됩니다.  
  
    -   **서비스**: 모든 서비스를 나열 합니다.  
  
    -   **상태**: 서비스의 상태를 나열 합니다. 유효한 값은 "시작됨", "중지됨" 및 "오류"입니다.  
  
    -   **메타 데이터 주소**: 서비스의 메타 데이터 주소를 표시 합니다.  
  
-   두 번째 영역은 **추가 정보**합니다. 특정 서비스 줄을 선택할 때 서비스의 상태에 대 한 자세한 내용은 표시 된 **서비스** 영역입니다. 상태가 Error인 경우 화면에서 전체 오류 메시지를 볼 수 있습니다.  
  
## <a name="stopping-wcf-service-host"></a>WCF 서비스 호스트 중지  
 다음과 같은 네 가지 방법으로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 종료할 수 있습니다.  
  
-   Visual Studio에서 디버깅 세션을 중지 합니다.  
  
-   선택 **종료** 에서 **파일** 메뉴에는 **WCF 서비스 호스트** 창.  
  
-   선택 **종료** 상황에 맞는 메뉴에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 시스템 알림 영역에 서비스 호스트 트레이 아이콘입니다.  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트를 사용 중이면 끝냅니다.  
  
## <a name="using-service-host-without-administrator-privilege"></a>관리자 권한 없이 서비스 호스트 사용  
 개발 하는 관리자 권한이 없는 사용자도 사용할 수 있도록 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 ACL (액세스 제어 목록) 네임 스페이스에 대해 만들어집니다 "http://+:8731/Design_Time_Addresses" Visual Studio의 설치 중입니다. ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다. 관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. 관리자 권한이 없는 사용자도 이 ACL을 통해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트(wcfSvcHost.exe)를 사용할 수 있습니다.  
  
 [!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다. 다음은 netsh.exe를 사용하는 예입니다.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Netsh.exe에 대 한 자세한 내용은 참조 하십시오. "[Netsh.exe 도구 및 명령줄 스위치를 사용 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=97877)"입니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
