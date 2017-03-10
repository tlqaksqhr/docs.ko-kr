---
title: "Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30961"
  - "bc30961"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30961"
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

'\<typename1\>' 형식의 값을 '\<typename2\>'\(으\)로 변환할 수 없습니다.'\<projectname1\>' 프로젝트의 '\<filepath1\>'에 대한 파일 참조와 \<projectname2\>' 프로젝트의 '\<filepath2\>'에 대한 파일 참조가 섞여 있어 형식이 일치하지 않을 수도 있습니다.두 어셈블리가 동일한 경우 두 참조를 동일한 위치에서 가져오도록 해당 참조를 바꿔야 합니다.  
  
 프로젝트에서 하나의 어셈블리에 대한 여러 파일 참조를 작성하는 경우 컴파일러는 한 형식이 다른 형식으로 변환될 수 있는 것으로 보장할 수 없습니다.  
  
 각 파일 참조는 프로젝트의 출력 파일\(일반적으로 DLL 파일\)에 대한 파일 경로와 이름을 지정합니다.  컴파일러는 출력 파일의 소스가 동일하거나 동일한 어셈블리의 동일한 버전을 나타내는 것으로 보장할 수 없습니다.  따라서 다른 참조의 형식이 동일한 형식이거나 하나의 형식이 다른 형식으로 변환될 수 있는 것으로 보장할 수 없습니다.  
  
 참조된 어셈블리의 어셈블리 ID가 동일한 경우 단일 파일 참조를 사용할 수 있습니다.  *어셈블리 ID*에는 어셈블리의 이름, 버전, 공개 키가 있는 경우 해당 키 및 문화권이 포함됩니다.  이 정보는 어셈블리를 고유하게 식별합니다.  
  
 **오류 ID:** BC30961  
  
### 이 오류를 해결하려면  
  
-   참조된 어셈블리의 어셈블리 ID가 동일한 경우 단일 파일 참조만 남도록 파일 참조 중 하나를 제거하거나 바꿉니다.  
  
-   참조된 어셈블리의 어셈블리 ID가 서로 다른 경우 다른 어셈블리 형식으로의 어셈블리 형식 변환을 시도하지 않도록 코드를 변경합니다.  
  
## 참고 항목  
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)   
 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)