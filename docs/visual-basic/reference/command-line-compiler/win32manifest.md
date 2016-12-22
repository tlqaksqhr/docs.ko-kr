---
title: "/win32manifest (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32manifest compiler option [Visual Basic]"
  - "win32manifest compiler option [Visual Basic]"
  - "-win32manifest compiler option [Visual Basic]"
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

프로젝트의 PE 파일\(이식 가능한 실행 파일\)에 포함할 사용자 정의 Win32 응용 프로그램 매니페스트 파일을 지정합니다.  
  
## 구문  
  
```  
/win32manifest: fileName  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`fileName`|사용자 지정 매니페스트 파일의 경로입니다.|  
  
## 설명  
 기본적으로 Visual Basic 컴파일러는 asInvoker의 요청되는 실행 수준을 지정하는 응용 프로그램 매니페스트를 포함합니다.  실행 파일이 작성되는 폴더와 동일한 폴더에 매니페스트가 생성됩니다. Visual Studio를 사용하는 경우 일반적으로 bin\\Debug 또는 bin\\Release 폴더에 생성됩니다.  예를 들어 highestAvailable 또는 requireAdministrator의 요청되는 실행 수준을 지정하기 위해 사용자 지정 매니페스트를 제공하려면 이 옵션을 사용하여 파일 이름을 지정합니다.  
  
> [!NOTE]
>  이 옵션과 [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) 옵션은 함께 사용할 수 없습니다.  동일한 명령줄에서 두 가지 옵션을 모두 사용하는 경우 빌드 오류가 발생합니다.  
  
 요청되는 실행 수준을 지정하는 응용 프로그램 매니페스트가 없는 응용 프로그램에는 Windows Vista의 사용자 계정 컨트롤 기능에 있는 파일\/레지스트리 가상화가 적용됩니다.  가상화에 대한 자세한 내용은 [Windows Vista의 ClickOnce 배포](/visual-studio/deployment/clickonce-deployment-on-windows-vista)를 참조하십시오.  
  
 다음 조건 중 하나가 참이면 응용 프로그램에 가상화가 적용됩니다.  
  
1.  `/nowin32manifest` 옵션을 사용하며, `/win32resource` 옵션을 사용하여 이후 빌드 단계에서 또는 Windows 리소스 파일\(.res\)의 일부로 매니페스트를 제공하지 않는 경우  
  
2.  요청되는 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공하는 경우  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]에서는 기본 .manifest 파일을 만들어 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다.  프로젝트 디자이너의 **응용 프로그램** 탭에서 **UAC 설정 보기**를 클릭하면 기본 app.manifest 파일을 보거나 편집할 수 있습니다. 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)를 참조하십시오.  
  
 `/nowin32manifest` 옵션을 사용하여 응용 프로그램 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다.  응용 프로그램에 Windows Vista의 파일 또는 레지스트리 가상화를 적용하려는 경우 동일한 옵션을 사용합니다.  그러면 컴파일러가 PE 파일\(이식 가능 파일\)에서 기본 매니페스트를 만들고 포함시키는 것을 방지할 수 있습니다.  
  
## 예제  
 다음 예제에서는 Visual Basic 컴파일러가 PE에 삽입하는 기본 매니페스트를 보여 줍니다.  
  
> [!NOTE]
>  컴파일러는 표준 응용 프로그램 이름 MyApplications.app를 매니페스트 XML에 삽입합니다.  이렇게 하면 Windows Server 2003 서비스 팩 3에서 응용 프로그램을 실행할 수 있습니다.  
  
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
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)