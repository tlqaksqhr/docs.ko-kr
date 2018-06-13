---
title: Visual Basic에서 My 네임스페이스 확장
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 22d9d0def302b870de6f3e5ca4c142758b21314c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591835"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Visual Basic에서 My 네임스페이스 확장
`My` Visual Basic의 네임 스페이스 속성과 쉽게.NET Framework의 기능을 활용 하기 위해 사용할 수 있는 메서드를 노출 합니다. `My` 네임 스페이스 코드 한 줄으로 어려운 작업이 줄어들 일반적인 프로그래밍 문제를 단순화 합니다. 또한는 `My` 의 동작을 사용자 지정할 수 있도록 네임 스페이스는 à ü è `My` 특정 응용 프로그램 요구 사항에 맞게 조정 하는 계층 구조를 새 서비스를 추가 합니다. 이 항목에서는 기존 멤버의 사용자 지정 하는 `My` 네임 스페이스 및 사용자 지정 클래스를 추가 하는 방법의 `My` 네임 스페이스.  
  
 **항목 내용**  
  
-   [기존 Namespace 멤버 내에 사용자 지정](#customizing)  
  
-   [My 개체에 멤버 추가](#addingtoobjects)  
  
-   [사용자 지정 개체를 추가 하는 내 Namespace](#addingcustom)  
  
-   [멤버를 추가할는 My Namespace](#addingtonamespace)  
  
-   [사용자 지정 My 개체에 이벤트 추가](#addingevents)  
  
-   [디자인 지침](#design)  
  
-   [클래스 라이브러리에 대 한 디자인 내](#designing)  
  
-   [확장 패키징 및 배포](#packaging)  
  
##  <a name="customizing"></a> 기존 Namespace 멤버 내에 사용자 지정  
 `My` 자주 사용 하는 응용 프로그램, 컴퓨터, 등에 대 한 정보 노출 Visual Basic의에서 네임 스페이스입니다. 에 있는 개체의 전체 목록은 `My` 네임 스페이스, 참조 [내 참조](../../../visual-basic/language-reference/keywords/my-reference.md)합니다. 기존 멤버를 사용자 지정 해야 할 수 있습니다는 `My` 네임 스페이스 하므로 맞게 응용 프로그램의 필요 합니다. 에 있는 개체의 모든 속성은 `My` 읽기 전용으로 설정 하지 않은 네임 스페이스 사용자 지정 값으로 설정할 수 있습니다.  
  
 예를 들어, 자주 사용 하는 `My.User` 응용 프로그램을 실행 하는 사용자에 대 한 현재 보안 컨텍스트를 액세스 하는 개체입니다. 그러나 회사 추가 정보 및 회사 내 사용자에 대 한 기능을 노출 하는 사용자 지정 개체를 사용 합니다. 이 시나리오에서의 기본값을 대체할 수 있습니다는 `My.User.CurrentPrincipal` 다음 예제에서와 같이 사용자 고유의 사용자 지정 보안 주체 개체의 인스턴스를 사용 하 여 속성입니다.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 설정의 `CurrentPrincipal` 속성에는 `My.User` 개체 변경 되는 응용 프로그램이 실행 되는 id입니다. `My.User` 개체 차례로 새로 지정 된 사용자에 대 한 정보를 반환 합니다.  
  
##  <a name="addingtoobjects"></a> My 개체에 멤버 추가  
 반환 하는 형식은 `My.Application` 및 `My.Computer` 로 정의 `Partial` 클래스입니다. 따라서를 확장할 수 있습니다는 `My.Application` 및 `My.Computer` 개체를 만들어 한 `Partial` 라는 클래스 `MyApplication` 또는 `MyComputer`합니다. 클래스는 사용할 수 없습니다는 `Private` 클래스입니다. 클래스의 일부로 지정 하는 경우는 `My` 네임 스페이스에 포함 될 수 있는 속성 및 메서드 추가할 수 있습니다는 `My.Application` 또는 `My.Computer` 개체입니다.  
  
 다음 예에서는 라는 속성을 추가 하는 예를 들어 `DnsServerIPAddresses` 에 `My.Computer` 개체입니다.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> 사용자 지정 개체를 추가 하는 내 Namespace  
 하지만 `My` 작업이 있을 수 있습니다, 네임 스페이스는 여러 일반 프로그래밍 작업에 대 한 솔루션을 제공 하는 `My` 네임 스페이스는 다루지 않습니다. 예를 들어 응용 프로그램 사용자 데이터에 대 한 사용자 지정 디렉터리 서비스에 액세스할 수 있습니다 또는 응용 프로그램에서 Visual Basic을 사용한 기본적으로 설치 되지 않은 어셈블리를 사용할 수 있습니다. 확장할 수 있습니다는 `My` 네임 스페이스 사용자 지정 솔루션 환경에 관련 된 일반적인 작업을 포함할 수 있습니다. `My` 네임 스페이스는 증가 하는 응용 프로그램 요구를 충족 하기 위해 새 멤버를 추가 하려면 쉽게 확장할 수 있습니다. 또한 배포할 수 있습니다 프로그램 `My` Visual Basic 템플릿으로 다른 개발자에 게 네임 스페이스 확장 합니다.  
  
###  <a name="addingtonamespace"></a> 멤버를 추가할는 My Namespace  
 때문에 `My` 네임 스페이스는 다른 네임 스페이스와 비슷한 있습니다 수 최상위 속성을 추가할 모듈을 추가 하 고 지정 하 여 한 `Namespace` 의 `My`합니다. 주석을 사용 하 여 모듈의 `HideModuleName` 다음 예제와 같이 특성입니다. `HideModuleName` 특성 IntelliSense의 멤버를 표시 하는 경우 모듈 이름 표시 되지 것입니다 보장은 `My` 네임 스페이스입니다.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 멤버를 추가 하는 `My` 네임 스페이스, 모듈에 필요에 따라 속성을 추가 합니다. 에 추가 된 각 속성에 대 한는 `My` 네임 스페이스, 형식의 private 필드를 추가 `ThreadSafeObjectProvider(Of T)`형식이 사용자 지정 속성에서 반환 되는 형식, 합니다. 이 필드는 스레드로부터 안전한 개체 인스턴스를 호출 하 여 속성에 의해 반환 될 만드는에 사용 된 `GetInstance` 메서드. 결과적으로, 확장된 속성에 액세스 하는 각 스레드에 반환 된 형식의 인스턴스를 받습니다. 다음 예에서는 라는 속성을 추가 `SampleExtension` 형식의 `SampleExtension` 에 `My` 네임 스페이스:  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> 사용자 지정 My 개체에 이벤트 추가  
 사용할 수는 `My.Application` 사용자 지정에 대 한 이벤트를 노출 하는 개체 `My` 확장 하 여 개체는 `MyApplication` partial 클래스에는 `My` 네임 스페이스입니다. Windows 기반 프로젝트를 두 번 있습니다는 **My Project** 에서 프로젝트에 대 한 노드에서 **솔루션 탐색기**합니다. Visual Basic에서 **프로젝트 디자이너**, 클릭는 `Application` 탭을 클릭 한 다음는 `View Application Events` 단추입니다. ApplicationEvents.vb 라는 새 파일 생성 됩니다. 확장 하기 위한 다음 코드가 포함 되어는 `MyApplication` 클래스입니다.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 사용자 지정에 대 한 이벤트 처리기를 추가할 `My` 사용자 지정 이벤트 처리기를 추가 하 여 개체는 `MyApplication` 클래스입니다. 사용자 지정 이벤트를 통해 이벤트 처리기 추가, 제거, 또는 이벤트가 발생할 때 실행 되는 코드를 추가할 수 있습니다. `AddHandler` 를 위한 사용자 지정 이벤트는 이벤트를 처리 하는 사용자가 코드를 추가한 경우에 실행 코드입니다. 예를 들어 다음을 고려해 야는 `SampleExtension` 이전 섹션에서 개체에는 `Load` 이벤트에 대 한 사용자 지정 이벤트 처리기를 추가 하려면입니다. 다음 코드 예제에서는 라는 사용자 지정 이벤트 처리기를 보여 줍니다. `SampleExtensionLoad` 될 될 때 호출 되는 `My.SampleExtension.Load` 이벤트가 발생 합니다. 새 처리 하기 위해 코드 추가 때 `My.SampleExtensionLoad` 이벤트에는 `AddHandler` 이 사용자 지정 이벤트 코드를 실행 합니다. `MyApplication_SampleExtensionLoad` 메서드를 처리 하는 이벤트 처리기의 예가 나와 코드 예제에 포함 되어는 `My.SampleExtensionLoad` 이벤트입니다. `SampleExtensionLoad` 이벤트를 선택 하면 사용할 수 있습니다는 **내 응용 프로그램 이벤트** 코드 편집기 위의 ApplicationEvents.vb 파일을 편집 하는 경우 왼쪽된 드롭다운 목록에서 옵션입니다.  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> 디자인 지침  
 에 대 한 확장을 개발 하는 경우는 `My` 네임 스페이스 확장 구성 요소의 유지 관리 비용을 최소화 하기 위해 다음 지침을 따르세요.  
  
-   **확장 논리만 포함 됩니다.** 에 포함 된 논리는 `My` 네임 스페이스 확장에 필요한 기능을 노출 하는 데 필요한 코드만 포함 해야는 `My` 네임 스페이스입니다. 확장 프로그램은 소스 코드로 사용자 프로젝트에 상주 합니다, 하기 때문에 높은 유지 관리 비용이 발생 있으며 가능한 경우 피해 야 확장 구성 요소를 업데이트 합니다.  
  
-   **프로젝트 가정을 최소화 합니다.** 확장을 만들 때는 `My` 네임 스페이스, 참조, 프로젝트 수준의 imports 또는 특정 컴파일러 설정 집합이 가정 하지 않습니다 (예를 들어 `Option Strict` 해제) 합니다. 대신, 종속성을 최소화 하 고 사용 하 여 모든 형식 참조를 정규화는 `Global` 키워드입니다. 또한 확장 된 컴파일되는지 확인 `Option Strict` 확장에 대 한 오류를 최소화 on입니다.  
  
-   **확장 코드를 격리 합니다.** 단일 파일에 코드를 넣거나 하면 확장 프로그램을 Visual Studio 항목 템플릿으로 쉽게 배포할 수 있습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "확장 패키징 및 배포"를 참조 하십시오. 모든 배치는 `My` 단일 파일에서 네임 스페이스 확장 코드 또는 프로젝트에서 별도 폴더에도 도움이 됩니다 찾을 사용자는 `My` 네임 스페이스 확장 합니다.  
  
##  <a name="designing"></a> 클래스 라이브러리에 대 한 디자인 내  
 대부분의 개체 모델과 마찬가지로 몇 가지 디자인 패턴에서 잘 작동 하는 `My` 네임 스페이스와 다른 그렇지 않습니다. 에 대 한 확장을 디자인 하는 경우는 `My` 네임 스페이스 원칙은 다음과:  
  
-   **상태 비저장 메서드입니다.** 메서드는 `My` 네임 스페이스는 특정 작업에 완벽 한 솔루션을 제공 해야 합니다. 메서드에 전달 되는 매개 변수 값 특정 작업을 완료 하는 데 필요한 모든 입력을 제공 하는지 확인 합니다. 리소스에 대 한 열린 연결 등의 이전 상태를 사용 하는 메서드를 만들지 마십시오.  
  
-   **전역 인스턴스입니다.** 유지 관리 되는 유일한 상태는 `My` 네임 스페이스 전체 프로젝트에 적용 됩니다. 예를 들어 `My.Application.Info` 응용 프로그램에 걸쳐 공유 된 상태를 캡슐화 합니다.  
  
-   **단순 매개 변수 형식입니다.** 간단 하 게 복잡 한 매개 변수 형식을 사용 하지 않음으로써 합니다. 메서드를 입력 매개 변수 없음 만들거나 간단한 입력된 형식을 문자열, 기본 형식 등을 수행 하는 대신 합니다.  
  
-   **팩터리 메서드입니다.** 일부 유형은 인스턴스화가 까다롭습니다. 팩터리 메서드에 대 한 확장으로 제공 하는 `My` 네임 스페이스를 사용 하면 보다 쉽게 검색 하 고이 범주에 해당 하는 형식을 사용할 수 있습니다. 효과적으로 작동 하는 팩터리 메서드의 예로 `My.Computer.FileSystem.OpenTextFileReader`합니다. .NET Framework에서 사용할 수 있는 스트림 유형은 여러 가지가 있습니다. 특히, 텍스트 파일을 지정 하 여는 `OpenTextFileReader` 는 사용자가 사용할 스트림을 이해 하는 데 도움이 됩니다.  
  
 이러한 지침에서 클래스 라이브러리에 대 한 일반적인 디자인 원칙을 방해 하지 않습니다. 대신, Visual Basic을 사용 하는 개발자를 위한 최적화 된 권장 사항은 및 `My` 네임 스페이스입니다. 클래스 라이브러리를 만들기 위한 일반적인 디자인 원칙을 참조 하십시오. [Framework 디자인 지침](../../../standard/design-guidelines/index.md)합니다.  
  
##  <a name="packaging"></a> 확장 패키징 및 배포  
 포함할 수 있습니다 `My` 하거나 Visual Studio 프로젝트 템플릿 네임 스페이스 확장은 확장 프로그램을 패키지 하 고 Visual Studio 항목 템플릿 배포 합니다. 패키징할 때 프로그램 `My` Visual Studio 항목 템플릿 네임 스페이스 확장, Visual Basic에서 제공 하는 추가 기능을 활용 걸릴 수 있습니다. 이러한 기능을 특정 어셈블리를 참조 하는 프로젝트 확장을 포함 하거나 사용자가을 명시적으로 추가할 사용자 `My` 를 사용 하 여 네임 스페이스 확장의 **My 확장** Visual Basic의 페이지 프로젝트 디자이너입니다.  
  
 자세한 내용은 배포 하는 방법에 대 한 `My` 네임 스페이스 확장 참조 [패키징 및 배포 사용자 지정 My 확장](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 My 확장명 패키징 및 배포](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 [Visual Basic 응용 프로그램 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [My에 사용할 수 있는 개체 사용자 지정](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [프로젝트 디자이너, my 확장 페이지](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)  
 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [부분](../../../visual-basic/language-reference/modifiers/partial.md)
