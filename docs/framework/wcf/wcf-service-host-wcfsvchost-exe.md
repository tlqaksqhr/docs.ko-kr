---
title: "WCF 서비스 호스트(WcfSvcHost.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# WCF 서비스 호스트(WcfSvcHost.exe)
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 호스트\(WcfSvcHost.exe\)를 사용하면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 디버거\(F5\)를 시작하여 구현한 서비스를 자동으로 호스팅하고 테스트할 수 있습니다.그런 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트\(WcfTestClient.exe\) 또는 자체 클라이언트로 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.  
  
## WCF 서비스 호스트  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트의 서비스를 열거하고 프로젝트의 구성을 로드하며 찾은 각 서비스에 대한 호스트를 인스턴스화합니다.이 도구는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 템플릿을 통해 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에 통합되어 프로젝트의 디버깅을 시작할 때 호출됩니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 사용하면 개발하는 동안 추가 코드를 작성하거나 특정 호스트를 커밋하지 않고 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트의 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스트할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 부분 신뢰를 지원하지 않습니다.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 부분 신뢰에서 사용하려는 경우 서비스를 빌드하기 위해 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트 템플릿을 사용하지 마십시오.대신 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 WebSite 템플릿을 선택하여 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 새 WebSite를 만들고, 이를 통해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 부분 신뢰가 지원되는 WebServer에서 서비스를 호스팅할 수 있습니다.  
  
## WCF 서비스 호스트에서 호스팅하는 프로젝트 형식  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리, 순차 워크플로 서비스 라이브러리, 상태 시스템 워크플로 서비스 라이브러리 및 배포 서비스 라이브러리와 같은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트 형식을 호스팅할 수 있습니다.또한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 **항목 추가** 기능을 사용하여 서비스 라이브러리 프로젝트에 추가할 수 있는 해당 서비스를 호스팅할 수 있습니다.여기에는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스, WF 상태 시스템 서비스, WF 순차 서비스, XAML WF 상태 시스템 서비스 및 XAML WF 순차 서비스가 포함됩니다.  
  
 그러나 이 도구를 사용하여 호스트를 구성할 수는 없습니다.이 작업의 경우 App.config 파일을 수동으로 편집해야 합니다.또한 이 도구는 사용자 정의 구성 파일의 유효성을 검사하지 않습니다.  
  
> [!CAUTION]
>  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 프로덕션 환경에서 서비스를 호스팅할 목적으로 엔지니어링되지는 않았기 때문에 해당 목적으로 사용해서는 안 됩니다.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트는 이러한 환경의 안정성, 보안성 및 관리 효율성 요구 사항을 지원하지 않습니다.IIS는 우수한 안정성 및 모니터링 기능을 제공하는 호스팅 서비스의 기본 솔루션이므로 대신 IIS를 사용합니다.서비스 개발이 완료되면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트에서 IIS로 서비스를 마이그레이션해야 합니다.  
  
## Visual Studio 내에서 WCF 서비스 호스트를 사용하기 위한 시나리오  
 다음 표에서는 **명령줄 인수** 대화 상자의 모든 매개 변수를 보여 줍니다. 이 대화 상자는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하여 **속성**을 선택한 다음 **디버그** 탭을 선택하고 **프로젝트 시작**을 클릭하여 찾을 수 있습니다.이러한 매개 변수는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 구성할 때 유용합니다.  
  
|매개 변수|의미|  
|-----------|--------|  
|`/client`|서비스가 호스팅된 후에 실행할 실행 파일의 경로를 지정하는 선택적 매개 변수입니다.이 매개 변수를 사용하면 서비스가 호스팅된 후에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트가 시작됩니다.|  
|`/clientArg`|문자열을 사용자 지정 클라이언트 응용 프로그램에 전달되는 인수로 지정합니다.|  
|`/?`|도움말 텍스트를 표시합니다.|  
  
#### WCF 테스트 클라이언트 사용  
 새 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트를 만들고 F5 키를 눌러 디버거를 시작하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 프로젝트에서 찾은 모든 서비스를 호스팅하기 시작합니다.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트는 구성 파일에 정의된 서비스 끝점 목록을 자동으로 열어 표시합니다.주 창에서 매개 변수를 테스트하고 서비스를 호출할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트가 사용되는지 확인하려면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택한 다음 **디버그** 탭을 선택합니다.**프로젝트 시작**을 클릭하고 다음 항목이 **명령줄 인수** 대화 상자에 표시되는지 확인합니다.  
  
 `/client:WcfTestClient.exe`  
  
