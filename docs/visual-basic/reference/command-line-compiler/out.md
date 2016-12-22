---
title: "/out (Visual Basic) | Microsoft Docs"
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
  - "/out compiler option [Visual Basic]"
  - "-out compiler option [Visual Basic]"
  - "out compiler option [Visual Basic]"
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /out (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

출력 파일의 이름을 지정합니다.  
  
## 구문  
  
```  
/out:filename  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`filename`|필수 요소.  컴파일러가 만드는 출력 파일의 이름입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.|  
  
## 설명  
 만들 파일의 전체 이름과 확장명을 지정합니다.  지정하지 않을 경우, .exe 파일은 `Sub Main` 프로시저를 포함하는 소스 코드 파일에서 이름을 가져오고 .dll 파일은 첫째 소스 코드 파일에서 이름을 가져옵니다.  
  
 .exe 또는 .dll 확장명 없이 파일 이름을 지정할 경우 컴파일러는 `/target` 컴파일러 옵션에 지정된 값에 따라 확장명을 자동으로 추가합니다.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/out을 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  **어셈블리 이름** 상자의 값을 수정합니다.|  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하고 출력 파일 `T2.exe`를 만듭니다.  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)