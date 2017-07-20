---
title: "/win32manifest(C# 컴파일러 옵션) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: bb28bf28c3d8a426322e1c1795941de7e9aa4bf6
ms.openlocfilehash: fd8c0a9a398c8f8d6c589ffcf0426a375a82a6a8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/03/2017

---
# <a name="win32manifest-c-compiler-options"></a>/win32manifest(C# 컴파일러 옵션)
프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 응용 프로그램 매니페스트 파일을 식별하려면 **/win32manifest** 옵션을 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/win32manifest: filename  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 사용자 지정 매니페스트 파일의 이름 및 위치입니다.  
  
## <a name="remarks"></a>설명  
 기본적으로 [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] 컴파일러는 "asInvoker"의 요청된 실행 수준을 지정하는 응용 프로그램 매니페스트를 포함합니다. 실행 파일이 작성되는 폴더에 매니페스트가 생성됩니다. Visual Studio를 사용하는 경우 대개 bin\Debug 또는 bin\Release 폴더입니다. 예를 들어 "highestAvailable" 또는 "requireAdministrator"의 요청된 실행 수준을 지정하기 위해 사용자 지정 매니페스트를 제공하려면 이 옵션을 사용하여 파일 이름을 지정합니다.  
  
> [!NOTE]
>  이 옵션과 [/win32res(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) 옵션은 함께 사용할 수 없습니다. 같은 명령줄에서 두 옵션을 모두 사용하려고 하면 빌드 오류가 발생합니다.  
  
 요청된 실행 수준을 지정하는 응용 프로그램 매니페스트가 없는 응용 프로그램은 Windows Vista의 사용자 계정 컨트롤 기능 아래에서 파일/레지스트리 가상화의 적용을 받습니다. 가상화에 대한 자세한 내용은 [Windows Vista 개발자 스토리: UAC(사용자 계정 컨트롤)에 대한 Windows Vista 응용 프로그램 개발 요구 사항](http://go.microsoft.com/fwlink/?LinkId=95452)을 참조하세요.  
  
 다음 조건 중 하나라도 참인 경우 응용 프로그램에 가상화가 적용됩니다.  
  
-   사용자는 **/nowin32manifest** 옵션을 사용하며, **/win32res** 옵션을 사용하여 나중 빌드 단계 또는 Windows Resource(.res) 파일의 일부로 매니페스트를 제공하지 않습니다.  
  
-   요청한 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공합니다.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]는 기본 .manifest 파일을 만들고 이를 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다. 텍스트 편집기에서 파일을 만들고 프로젝트에 파일을 추가하여 사용자 지정 매니페스트를 추가할 수 있습니다. 또는 **솔루션 탐색기**에서 **프로젝트** 아이콘을 마우스 오른쪽 단추로 클릭하고, **새 항목 추가**와 **응용 프로그램 매니페스트 파일**을 차례로 클릭합니다. 신규 또는 기존 매니페스트 파일을 추가하면 **매니페스트** 드롭다운 목록에 나타납니다. 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(C#)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.  
  
 [/nowin32manifest(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) 옵션을 사용하여 응용 프로그램 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다. 응용 프로그램이 Windows Vista에서 파일 또는 레지스트리 가상화의 적용을 받도록 하려면 동일한 옵션을 사용합니다. 이렇게 하면 컴파일러가 PE(이식 가능한 실행 파일) 파일에 기본 매니페스트를 만들고 포함할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 Visual C# 컴파일러가 PE에 삽입하는 기본 매니페스트를 보여 줍니다.  
  
> [!NOTE]
>  컴파일러는 표준 응용 프로그램 이름인 "MyApplication.app"을 xml에 삽입합니다. 이는 Windows Server 2003 서비스 팩 3에서 응용 프로그램을 실행하기 위한 해결 방법입니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [-nowin32manifest(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
