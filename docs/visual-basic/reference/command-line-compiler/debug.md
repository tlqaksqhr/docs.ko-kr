---
title: "/debug (Visual Basic) | Microsoft Docs"
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
  - "debug compiler switches"
  - "/debug compiler option [Visual Basic]"
  - "-debug compiler option [Visual Basic]"
  - "debug compiler option [Visual Basic]"
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /debug (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러가 디버깅 정보를 생성하여 출력 파일에 저장합니다.  
  
## 구문  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`+`  &#124; `-`|선택적 요소.  `+`나 `/debug`를 지정하면 컴파일러가 디버깅 정보를 생성하여 .pdb 파일에 저장합니다.  `-`를 지정하는 것은 `/debug`를 지정하지 않는 것과 같습니다.|  
|`full`  &#124; `pdbonly`|선택적 요소.  컴파일러에서 생성하는 디버깅 정보의 형식을 지정합니다.  `/debug:pdbonly`를 지정하지 않으면 기본값은 `full`입니다. 즉, 디버거를 실행 중인 프로그램에 연결할 수 있습니다.  `pdbonly`를 지정하면 디버거에서 프로그램을 시작할 때 소스 코드를 디버깅할 수 있지만 실행 중인 프로그램을 디버거에 연결할 때만 어셈블리 언어가 표시됩니다.|  
  
## 설명  
 이 옵션을 사용하면 디버그 빌드를 만들 수 있습니다.  `/debug`, `/debug+` 또는 `/debug:full`을 지정하지 않으면 프로그램의 출력 파일을 디버깅할 수 없습니다.  
  
 기본값으로 `/debug-`가 지정되어 있어서 디버깅 정보가 생성되지 않습니다.  디버깅 정보를 생성하려면 `/debug` 또는 `/debug+`를 지정합니다.  
  
 응용 프로그램의 디버그 성능을 구성하는 방법에 대한 내용은 [쉽게 디버깅할 수 있도록 이미지 만들기](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md)를 참조하십시오.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/debug를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급 컴파일 옵션**을 클릭합니다.<br />4.  **디버그 정보 생성** 상자에서 값을 수정합니다.|  
  
## 예제  
 다음 예제에서는 출력 파일 `App.exe`에 디버깅 정보를 저장합니다.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)