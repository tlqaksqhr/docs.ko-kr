---
title: 어셈블리와 전역 어셈블리 캐시(Visual Basic)
ms.date: 07/20/2015
ms.assetid: fcf78ff1-f1ab-4a5d-b6d8-00d2046b6c80
ms.openlocfilehash: 6d1692d6b62e1f1f3a8f979d3de242003f034ed5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="assemblies-and-the-global-assembly-cache-visual-basic"></a>어셈블리와 전역 어셈블리 캐시(Visual Basic)
어셈블리는 .NET 기반 응용 프로그램에 대한 배포, 버전 제어, 재사용, 활성화 범위 및 보안 권한의 기본 단위를 형성합니다. 어셈블리는 실행 파일(.exe) 또는 동적 연결 라이브러리(.dll) 파일의 형태를 가지며 .NET Framework의 구성 요소입니다. 어셈블리는 형식 구현을 인식하는 데 필요한 정보와 함께 공용 언어 런타임을 제공합니다. 어셈블리를 함께 작동하도록 빌드되고 논리적 기능 단위를 형성하는 리소스 및 형식 컬렉션으로 생각할 수 있습니다.  
  
 어셈블리에는 하나 이상의 모듈이 포함될 수 있습니다. 예를 들어 여러 개별 개발자가 별도 모듈로 작업하다가 함께 모여 단일 어셈블리를 만드는 방식으로 대규모 프로젝트를 계획할 수 있습니다. 모듈에 대한 자세한 내용은 [방법: 다중 파일 어셈블리 빌드](../../../../framework/app-domains/how-to-build-a-multifile-assembly.md)를 참조하세요.  
  
 어셈블리에는 다음과 같은 속성이 있습니다.  
  
-   어셈블리는 .exe 또는 .dll 파일로 구현됩니다.  
  
-   어셈블리를 전역 어셈블리 캐시에 저장하면 응용 프로그램 간에 공유할 수 있습니다. 어셈블리를 전역 어셈블리 캐시에 넣으려면 강력한 이름이 지정되어야 합니다. 자세한 내용은 [강력한 이름의 어셈블리](../../../../framework/app-domains/strong-named-assemblies.md)를 참조하세요.  
  
-   어셈블리는 필요한 경우에만 메모리에 로드됩니다. 사용되지 않을 때는 로드되지 않습니다. 즉, 어셈블리는 대규모 프로젝트에서 리소스를 관리하는 효율적인 방법일 수 있습니다.  
  
-   리플렉션을 사용하여 프로그래밍 방식으로 어셈블리에 대한 정보를 얻을 수 있습니다. 자세한 내용은 [리플렉션(Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)을 참조하세요.  
  
-   검사할 어셈블리만 로드하려면 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 같은 메서드를 사용합니다.  
  
## <a name="assembly-manifest"></a>어셈블리 매니페스트  
 모든 어셈블리 내에는 *어셈블리 매니페스트*가 있습니다. 목차와 마찬가지로, 어셈블리 매니페스트에는 다음이 포함됩니다.  
  
-   어셈블리의 ID(해당 이름 및 버전).  
  
-   어셈블리를 구성하는 다른 모든 파일을 설명하는 파일 테이블(예: 사용자의 .exe 또는 .dll 파일이 의존하는 사용자가 만든 다른 모든 어셈블리 또는 비트맵이나 추가 정보 파일)  
  
-   *어셈블리 참조 목록*: 누군가가 만들었을 수 있으며 사용자의 응용 프로그램에 필요한 .dlls 또는 기타 파일을 비롯한 모든 외부 종속성 목록 어셈블리 참조는 global 및 private 개체에 대한 참조를 포함합니다. global 개체는 System32 디렉터리 등과 같이 다른 응용 프로그램에서 사용할 수 있는 영역인 전역 어셈블리 캐시에 상주합니다. <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임스페이스는 전역 어셈블리 캐시의 어셈블리에 대한 예입니다. private 개체는 응용 프로그램이 설치된 디렉터리와 같거나 낮은 수준에 있는 디렉터리에 있어야 합니다.  
  
 어셈블리는 콘텐츠, 버전 관리 및 종속성에 대한 정보를 포함하므로 Visual Basic으로 만드는 응용 프로그램은 제대로 작동하기 위해 Windows 레지스트리 값에 의존하지 않습니다. 어셈블리는 .dll 충돌을 줄이고 더 안정적이고 배포하기 쉬운 응용 프로그램을 구현합니다. 많은 경우에 해당 파일을 대상 컴퓨터에 복사하는 것만으로 .NET 기반 응용 프로그램을 설치할 수 있습니다.  
  
 자세한 내용은 [어셈블리 매니페스트](../../../../framework/app-domains/assembly-manifest.md)를 참조하세요.  
  
## <a name="adding-a-reference-to-an-assembly"></a>어셈블리에 대한 참조 추가  
 어셈블리를 사용하려면 해당 참조를 추가해야 합니다. 다음에는 [Imports 문](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 사용하여 사용하려는 항목의 네임스페이스를 선택합니다. 어셈블리를 참조하고 가져오면 해당 코드가 소스 파일에 속해 있는 것처럼 해당 네임스페이스의 액세스 가능한 모든 클래스, 속성, 메서드 및 다른 멤버를 응용 프로그램에서 사용할 수 있습니다.  
  
## <a name="creating-an-assembly"></a>어셈블리 만들기  
 명령줄 컴파일러를 사용하여 명령줄에서 빌드하는 방식으로 응용 프로그램을 컴파일합니다. 명령줄에서 어셈블리를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)를 참조하세요.  
  
> [!NOTE]
>  Visual Studio에서 어셈블리를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공용 언어 런타임의 어셈블리](../../../../framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Friend 어셈블리 (Visual Basic)](friend-assemblies.md)  
 [방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유](how-to-share-an-assembly-with-other-applications.md)  
 [방법: 어셈블리 로드 및 언로드 (Visual Basic)](how-to-load-and-unload-assemblies.md)  
 [방법: 파일 어셈블리 (Visual Basic) 인지 확인 합니다.](how-to-determine-if-a-file-is-an-assembly.md)  
 [방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용](how-to-create-and-use-assemblies-using-the-command-line.md)  
 [연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함](walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
 [연습: Visual Studio에서 Microsoft Office 어셈블리의 형식 정보 포함(Visual Basic)](walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-vs.md)
