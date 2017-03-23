---
title: "/win32manifest (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b07d5816e5bb80a95e608fa7214a2db48ebac0dc
ms.lasthandoff: 03/13/2017

---
# <a name="win32manifest-visual-basic"></a>/win32manifest(Visual Basic)
프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 응용 프로그램 매니페스트 파일을 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`fileName`|사용자 지정 매니페스트 파일의 경로입니다.|  
  
## <a name="remarks"></a>주의  
 기본적으로 Visual Basic 컴파일러는 asInvoker의 요청 된 실행 수준을 지정 하는 응용 프로그램 매니페스트를 포함 합니다. 실행 파일이 작성 되는, 일반적으로 bin\Debug 또는 bin\Release 폴더 Visual Studio를 사용 하는 경우 동일한 폴더에 매니페스트가 생성 됩니다. 예를 들어 requireAdministrator 또는 highestAvailable의 요청 된 실행 수준을 지정 하려면 사용자 지정 매니페스트를 제공 하려는 경우 파일의 이름을 지정 하려면이 옵션을 사용 합니다.  
  
> [!NOTE]
>  이 옵션 및 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) 옵션은 함께 사용할 수 없습니다. 동일한 명령줄에서 두 옵션을 사용 하려고 하면 빌드 오류가 얻게 됩니다.  
  
 매니페스트는 응용 프로그램이 있는 응용 프로그램을 Windows Vista의 사용자 계정 컨트롤 기능 파일/레지스트리 가상화는 요청 된 실행 수준이 됩니다 지정 합니다. 가상화에 대 한 자세한 내용은 참조 [Windows Vista의 ClickOnce 배포](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista)합니다.  
  
 다음 조건 중 하나에 해당 하는 경우에 응용 프로그램 가상화가 적용 됩니다.  
  
1.  사용 된 `/nowin32manifest` 옵션을 할 수 없으며 Windows 리소스 (.res) 파일의 일부 또는 이후 빌드 단계에서 매니페스트를 사용 하 여는 `/win32resource` 옵션입니다.  
  
2.  요청된 된 실행 수준을 지정 하지 않는 사용자 지정 매니페스트를 제공 합니다.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]기본.manifest 파일을 만들고 실행 파일과 함께 디버그 및 릴리스 디렉터리에 저장 합니다. 보거나 클릭 하 여 기본 app.manifest 파일을 편집할 수 있습니다 **UAC 설정 보기** 에 **응용 프로그램** 프로젝트 디자이너 탭 합니다. 자세한 내용은 참조 [응용 프로그램 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)합니다.  
  
 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 사용 하 여 응용 프로그램 매니페스트를 제공할 수는 `/nowin32manifest` 옵션입니다. 응용 프로그램을 Windows Vista에서 파일 또는 레지스트리 가상화 하려는 경우 동일한 옵션을 사용 합니다. 이렇게 하면 컴파일러에서 만들고 기본 매니페스트는 PE 파일에 포함 되지 것입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 Visual Basic 컴파일러는 PE 삽입 기본 매니페스트를 보여 줍니다.  
  
> [!NOTE]
>  컴파일러는 XML 매니페스트에 표준 응용 프로그램 이름 MyApplication.app를 삽입합니다. Windows Server 2003 서비스 팩 3에서 실행할 응용 프로그램을 사용 하도록 설정 하는 해결 방법입니다.  
  
```  
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
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
