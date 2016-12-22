---
title: "/resource (Visual Basic) | Microsoft Docs"
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
  - "/resource compiler option [Visual Basic]"
  - "-resource compiler option [Visual Basic]"
  - "/res compiler option [Visual Basic]"
  - "res compiler option [Visual Basic]"
  - "-res compiler option [Visual Basic]"
  - "resource compiler option [Visual Basic]"
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /resource (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

관리되는 리소스를 어셈블리에 포함합니다.  
  
## 구문  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`filename`|필수 요소.  출력 파일에 포함할 리소스 파일의 이름입니다.  기본적으로 `filename`은 어셈블리에서 public 파일입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.|  
|`identifier`|선택적 요소.  리소스의 논리적 이름, 즉 리소스를 로드하는 데 사용되는 이름입니다.  기본값은 파일 이름입니다.  어셈블리 매니페스트에서 리소스가 공용 리소스인지 개인 리소스인지 지정할 수도 있습니다\(예: `/res:``filename.res`,`myname.res`,`public`\).|  
  
## 설명  
 리소스 파일을 출력 파일에 넣지 않고 리소스를 어셈블리에 링크하려면 `/linkresource`를 사용하십시오.  
  
 `filename`이 개발 환경에서 또는 [Resgen.exe\(리소스 파일 생성기\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)를 사용하여 만든 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일인 경우 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 이 파일에 액세스할 수 있습니다. 자세한 내용은 <xref:System.Resources.ResourceManager>를 참조하십시오.  다른 모든 리소스에 런타임에 액세스하려면 <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> 메서드 중 하나를 사용합니다.  
  
 `/res`는 `/resource` 의 약식 표현입니다.  
  
 설정 하는 방법에 대 한 내용은 `/resource` Visual Studio IDE를 참조 하십시오. [응용 프로그램 리소스 관리\(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
## 예제  
 다음 코드에서는 `In.vb`를 컴파일하고 리소스 파일 `Rf.resource`에 연결합니다.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)