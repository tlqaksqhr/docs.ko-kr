---
title: "/win32manifest (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/win32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/win32manifest compiler option [C#]"
  - "win32manifest compiler option [C#]"
  - "-win32manifest compiler option [C#]"
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /win32manifest (C# Compiler Options)
**\/win32manifest** 옵션을 사용하여 프로젝트의 PE 파일\(이식 가능 파일\)에 포함할 사용자 정의 Win32 응용 프로그램 매니페스트 파일을 지정합니다.  
  
## 구문  
  
```  
/win32manifest: filename  
```  
  
## 인수  
 `filename`  
 사용자 지정 매니페스트 파일의 이름 및 위치입니다.  
  
## 설명  
 기본적으로 [!INCLUDE[csharp_current_short](../../../csharp/language-reference/compiler-options/includes/csharp-current-short-md.md)] 컴파일러는 "asInvoker"의 요청되는 실행 수준을 지정하는 응용 프로그램 매니페스트를 포함합니다. 실행 파일이 작성되는 폴더와 동일한 폴더에 매니페스트가 생성됩니다. Visual Studio를 사용하는 경우 일반적으로 bin\\Debug 또는 bin\\Release 폴더에 생성됩니다.  예를 들어 "highestAvailable" 또는 "requireAdministrator" 의 요청된 실행 수준을 지정하기 위해, 사용자 지정 매니페스트를 제공하려면, 이 옵션을 사용하여 파일 이름을 지정합니다.  
  
> [!NOTE]
>  이 옵션과 [\/win32res \(Import a Win32 Resource File\)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) 옵션은 함께 사용할 수 없습니다.  동일한 명령줄에서 두 가지 옵션을 모두 사용하는 경우 빌드 오류가 발생합니다.  
  
 요청되는 실행 수준을 지정하는 응용 프로그램 매니페스트가 없는 응용 프로그램에는 Windows Vista의 사용자 계정 컨트롤 기능에 있는 파일\/레지스트리 가상화가 적용됩니다.  가상화에 대한 자세한 내용은 다음을 참조하십시오. [The Windows Vista Developer Story: Windows Vista Application Development Requirements for User Account Control \(UAC\)](http://go.microsoft.com/fwlink/?LinkId=95452).  
  
 다음 조건 중 하나에 해당되면 응용 프로그램에 가상화가 적용됩니다.  
  
-   **\/nowin32manifest** 옵션을 사용하며, **\/win32res** 옵션을 사용하여 이후 빌드 단계에서 또는 Windows 리소스 파일\(.res\)의 일부로 매니페스트를 제공하지 않는 경우  
  
-   요청되는 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공하는 경우  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서는 기본 .manifest 파일을 만들어 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다.  텍스트 편집기에서 사용자 지정 매니페스트를 만들어 추가한 다음 프로젝트에 파일을 추가할 수 있습니다.  또는 **솔루션 탐색기**의 **프로젝트** 아이콘을 마우스 오른쪽 단추로 클릭한 후 **새 항목 추가**를 클릭한 다음 **응용 프로그램 매니페스트 파일**을 클릭할 수 있습니다.  새 매니페스트 또는 기존 매니페스트 파일을 추가하면 **매니페스트** 드롭다운 목록에 표시됩니다.  자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp)을 참조하십시오.  
  
 [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) 옵션을 사용하여 응용 프로그램 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다.  응용 프로그램에 Windows Vista의 파일 또는 레지스트리 가상화를 적용하려는 경우 동일한 옵션을 사용합니다.  이렇게 하면 컴파일러가 PE 파일\(이식 가능 파일\)에서 기본 매니페스트를 만들고 포함할 수 없습니다.  
  
## 예제  
 다음 예제에서는 Visual C\# 컴파일러가 PE에 삽입하는 기본 매니페스트를 보여 줍니다.  
  
> [!NOTE]
>  컴파일러는 표준 응용 프로그램 이름인 "MyApplications.app"를 xml에 삽입합니다.  이렇게 하면 Windows Server 2003 서비스 팩 3에서 응용 프로그램을 실행할 수 있습니다.  
  
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
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)