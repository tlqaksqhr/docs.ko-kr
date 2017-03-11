---
title: "/linkresource (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/linkresource compiler option [Visual Basic]"
  - "-linkresource compiler option [Visual Basic]"
  - "linkresource compiler option [Visual Basic]"
  - "/linkres compiler option [Visual Basic]"
  - "linkres compiler option [Visual Basic]"
  - "-linkres compiler option [Visual Basic]"
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /linkresource (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

관리되는 리소스에 대한 링크를 만듭니다.  
  
## 구문  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## 인수  
 `filename`  
 필수 요소.  어셈블리에 연결할 리소스 파일입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.  
  
 `identifier`  
 선택적 요소.  리소스에 대한 논리 이름으로,  리소스를 로드할 때 사용됩니다.  기본값은 파일 이름입니다.  어셈블리 매니페스트에서 파일이 공용 파일인지 개인 파일인지를 지정할 수도 있습니다\(예: `/linkres:filename.res,myname.res,public`\).  기본적으로 `filename`은 어셈블리에서 public 파일입니다.  
  
## 설명  
 `/linkresource` 옵션은 출력 파일에 리소스 파일을 포함하지 않습니다. 리소스 파일을 포함시키려면 `/resource` 옵션을 사용하십시오.  
  
 `/linkresource` 옵션을 사용하려면 `/target:module`이 아니라 `/target` 옵션 중 하나가 필요합니다.  
  
 `filename`이 [Resgen.exe\(리소스 파일 생성기\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)를 사용하여 만들었거나 개발 환경에서 만든 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 리소스 파일인 경우 이 파일은 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 액세스할 수 있습니다.  자세한 내용은 <xref:System.Resources.ResourceManager>을 참조하십시오. 런타임에 다른 모든 리소스에 액세스하려면 <xref:System.Reflection.Assembly>에서 `GetManifestResource`로 시작하는 메서드를 사용하십시오.  
  
 파일 이름에는 모든 형식의 파일을 지정할 수 있습니다.  예를 들어, 어셈블리의 네이티브 dll 부분을 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있도록 만들 수 있습니다.  
  
 `/linkresource`의 약식 표현은 `/linkres`입니다.  
  
> [!NOTE]
>  `/linkresource` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 `In.vb`를 컴파일하여 리소스 파일 `Rf.resource`에 연결합니다.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)