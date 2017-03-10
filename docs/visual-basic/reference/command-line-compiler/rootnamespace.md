---
title: "/rootnamespace | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/rootnamespace"
  - "rootnamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/rootnamespace compiler option [Visual Basic]"
  - "-rootnamespace compiler option [Visual Basic]"
  - "rootnamespace compiler option [Visual Basic]"
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /rootnamespace
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

모든 형식 선언을 위한 네임스페이스를 지정합니다.  
  
## 구문  
  
```  
/rootnamespace:namespace  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`namespace`|현재 프로젝트에 대한 모든 형식 선언을 포함할 네임스페이스의 이름입니다.|  
  
## 설명  
 Visual Studio 실행 파일\(Devenv.exe\)을 사용하여 Visual Studio 통합 개발 환경에서 만든 프로젝트를 컴파일하려면 `/rootnamespace`를 사용하여 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> 속성 값을 지정합니다.  자세한 내용은 [Devenv 명령줄 스위치](/visual-studio/ide/reference/devenv-command-line-switches)를 참조하십시오.  
  
 공용 언어 런타임 MSIL Disassembler\(I`ldasm.exe`\)를 사용하면 출력 파일에 있는 네임스페이스 이름을 볼 수 있습니다.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/rootnamespace를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  **루트 네임스페이스** 상자의 값을 수정합니다.|  
  
## 예제  
 다음 코드에서는 `In.vb`를 컴파일하고 `mynamespace` 네임스페이스에 있는 모든 형식 선언을 포함합니다.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe\(IL 디스어셈블러\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)