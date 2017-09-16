---
title: "방법: COM 래퍼 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e99b084ddb565a8ae00ee917eaf7fca2c659ab64
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-create-com-wrappers"></a>방법: COM 래퍼 만들기
[!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] 기능이나 .NET Framework 도구인 Tlbimp.exe 및 Regasm.exe를 사용하여 COM(구성 요소 개체 모델) 래퍼를 만들 수 있습니다. 두 메서드는 모두 COM 래퍼의 두 가지 형식을 생성합니다.  
  
-   관리 코드에서 COM 개체를 실행하기 위한 형식 라이브러리의 [런타임 호출 가능 래퍼](../../../docs/framework/interop/runtime-callable-wrapper.md).  
  
-   네이티브 응용 프로그램에서 관리 개체를 실행하기 위한 필수 레지스트리 설정이 포함된 [COM 호출 가능 래퍼](../../../docs/framework/interop/com-callable-wrapper.md).  
  
 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에서 프로젝트에 COM 래퍼를 참조로 추가할 수 있습니다.  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a>관리되는 응용 프로그램에서 COM 개체 래핑  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a>Visual Studio를 사용하여 런타임 호출 가능 래퍼를 만들려면  
  
1.  관리되는 응용 프로그램에 대한 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.  
  
3.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
4.  [참조 추가] 대화 상자에서 **COM** 탭을 클릭하고, 사용할 구성 요소를 선택하고, **확인**을 클릭합니다.  
  
     **솔루션 탐색기**에서 COM 구성 요소는 프로젝트의 참조 폴더에 추가됩니다.  
  
 이제 COM 개체에 액세스하기 위한 코드를 작성할 수 있습니다. 먼저 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]의 경우 `Imports` 문을 사용하고 [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)]의 경우 `Using` 문을 사용하여 개체를 선언할 수 있습니다.  
  
> [!NOTE]
>  Microsoft Office 구성 요소를 프로그래밍하려면 먼저 Microsoft 다운로드 센터에서 [Microsoft Office PIA](http://go.microsoft.com/fwlink/?LinkId=50479)(주 Interop 어셈블리)를 설치합니다. 4단계에서는 **Microsoft Word 11.0 개체 라이브러리**와 같이 원하는 Office 제품에 사용 가능한 최신 버전의 개체 라이브러리를 선택합니다.  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a>.NET Framework 도구를 사용하여 런타임 호출 가능 래퍼를 만들려면  
  
-   [Tlbimp.exe(형식 라이브러리 가져오기)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 도구를 실행합니다.  
  
 이 도구는 원본 형식 라이브러리에 정의된 형식의 런타임 메타데이터를 포함하는 어셈블리를 만듭니다.  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a>네이티브 응용 프로그램에서 관리 개체 래핑  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a>Visual Studio를 사용하여 COM 호출 가능 래퍼를 만들려면  
  
1.  네이티브 코드에서 실행할 관리되는 클래스에 대한 클래스 라이브러리 프로젝트를 만듭니다. 이 클래스에는 기본 생성자가 있어야 합니다.  
  
     AssemblyInfo 파일에 어셈블리에 대한 전체 4개 부분 버전 번호가 있는지 확인합니다. Windows 레지스트리에서 버전을 유지 관리하려면 이 번호가 필요합니다. 버전 번호에 대한 자세한 내용은 [어셈블리 버전 관리](../../../docs/framework/app-domains/assembly-versioning.md)를 참조하세요.  
  
2.  **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
3.  **컴파일** 탭을 클릭합니다.  
  
4.  **COM interop 등록** 확인란을 선택합니다.  
  
 프로젝트를 빌드하면 COM interop에 대한 어셈블리가 자동으로 등록됩니다. [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에서 네이티브 응용 프로그램을 빌드할 경우 **프로젝트** 메뉴에서 **참조 추가**를 클릭하여 어셈블리를 사용할 수 있습니다.  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a>.NET Framework 도구를 사용하여 COM 호출 가능 래퍼를 만들려면  
  
-   [Regasm.exe(어셈블리 등록 도구)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) 도구를 실행합니다.  
  
 이 도구는 어셈블리 메타데이터를 읽고 레지스트리에 필요한 항목을 추가합니다. 따라서 COM 클라이언트는 .NET Framework 클래스를 투명하게 만들 수 있습니다. 네이티브 COM 클래스인 것처럼 어셈블리를 사용할 수 있습니다.  
  
 디렉터리에 있는 어셈블리에서 Regasm.exe를 실행하고 나서 [Gacutil.exe(전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 실행하여 어셈블리를 전역 어셈블리 캐시로 이동합니다. 어셈블리가 다른 곳에 있는지 항상 전역 어셈블리 캐시가 검사되므로 어셈블리를 이동해도 위치 레지스트리 항목이 무효화되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임 호출 가능 래퍼](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM 호출 가능 래퍼](../../../docs/framework/interop/com-callable-wrapper.md)

