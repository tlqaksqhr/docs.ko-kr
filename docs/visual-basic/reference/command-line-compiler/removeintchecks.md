---
title: "/removeintchecks | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "removeintchecks"
  - "/removeintchecks"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "removeintchecks compiler option [Visual Basic]"
  - "/removeintchecks compiler option [Visual Basic]"
  - "-removeintchecks compiler option [Visual Basic]"
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /removeintchecks
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

정수 연산에 대한 오버플로 오류 검사를 설정하거나 해제합니다.  
  
## 구문  
  
```  
/removeintchecks[+ | -]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`+`  &#124; `-`|선택적 요소.  `/removeintchecks-` 옵션 되도록 컴파일러가 모든 정수 연산 오버플로 오류를 확인 합니다.  기본값은 `/removeintchecks-`입니다.<br /><br /> `/removeintchecks` 또는 `/removeintchecks+`를 지정하면 오류를 검사하지 않으므로 정수 계산을 더욱 빠르게 할 수 있습니다.  그러나 오류 검사를 사용하지 않으면 데이터 형식 용량이 오버플로되더라도 오류가 발생하지 않아 부정확한 결과가 저장될 수 있습니다.|  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/removeintchecks를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  **정수 오버플로 검사 해제** 상자의 값을 수정합니다.|  
  
## 예제  
 다음 코드에서는 `Test.vb`를 컴파일하고 정수 오버플로 오류 검사 설정을 해제합니다.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)