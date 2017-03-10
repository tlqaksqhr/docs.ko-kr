---
title: "/baseaddress | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/baseaddress"
  - "baseaddress"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-baseaddress compiler option [Visual Basic]"
  - "/baseaddress compiler option [Visual Basic]"
  - "baseaddress compiler option [Visual Basic]"
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /baseaddress
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

DLL을 만들 때 기본 기준 주소를 지정합니다.  
  
## 구문  
  
```  
/baseaddress:address  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`address`|필수 요소.  DLL의 기준 주소입니다.  이 주소는 16진수 숫자로 지정해야 합니다.|  
  
## 설명  
 DLL의 기본 기준 주소는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]에 의해 설정됩니다.  
  
 이 주소의 하위 단어는 반올림됩니다.  예를 들어, 0x11110001을 지정할 경우 0x11110000으로 반올림됩니다.  
  
 DLL에 대한 서명 프로세스를 완료하려면 강력한 명명 도구\(Sn.exe\)를 `–R` 옵션과 함께 사용합니다.  
  
 대상이 DLL이 아닌 경우 이 옵션은 무시됩니다.  
  
||  
|-|  
|Visual Studio IDE에서 \/baseaddress를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급**을 클릭합니다.<br />4.  **DLL 기준 주소:** 상자의 값을 수정합니다. **Note:**      대상이 DLL이 아니면 **DLL 기준 주소:** 상자는 읽기 전용입니다.|  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)