---
title: "/reference (Visual Basic) | Microsoft Docs"
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
  - "/reference compiler option [Visual Basic]"
  - "r compiler option [Visual Basic]"
  - "-reference compiler option [Visual Basic]"
  - "/r compiler option [Visual Basic]"
  - "reference compiler option [Visual Basic]"
  - "-r compiler option [Visual Basic]"
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컴파일러가 지정된 어셈블리의 형식 정보를 현재 컴파일 중인 프로젝트에서 사용할 수 있도록 만듭니다.  
  
## 구문  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`fileList`|필수 요소.  쉼표로 구분된 어셈블리 파일 이름입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표로 묶습니다.|  
  
## 설명  
 가져오는 파일에 어셈블리 메타데이터가 들어 있어야 합니다.  어셈블리 외부에서는 public 형식만 볼 수 있습니다.  [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션은 모듈에서 메타데이터를 가져옵니다.  
  
 다른 어셈블리\(Assembly B\)를 참조하는 어셈블리\(Assembly A\)를 참조할 때 다음과 같은 경우에는 Assembly B를 참조해야 합니다.  
  
-   Assembly A에서 사용하는 형식이 Assembly B의 형식에서 상속되었거나 Assembly B의 인터페이스로 구현된 경우  
  
-   Assembly B의 반환 형식이나 매개 변수 형식의 필드, 속성, 이벤트 또는 메서드를 호출하는 경우  
  
 하나 이상의 어셈블리 참조가 있는 디렉터리를 지정하려면 [\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)를 사용합니다.  
  
 컴파일러에서 모듈이 아닌 어셈블리의 형식을 인식하려면 형식을 확인하도록 컴파일러가 지정되어야 합니다.  형식을 확인하도록 지정하는 방법으로는 형식의 인스턴스를 정의하는 방법이 있습니다.  컴파일러는 다른 방법으로도 어셈블리에서 형식 이름을 확인할 수 있습니다.  예를 들어, 어셈블리에서 특정 형식을 상속하면 해당 형식 이름이 컴파일러에 알려집니다.  
  
 일반적으로 사용되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리를 참조하는 Vbc.rsp 지시 파일이 기본적으로 사용됩니다.  컴파일러에서 Vbc.rsp를 사용하지 않도록 하려면 `/noconfig`를 사용합니다.  
  
 `/r`는 `/reference` 의 약식 표현입니다.  
  
## 예제  
 다음 코드에서는 소스 파일 I`nput.vb`를 컴파일한 다음 M`etad1.dll`과 M`etad2.dll`로부터 어셈블리를 참조하여 O`ut.exe`를 생성합니다.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)