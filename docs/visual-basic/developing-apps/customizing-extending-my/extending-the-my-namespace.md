---
title: "확장은 Visual Basic에서 My Namespace | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddingMyExtensions
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1d1e957536f35b81a9672994c9d4d261afb764ea
ms.lasthandoff: 03/13/2017

---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Visual Basic에서 My 네임스페이스 확장
`My` Visual Basic의 네임 스페이스의.NET Framework의 강력한 쉽게 활용할 수 있도록 하는 메서드와 속성을 노출 합니다. `My` 네임 스페이스는 어려운 작업이 줄어들 코드 한 줄으로 일반적인 프로그래밍 문제를 단순화 합니다. 또한는 `My` 동작을 사용자 지정할 수 있도록 네임 스페이스는 완벽 한 확장성 `My` 에 특정 응용 프로그램 요구에 맞게 해당 계층 구조에 새 서비스를 추가 하 고 있습니다. 이 항목에서는 기존 멤버의 사용자 지정 하는 `My` 네임 스페이스 및 사용자 지정 클래스를 추가 하는 방법을 `My` 네임 스페이스.  
  
 **항목 내용**  
  
-   [기존 내 Namespace 멤버 사용자 지정](#customizing)  
  
-   [My 개체에 멤버 추가](#addingtoobjects)  
  
-   [사용자 지정 개체를 추가 My Namespace](#addingcustom)  
  
-   [에 멤버 추가 My Namespace](#addingtonamespace)  
  
-   [사용자 지정 My 개체에 이벤트 추가](#addingevents)  
  
-   [디자인 지침](#design)  
  
-   [에 대 한 클래스 라이브러리 디자인 내](#designing)  
  
-   [확장 패키징 및 배포](#packaging)  
  
##  <a name="customizing"></a>기존 내 Namespace 멤버 사용자 지정  
 `My` 자주 사용 하는 응용 프로그램, 컴퓨터, 등 하는 방법에 대 한 정보 노출 Visual Basic에서에서 네임 스페이스입니다. 에 있는 개체의 전체 목록은 `My` 네임 스페이스 참조 [내 참조](../../../visual-basic/language-reference/keywords/my-reference.md)합니다. 기존 멤버를 사용자 지정 해야 할 수 있습니다는 `My` 네임 스페이스 향상 될 수 있도록 응용 프로그램의 요구와 일치 합니다. 에 있는 개체의 모든 속성은 `My` 읽기 전용으로 설정 되지 않은 네임 스페이스는 사용자 지정 값으로 설정할 수 있습니다.  
  
 예를 들어, 자주 사용 하 여 `My.User` 응용 프로그램을 실행 하는 사용자에 대 한 현재 보안 컨텍스트에 액세스 하는 개체입니다. 그러나 회사는 회사 내 사용자에 대 한 기능 및 추가 정보를 노출 하는 사용자 지정 사용자 개체를 사용 합니다. 이 시나리오에서의 기본값을 바꿀 수는 `My.User.CurrentPrincipal` 다음 예제에 나온 것 처럼 사용자 고유의 사용자 지정 보안 주체 개체의 인스턴스를 사용 하 여 속성입니다.  
  
 [!code-vb[VbVbcnExtendingMy #&1;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 설정의 `CurrentPrincipal` 속성에는 `My.User` 개체가 응용 프로그램이 실행 되는 id를 변경 합니다. `My.User` 개체를 새로 지정 된 사용자에 대 한 정보를 반환 합니다.  
  
##  <a name="addingtoobjects"></a>My 개체에 멤버 추가  
 반환 된 형식은 `My.Application` 및 `My.Computer` 으로 정의 된 `Partial` 클래스입니다. 따라서, 확장할 수 있습니다는 `My.Application` 및 `My.Computer` 개체를 만들어 한 `Partial` 라는 클래스 `MyApplication` 또는 `MyComputer`합니다. 클래스는 될 수 없습니다는 `Private` 클래스입니다. 클래스의 일부로 지정 하는 경우는 `My` 네임 스페이스와 함께 제공 되는 메서드와 속성을 추가할 수 없다는 `My.Application` 또는 `My.Computer` 개체입니다.  
  
 다음 예제에서는 라는 속성을 추가 하는 예를 들어 `DnsServerIPAddresses` 에 `My.Computer` 개체입니다.  
  
 [!code-vb[VbVbcnExtendingMy #&2;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a>사용자 지정 개체를 추가 My Namespace  
 있지만 `My` 작업이 있을 수 있습니다, 네임 스페이스는 여러 일반 프로그래밍 작업에 대 한 솔루션을 제공 하는 `My` 네임 스페이스는 다루지 않습니다. 예를 들어, 응용 프로그램 사용자 데이터에 대 한 사용자 지정 디렉터리 서비스에 액세스할 수 또는 응용 프로그램에서 Visual Basic에 대해 기본적으로 설치 되지 않은 어셈블리를 사용할 수 있습니다. 확장할 수는 `My` 환경에 관련 된 일반적인 작업에 대 한 사용자 지정 솔루션을 포함 하도록 네임 스페이스입니다. `My` 네임 스페이스 증가 하는 응용 프로그램 요구를 충족 하기 위해 새 멤버를 추가 하도록 쉽게 확장할 수 있습니다. 배포할 수는 또한 프로그램 `My` Visual Basic 템플릿으로 다른 개발자에 게 네임 스페이스 확장 합니다.  
  
###  <a name="addingtonamespace"></a>에 멤버 추가 My Namespace  
 때문에 `My` 네임 스페이스가 같은 다른 네임 스페이스를 추가할 수 있습니다 최상위 속성에는 모듈을 추가 하 고 지정 하 여 한 `Namespace` 의 `My`합니다. 주석을 사용 하 여 모듈의 `HideModuleName` 다음 예와에서 같이 특성입니다. `HideModuleName` 특성의 멤버를 표시 하는 경우 IntelliSense가 모듈 이름을 표시 되도록 할 수는 `My` 네임 스페이스입니다.  
  
 [!code-vb[VbVbcnExtendingMy #&3;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 멤버를 추가 하는 `My` 네임 스페이스를 모듈에 필요에 따라 속성을 추가 합니다. 에 추가 된 각 속성에 대 한는 `My` 네임 스페이스를 유형의 private 필드를 추가 `ThreadSafeObjectProvider(Of T)`, 형식이 사용자 지정 속성에서 반환 되는 형식입니다. 이 필드는 스레드로부터 안전한 개체를 호출 하 여 속성에 의해 반환 되는 인스턴스를 만드는 데 사용 되는 `GetInstance` 메서드. 결과적으로, 확장된 속성에 액세스 하는 각 스레드에 반환 된 형식의 고유 인스턴스를 받습니다. 다음 예제에서는 라는 속성을 추가 `SampleExtension` 형식의 `SampleExtension` 에 `My` 네임 스페이스:  
  
 [!code-vb[VbVbcnExtendingMy #&4;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a>사용자 지정 My 개체에 이벤트 추가  
 사용할 수는 `My.Application` 사용자 지정에 대 한 이벤트를 노출 하는 개체 `My` 확장 하 여 개체는 `MyApplication` 의 partial 클래스는 `My` 네임 스페이스. Windows 기반 프로젝트를 두 번 있습니다는 **My Project** 에서 프로젝트 노드를에서 **솔루션 탐색기**합니다. Visual Basic에서 **프로젝트 디자이너**, 클릭는 `Application` 탭 클릭 한 후의 `View Application Events` 단추입니다. ApplicationEvents.vb 라는 새 파일을 생성 됩니다. 확장을 위한 다음 코드가 포함 된 `MyApplication` 클래스입니다.  
  
 [!code-vb[VbVbcnExtendingMy #&5;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 사용자 지정에 대 한 이벤트 처리기를 추가할 수 있습니다 `My` 사용자 지정 이벤트 처리기를 추가 하 여 개체는 `MyApplication` 클래스입니다. 사용자 지정 이벤트에서 이벤트 처리기 추가, 제거, 또는 이벤트가 발생할 때 실행할 코드를 추가할 수 있도록 합니다. `AddHandler` 코드 사용자 지정 이벤트는 이벤트를 처리 하는 사용자가 코드를 추가한 경우에 실행 합니다. 예를 들어, 다음을 고려해 야는 `SampleExtension` 이전 섹션에서 개체에는 `Load` 이벤트에 대 한 사용자 지정 이벤트 처리기를 추가 하려면입니다. 다음 코드 예제에서는 라는 사용자 지정 이벤트 처리기를 보여 줍니다. `SampleExtensionLoad` 그 정도면 될 때 호출 되는 `My.SampleExtension.Load` 이벤트가 발생 합니다. 새 처리 하기 위해 코드 추가 때 `My.SampleExtensionLoad` 이벤트는 `AddHandler` 부분에서는이 사용자 지정 이벤트 코드가 실행 됩니다. `MyApplication_SampleExtensionLoad` 메서드를 처리 하는 이벤트 처리기의 예제를 보여는 코드 예제에 포함 됩니다는 `My.SampleExtensionLoad` 이벤트입니다. `SampleExtensionLoad` 이벤트를 선택 하면 사용할 수 있습니다는 **내 응용 프로그램 이벤트** 코드 편집기 위의 ApplicationEvents.vb 파일을 편집 하는 경우 왼쪽된 드롭 다운 목록에서 옵션입니다.  
  
 [!code-vb[VbVbcnExtendingMy #&6;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a>디자인 지침  
 에 대 한 확장을 개발 하는 경우는 `My` 네임 스페이스를 확장 구성 요소의 유지 관리 비용을 최소화 하기 위해 다음 지침을 따르십시오.  
  
-   **확장 논리만 포함 됩니다.** 에 포함 된 논리는 `My` 네임 스페이스 확장에 필요한 기능을 노출 하는 데 필요한 코드만 포함 해야는 `My` 네임 스페이스입니다. 확장 프로그램은 소스 코드로 사용자 프로젝트에 위치 합니다, 때문에 확장 구성 요소 업데이트 높은 유지 관리 비용이 발생 피해 야 합니다 가능한 경우.  
  
-   **프로젝트 가정을 최소화 합니다.** 확장을 만들 때의 `My` 네임 스페이스, 참조, 프로젝트 수준의 imports 또는 특정 컴파일러 설정의 집합을 가정 하지 마십시오 (예를 들어 `Option Strict` 해제) 합니다. 대신 종속성을 최소화 하 고 사용 하 여 모든 형식 참조를 정규화는 `Global` 키워드입니다. 또한 확장 된 컴파일되는지 확인 해야 `Option Strict` 확장에 대 한 오류를 최소화 하에 있습니다.  
  
-   **확장 코드를 격리 합니다.** 단일 파일에 코드를 넣거나 하면 확장 프로그램을 Visual Studio 항목 템플릿으로 쉽게 배포할 수 있습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "확장 패키징 및 배포"를 참조 하십시오. 모든 배치는 `My` 네임 스페이스 확장 코드를 단일 파일 또는 프로젝트에서 별도 폴더에도 도움이 됩니다 찾은 사용자는 `My` 네임 스페이스 확장 합니다.  
  
##  <a name="designing"></a>에 대 한 클래스 라이브러리 디자인 내  
 대부분의 개체 모델의 경우 처럼 일부 디자인 패턴에서 잘 작동 하는 `My` 네임 스페이스와 다른 하지 않습니다. 에 대 한 확장 디자인 하는 경우는 `My` 네임 스페이스를 원칙은 다음과:  
  
-   **상태 비저장 메서드입니다.** 메서드는 `My` 네임 스페이스는 특정 작업에 완벽 한 솔루션을 제공 해야 합니다. 메서드에 전달 되는 매개 변수 값은 특정 작업을 완료 하는 데 필요한 모든 입력을 제공 하는지 확인 합니다. 리소스에 대 한 열린 연결 등의 이전 상태를 사용 하는 메서드를 만들지 마십시오.  
  
-   **전역 인스턴스입니다.** 유지 관리 되는 유일한 상태는 `My` 네임 스페이스 전체 프로젝트에 적용 됩니다. 예를 들어 `My.Application.Info` 응용 프로그램에 걸쳐 공유 되는 상태를 캡슐화 합니다.  
  
-   **간단한 매개 변수 형식입니다.** 간단 하 게 복잡 한 매개 변수 형식을 사용 하지 않음으로써 합니다. 입력 매개 변수가 하나 사용 하는 메서드와 만들거나 간단한 입력된 형식을 문자열, 기본 형식 등을 수행 하는 대신 합니다.  
  
-   **팩터리 메서드입니다.** 일부 유형은 인스턴스화가 까다롭습니다. 팩터리 메서드에 대 한 확장으로 제공 하는 `My` 네임 스페이스를 사용 하면 보다 쉽게 검색 하 고이 범주에 해당 하는 형식을 사용할 수 있습니다. 잘 작동 하는 팩터리 메서드의 예로 `My.Computer.FileSystem.OpenTextFileReader`합니다. .NET Framework에서 사용할 수 있는 스트림 유형은 여러 가지가 있습니다. 특히, 텍스트 파일을 지정 하 여는 `OpenTextFileReader` 는 사용자가 사용할 스트림을 이해 하는 데 도움이 됩니다.  
  
 이러한 지침은 클래스 라이브러리에 대 한 일반적인 디자인 원칙을 방해 하지 않습니다. 대신, 이러한은 Visual Basic을 사용 하는 개발자를 위한 최적화 된 권장 사항 및 `My` 네임 스페이스입니다. 클래스 라이브러리를 만들기 위한 일반적인 디자인 원칙에 대 한 참조 [Framework 디자인 지침](http://msdn.microsoft.com/library/5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b)합니다.  
  
##  <a name="packaging"></a>확장 패키징 및 배포  
 포함할 수 있습니다 `My` Visual Studio 프로젝트 템플릿 또는 사용자에서 네임 스페이스 확장 프로그램 확장을 패키지화 하 고 Visual Studio 항목 템플릿으로 배포 수 있습니다. 패키징할 때 프로그램 `My` 네임 스페이스 확장을 Visual Studio 항목 템플릿으로, Visual Basic에서 제공 하는 추가 기능을 걸릴 수 있습니다. 이러한 기능을 프로젝트는 특정 어셈블리를 참조 하는 경우 확장을 포함 하거나 사용자가 명시적으로 추가할 수 여 `My` 를 사용 하 여 네임 스페이스 확장은 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.  
  
 배포 하는 방법에 대 한 자세한 `My` 네임 스페이스 확장 참조 [패키징 및 배포 사용자 지정 My 확장](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [패키징 및 배포 사용자 지정 My 확장](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)   
 [Visual Basic 응용 프로그램 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [사용자 지정 하는 개체는 지원 되는 내](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [프로젝트 디자이너, my 확장 페이지](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)   
 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [부분](../../../visual-basic/language-reference/modifiers/partial.md)
