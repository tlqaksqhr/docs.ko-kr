---
title: "/libpath | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "libpath compiler option [Visual Basic]"
  - "/libpath compiler option [Visual Basic]"
  - "-libpath compiler option [Visual Basic]"
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /libpath
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

참조된 어셈블리의 위치를 지정합니다.  
  
## 구문  
  
```  
/libpath:dirList  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`dirList`|필수 요소.  참조된 어셈블리가 현재 작업 디렉터리\(컴파일러를 호출하는 디렉터리\)나 공용 언어 런타임의 시스템 디렉터리에 없는 경우 컴파일러가 찾는 디렉터리의 세미콜론으로 구분된 목록입니다.  디렉터리 이름에 공백이 포함되어 있는 경우 이름을 따옴표\(" "\)로 묶습니다.|  
  
## 설명  
 `/libpath` 옵션은 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md) 옵션에 의해 참조되는 어셈블리의 위치를 지정합니다.  
  
 컴파일러에서는 정규화된 경로에 없는 어셈블리 참조를 다음 순서에 따라 검색합니다.  
  
1.  현재 작업 디렉터리.  컴파일러를 실행한 디렉터리입니다.  
  
2.  공용 언어 런타임 시스템 디렉터리  
  
3.  `/libpath`에서 지정한 디렉터리  
  
4.  LIB 환경 변수에서 지정한 디렉터리  
  
 `/libpath` 옵션은 계속 추가할 수 있는 옵션이며 이 옵션을 두 번 이상 지정하면 이전 값에 추가됩니다.  
  
 어셈블리 참조를 지정하려면 `/reference`를 사용합니다.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/libpath를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **참조** 탭을 클릭합니다.<br />3.  **참조 경로...** 단추를 클릭합니다.<br />4.  **참조 경로** 대화 상자의 **폴더:** 상자에 디렉터리 이름을 입력합니다.<br />5.  **폴더 추가**를 클릭합니다.|  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하여 .exe 파일을 만듭니다.  컴파일러에서는 작업 디렉터리, C: 드라이브의 루트 디렉터리 및 C: 드라이브의 새 어셈블리 디렉터리에서 어셈블리 참조를 찾습니다.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## 참고 항목  
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)