#### 사용자 지정 클라이언트 사용  
 사용자 지정 클라이언트를 사용하려면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하여 **속성**을 선택한 다음 **디버그** 탭을 선택합니다.**프로젝트 시작**을 클릭하고 **명령줄 인수** 대화 상자에서 `/client` 매개 변수를 편집하여 다음 예제에서처럼 사용자 지정 클라이언트를 가리킵니다.  
  
 `/client:"path/CustomClient.exe"`  
  
 F5 키를 눌러 서비스를 다시 시작하는 경우 디버거를 시작할 때 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 사용자 지정 클라이언트를 자동으로 시작합니다.  
  
 또한 `/clientArg:` 매개 변수를 사용하여 다음 예제에서처럼 문자열을 사용자 지정 클라이언트 응용 프로그램에 전달되는 인수로 지정할 수 있습니다.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 예를 들어 배포 서비스 라이브러리 템플릿을 사용하는 경우 다음 명령줄 인수를 사용할 수 있습니다.  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### 클라이언트 없음 지정  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스팅 후에 클라이언트를 사용하지 않도록 지정하려면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 **솔루션 탐색기**에서 **속성**을 선택한 다음 **디버그** 탭을 선택합니다.**프로젝트 시작**을 클릭하고 **명령줄 인수** 대화 상자를 비워 둡니다.  
  
#### 사용자 지정 호스트 사용  
 사용자 지정 호스트를 사용하려면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하여 **속성**을 선택한 다음 **디버그** 탭을 선택합니다.**시작 외부 프로그램**을 클릭하고 사용자 지정 호스트의 전체 경로를 입력합니다.또한 **명령줄 인수** 대화 상자를 사용하여 호스트에 전달되는 인수를 지정할 수 있습니다.  
  
## WCF 서비스 호스트 사용자 인터페이스  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 경우 F5 키를 눌러 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 처음으로 호출하면 **WCF 서비스 호스트** 창이 자동으로 열립니다.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 실행 중이면 프로그램의 아이콘이 알림 영역에 표시됩니다.아이콘을 두 번 클릭하여 **WCF 서비스 호스트** 창을 엽니다.  
  
 서비스를 호스팅하는 동안 오류가 발생하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트 대화 상자가 열리고 관련 정보가 표시됩니다.  
  
 **WCF 서비스 호스트** 주 창에는 다음 두 개의 메뉴가 있습니다.  
  
-   **파일**: **닫기** 및 **끝내기** 명령이 있습니다.**닫기**를 클릭하면 **WCF 서비스 호스트** 대화 상자가 닫히지만 서비스는 계속 호스팅됩니다.**끝내기**를 클릭하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트도 종료됩니다.또한 호스팅되는 서비스가 모두 중지됩니다.  
  
-   **도움말**: 버전 정보가 포함된 **정보** 명령이 있습니다.또한 도움말 파일을 열 수 있는 **도움말** 명령이 있습니다.  
  
 주 **WCF 서비스 호스트** 창에는 다음 두 개의 영역이 있습니다.  
  
-   첫 번째 영역은 **서비스**입니다.여기에는 모든 서비스의 기본 정보를 표시하는 목록이 있습니다.이 정보에는 다음과 같은 내용이 포함됩니다.  
  
    -   **서비스**: 모든 서비스를 나열합니다.  
  
    -   **상태**: 서비스의 상태를 나열합니다.유효한 값은 "시작됨", "중지됨" 및 "오류"입니다.  
  
    -   **메타데이터 주소**: 서비스의 메타데이터 주소를 표시합니다.  
  
-   두 번째 영역은 **추가 정보**입니다.이 영역은 **서비스** 영역에서 특정 서비스 줄을 선택한 경우 해당 서비스 상태에 대한 자세한 정보를 표시합니다.상태가 Error인 경우 화면에서 전체 오류 메시지를 볼 수 있습니다.  
  
## WCF 서비스 호스트 중지  
 다음과 같은 네 가지 방법으로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트를 종료할 수 있습니다.  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 디버깅 세션을 중지합니다.  
  
-   **WCF 서비스 호스트** 창의 **파일** 메뉴에서 **끝내기**를 선택합니다.  
  
-   시스템 알림 영역에 있는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트 트레이 아이콘의 상황에 맞는 메뉴에서 **끝내기**를 선택합니다.  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트를 사용 중이면 끝냅니다.  
  
## 관리자 권한 없이 서비스 호스트 사용  
 관리자 권한이 없는 사용자도 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 개발할 수 있도록 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 설치하는 동안 "http:\/\/\+:8731\/Design\_Time\_Addresses" 네임스페이스에 대한 ACL\(액세스 제어 목록\)이 만들어집니다.ACL은 \(UI\)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다.관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. 관리자 권한이 없는 사용자도 이 ACL을 통해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트\(wcfSvcHost.exe\)를 사용할 수 있습니다.  
  
 [!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다.다음은 netsh.exe를 사용하는 예입니다.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Netsh.exe에 대한 자세한 내용은 "[Netsh.exe 도구 및 명령줄 스위치 사용 방법](http://go.microsoft.com/fwlink/?LinkId=97877)"\(영문 페이지일 수 있음\)을 참조하십시오.  
  
## 참고 항목  
 [WCF 테스트 클라이언트\(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)