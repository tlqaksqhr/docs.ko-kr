---
title: "/nowarn | Microsoft Docs"
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
  - "nowarn compiler option [Visual Basic]"
  - "/nowarn compiler option [Visual Basic]"
  - "-nowarn compiler option [Visual Basic]"
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /nowarn
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

경고를 생성하는 컴파일러 기능을 비활성화합니다.  
  
## 구문  
  
```  
/nowarn[:numberList]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`numberList`|선택적 요소.  컴파일러에서 표시하지 않을 경고 ID 번호를 쉼표로 구분한 목록입니다.  경고 ID를 지정하지 않으면 모든 경고가 표시되지 않습니다.|  
  
## 설명  
 `/nowarn` 옵션을 사용하면 컴파일러에서 경고가 생성되지 않습니다.  개별 경고를 표시하지 않으려면 해당 경고 ID를 콜론 다음의 `/nowarn` 옵션에 지정합니다.  경고 번호는 각각 쉼표로 구분합니다.  
  
 경고 식별자의 숫자 부분만 지정해야 합니다.  예를 들어, 사용되지 않는 지역 변수에 대한 경고인 BC42024를 표시하지 않으려면 `/nowarn:42024`를 지정합니다.  
  
 경고 ID 번호에 대한 자세한 내용은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/nowarn을 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **모든 경고 사용 안 함** 확인란을 선택하여 모든 경고를 비활성화합니다.<br />     \-또는\-<br />     특정 경고를 사용하지 않으려면 해당 경고 옆의 드롭다운 목록에서 **없음**을 클릭합니다.|  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하며 경고를 표시하지 않습니다.  
  
```  
vbc /nowarn t2.vb  
```  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하며 사용되지 않는 지역 변수에 대한 경고\(42024\)를 표시하지 않습니다.  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)