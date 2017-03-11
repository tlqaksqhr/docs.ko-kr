---
title: "Extending the My Namespace in Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AddingMyExtensions"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My namespace, customizing"
  - "My namespace"
  - "My namespace, extending"
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Extending the My Namespace in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic의 `My` 네임스페이스는 .NET Framework의 강력한 기능을 쉽게 사용할 수 있게 해 주는 속성과 메서드를 노출합니다.  `My` 네임스페이스를 사용하면 일반적인 프로그래밍 문제가 간단하게 해결되므로 까다로운 작업이 코드 한 줄로 줄어들 수 있습니다.  또한 `My` 네임스페이스는 완전히 확장 가능하기 때문에 특정한 응용 프로그램의 요구 사항에 맞게 `My`의 동작을 사용자 지정하고 계층 구조에 새 서비스를 추가할 수 있습니다.  이 항목에서는 `My` 네임스페이스의 기존 멤버를 사용자 지정하는 방법과 사용자 지정 클래스를 `My` 네임스페이스에 추가하는 방법을 설명합니다.  
  
 **항목 내용**  
  
-   [기존 My 네임스페이스 멤버 사용자 지정](#customizing)  
  
-   [My 개체에 멤버 추가](#addingtoobjects)  
  
-   [My 네임스페이스에 사용자 지정 개체 추가](#addingcustom)  
  
-   [My 네임스페이스에 멤버 추가](#addingtonamespace)  
  
-   [사용자 지정 My 개체에 이벤트 추가](#addingevents)  
  
-   [디자인 지침](#design)  
  
-   [My에 대한 클래스 라이브러리 디자인](#designing)  
  
-   [확장 패키징 및 배포](#packaging)  
  
##  <a name="customizing"></a> 기존 My 네임스페이스 멤버 사용자 지정  
 Visual Basic의 `My` 네임스페이스는 응용 프로그램, 컴퓨터 등에 대한 자주 사용되는 정보를 노출합니다.  `My` 네임스페이스에 있는 개체의 전체 목록을 보려면 [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md)를 참조하십시오.  `My` 네임스페이스의 기존 멤버를 응용 프로그램의 요구 사항에 맞게 사용자 지정할 수 있습니다.  `My` 네임스페이스에서 읽기 전용이 아닌 모든 개체 속성을 사용자 지정 값으로 설정할 수 있습니다.  
  
 예를 들어 응용 프로그램을 실행하는 사용자의 현재 보안 컨텍스트에 액세스하기 위해 `My.User` 개체를 자주 사용한다고 가정해 보겠습니다.  하지만 회사에서는 사용자 지정된 사용자 개체를 사용하여 회사 내 사용자에 대한 추가적인 정보와 기능을 노출합니다.  이 경우 다음 예제에서처럼 `My.User.CurrentPrincipal` 속성의 기본값을 사용자 지정 Principal 개체의 인스턴스로 바꿀 수 있습니다.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/visualbasic/extending-the-my-namespace_1.vb)]  
  
 `My.User` 개체에 `CurrentPrincipal` 속성을 설정하면 응용 프로그램 실행에 사용되는 ID가 변경됩니다.  그러면 `My.User` 개체는 새로 지정된 사용자에 대한 정보를 반환합니다.  
  
##  <a name="addingtoobjects"></a> My 개체에 멤버 추가  
 `My.Application` 및 `My.Computer`에서 반환된 형식은 `Partial` 클래스로 정의됩니다.  따라서 `MyApplication` 또는 `MyComputer`라는 `Partial` 클래스를 만들어 `My.Application` 및`My.Computer` 개체를 확장할 수 있습니다.  클래스는 `Private` 클래스일 수 없습니다.  클래스를 `My` 네임스페이스의 일부로 지정하면 `My.Application` 또는 `My.Computer` 개체와 함께 포함될 속성과 메서드를 추가할 수 있습니다.  
  
 예를 들어 다음 예제에서는 `My.Computer` 개체에 `DnsServerIPAddresses`라는 속성을 추가합니다.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/visualbasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> My 네임스페이스에 사용자 지정 개체 추가  
 `My` 네임스페이스는 다양한 일반적인 프로그래밍 작업에 대한 솔루션을 제공하지만 `My` 네임스페이스로 해결되지 않는 작업이 있을 수 있습니다.  예를 들어 응용 프로그램이 사용자 데이터를 위해 사용자 지정 디렉터리 서비스에 액세스하거나 Visual Basic과 함께 기본적으로 설치되지 않는 어셈블리를 사용해야 할 수 있습니다.  `My` 네임스페이스를 확장하여 각각의 환경에서 일반적으로 수행되는 작업에 대한 사용자 지정 솔루션을 포함할 수 있습니다.  응용 프로그램의 요구 사항이 늘어남에 따라 `My` 네임스페이스를 확장하여 새 멤버를 추가할 수 있습니다.  또한 `My` 네임스페이스 확장을 Visual Basic 템플릿 형태로 다른 개발자에게 배포할 수 있습니다.  
  
###  <a name="addingtonamespace"></a> My 네임스페이스에 멤버 추가  
 `My` 네임스페이스는 다른 네임스페이스와 비슷한 특징을 가지고 있기 때문에 모듈을 추가하고 `My`의 `Namespace`를 지정하여 최상위 속성을 추가할 수 있습니다.  다음 예제에서처럼 `HideModuleName` 특성으로 모듈에 주석을 지정합니다.  `HideModuleName` 특성을 사용하면 IntelliSense에서 `My` 네임스페이스의 멤버를 표시할 때 모듈 이름이 표시되지 않습니다.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/visualbasic/extending-the-my-namespace_3.vb)]  
  
 `My` 네임스페이스에 멤버를 추가하려면 모듈에 필요한 속성을 추가해야 합니다.  `My` 네임스페이스에 추가된 각 속성에 대해 `ThreadSafeObjectProvider(Of T)` 형식의 private 필드를 추가합니다. 여기서 형식은 사용자 지정 속성에서 반환된 형식입니다.  이 필드는 `GetInstance` 메서드 호출을 통해 속성에서 반환되는, 스레드로부터 안전한 개체 인스턴스를 만드는 데 사용됩니다.  따라서 확장된 속성에 액세스하는 각 스레드는 반환된 형식의 자체 인스턴스를 수신합니다.  다음 예제에서는 `SampleExtension` 형식의 `SampleExtension`이라는 속성을 `My` 네임스페이스에 추가합니다.  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/visualbasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> 사용자 지정 My 개체에 이벤트 추가  
 `My.Application` 개체를 사용하여 `My` 네임스페이스의 `MyApplication` partial 클래스를 확장하여 사용자 지정 `My` 개체에 대한 이벤트를 노출할 수 있습니다.  Windows 기반 프로젝트의 경우 **솔루션 탐색기**에서 프로젝트에 대한 **내 프로젝트** 노드를 두 번 클릭할 수 있습니다.  Visual Basic **프로젝트 디자이너**에서는 `Application` 탭을 클릭한 다음 `View Application Events` 단추를 클릭합니다.  그러면 이름이 ApplicationEvents.vb인 새 파일이 만들어집니다.  이 파일에는 `MyApplication` 클래스를 확장하는 다음과 같은 코드가 들어 있습니다.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/visualbasic/extending-the-my-namespace_5.vb)]  
  
 `MyApplication` 클래스에 사용자 지정 이벤트 처리기를 추가하여 사용자 지정 `My` 개체에 대한 이벤트 처리기를 추가할 수 있습니다.  사용자 지정 이벤트를 사용하면 이벤트 처리기가 추가 또는 제거되거나 이벤트가 발생했을 때 실행되는 코드를 추가할 수 있습니다.  사용자 지정 이벤트에 대한 `AddHandler` 코드는 사용자가 이벤트 처리를 위해 코드를 추가한 경우에만 실행됩니다.  예를 들어 이전 단원에서 설명한 `SampleExtension` 개체에 사용자 지정 이벤트 처리기를 추가하려고 하는 `Load` 이벤트가 있다고 가정해 보겠습니다.  다음 코드 예제에서는 `My.SampleExtension.Load` 이벤트가 발생할 때 호출될 `SampleExtensionLoad`라는 사용자 지정 이벤트 처리기를 보여 줍니다.  새 `My.SampleExtensionLoad` 이벤트를 처리하기 위한 코드가 추가되면 이 사용자 지정 이벤트 코드의 `AddHandler` 부분이 실행됩니다.  `MyApplication_SampleExtensionLoad` 메서드는 `My.SampleExtensionLoad` 이벤트를 처리하는 이벤트 처리기의 예제를 보여 주기 위해 코드 예제에 포함되었습니다.  `SampleExtensionLoad` 이벤트는 ApplicationEvents.vb 파일을 편집할 때 코드 편집기 위에 있는 왼쪽 드롭다운 목록에서 **내 응용 프로그램 이벤트** 옵션을 선택한 경우에 사용할 수 있습니다.  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/visualbasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> 디자인 지침  
 `My` 네임스페이스에 대한 확장을 개발할 때 다음 지침을 사용하면 확장 구성 요소의 유지 관리 비용을 최소화할 수 있습니다.  
  
-   **확장 논리만 포함합니다.** `My` 네임스페이스 확장에 포함된 논리에는 필요한 `My` 네임스페이스 기능을 노출하는 데 필요한 코드만 포함되어야 합니다.  확장은 사용자 프로젝트에 소스 코드로 존재하기 때문에 높은 유지 관리 비용을 발생시킬 수 있는 확장 구성 요소의 업데이트는 되도록이면 피해야 합니다.  
  
-   **프로젝트 가정을 최소화합니다.** `My` 네임스페이스의 확장을 만들 때 참조, 프로젝트 수준 가져오기 또는 특정 컴파일러 설정\(예를 들어 `Option Strict` 해제\) 집합을 가정하지 마십시오.  대신 `Global` 키워드를 사용하여 종속성을 최소화하고 모든 형식 참조를 정규화하십시오.  또한 오류를 최소화하기 위해 `Option Strict`를 사용하여 확장을 컴파일하십시오.  
  
-   **확장 코드를 격리합니다.** 코드를 하나의 파일에 넣으면 확장을 Visual Studio 항목 템플릿으로 손쉽게 배포할 수 있습니다.  자세한 내용은 이 항목 뒷부분의 "확장 패키징 및 배포"를 참조하십시오.  모든 `My` 네임스페이스 확장 코드를 프로젝트에서 하나의 파일 또는 별도 폴더에 넣으면 사용자가 `My` 네임스페이스 확장을 더 수월하게 찾을 수 있습니다.  
  
##  <a name="designing"></a> My에 대한 클래스 라이브러리 디자인  
 대부분의 개체 모델과 마찬가지로 `My` 네임스페이스에서 잘 작동하는 디자인 패턴도 있고 그렇지 않은 디자인 패턴도 있습니다.  `My` 네임스페이스에 대한 확장을 디자인할 때는 다음 원칙을 고려하십시오.  
  
-   **상태 비저장 메서드.** `My` 네임스페이스의 메서드는 특정 작업에 완전한 솔루션을 제공해야 합니다.  메서드에 전달되는 매개 변수 값은 특정 작업을 수행하는 데 필요한 모든 입력을 제공해야 합니다.  리소스에 대한 열려 있는 연결과 같이 이전 상태를 사용하는 메서드는 만들지 않는 것이 좋습니다.  
  
-   **전역 인스턴스.** `My` 네임스페이스에서 유지되는 유일한 상태는 프로젝트에 대해 전역입니다.  예를 들어 `My.Application.Info`는 응용 프로그램 전체에서 공유되는 상태를 캡슐화합니다.  
  
-   **간단한 매개 변수 형식.** 복잡한 매개 변수 형식을 피하고 단순하게 유지해야 합니다.  매개 변수 입력을 받지 않거나 문자열이나 기본 형식 같은 간단한 입력 형식을 받는 메서드를 만드십시오.  
  
-   **팩터리 메서드.** 일부 형식은 인스턴스화가 까다롭습니다.  팩터리 메서드를 `My` 네임스페이스에 확장으로 제공하면 이 범주에 속하는 형식을 더 쉽게 발견하고 사용할 수 있습니다.  제대로 작동하는 팩터리 메서드의 예는 `My.Computer.FileSystem.OpenTextFileReader`입니다.  .NET Framework에서는 몇 개의 스트림 형식을 사용할 수 있습니다.  텍스트 파일을 지정한 경우 `OpenTextFileReader`는 사용자가 사용할 스트림을 이해하는 데 도움을 줍니다.  
  
 이 지침은 클래스 라이브러리에 대한 일반 디자인 원칙과 대치되지 않는,  Visual Basic과 `My` 네임스페이스를 사용하는 개발자를 위해 최적화된 권장 사항입니다.  클래스 라이브러리 만들기에 대한 일반적인 디자인 원칙에 대해서는 [프레임 워크 디자인 지침](../Topic/Framework%20Design%20Guidelines.md)을 참조하십시오.  
  
##  <a name="packaging"></a> 확장 패키징 및 배포  
 `My` 네임스페이스 확장은 Visual Studio 프로젝트 템플릿에 포함하거나 패키지하여, Visual Studio 항목 템플릿으로 배포할 수 있습니다.  `My` 네임스페이스 확장을 Visual Studio 항목 템플릿으로 패키지할 때는 Visual Basic이 제공하는 추가적인 기능을 활용할 수 있습니다.  이러한 기능을 통해 프로젝트가 특정 어셈블리를 참조할 때 확장을 포함하거나, 사용자가 Visual Basic 프로젝트 디자이너의 **My 확장** 페이지를 사용하여 `My` 네임스페이스 확장을 명시적으로 추가할 수 있습니다.  
  
 `My` 네임스페이스 확장을 배포하는 방법에 대한 자세한 내용은 [Packaging and Deploying Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)를 참조하십시오.  
  
## 참고 항목  
 [Packaging and Deploying Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)   
 [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [프로젝트 디자이너, My 확장 페이지](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)   
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)