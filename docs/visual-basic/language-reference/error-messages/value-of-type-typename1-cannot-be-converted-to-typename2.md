---
title: "Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30955"
  - "bc30955"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30955"
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<typename1\>' 형식의 값을 '\<typename2\>'\(으\)로 변환할 수 없습니다.형식 불일치는 '\<assemblyname\>' 어셈블리에 대한 프로젝트 참조와 파일 참조가 섞여 있기 때문일 수 있습니다.'\<projectname1\>' 프로젝트의 '\<filepath\>'에 대한 파일 참조를 '\<projectname2\>'에 대한 프로젝트 참조로 바꿔 보십시오.  
  
 프로젝트가 프로젝트 참조와 파일 참조를 모두 만드는 경우 컴파일러에서 반드시 한 형식을 다른 형식으로 변환할 수 있는 것은 아닙니다.  
  
 다음 의사\(pseudo\) 코드에서는 이러한 오류를 생성할 수 있는 상황을 보여 줍니다.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 `P1` 프로젝트는 `P2` 프로젝트를 통해 `P3` 프로젝트에 대한 간접 프로젝트 참조를 만들며 `P3`에 대한 직접 파일 참조도 만듭니다.  `commonObject` 선언에서는 `P3`에 대한 파일 참조를 사용하지만 `P2.getCommonClass`에 대한 호출에서는 `P3`에 대한 프로젝트 참조를 사용합니다.  
  
 이러한 상황에서의 문제점은 파일 참조가 `P3`의 출력 파일\(일반적으로 p3.dll\)에 대한 파일 경로와 이름을 지정하지만 프로젝트 참조는 프로젝트 이름으로 소스 프로젝트\(`P3`\)를 식별한다는 데 있습니다.  이 때문에 컴파일러는 `P3.commonClass` 형식이 두 개의 다른 참조를 통해 동일한 소스 코드에서 온 것임을 보장할 수 없습니다.  
  
 이러한 상황은 일반적으로 프로젝트 참조와 파일 참조를 함께 사용하는 경우 발생합니다.  위의 예제에서 `P1`이 파일 참조 대신 `P3`에 대한 직접 프로젝트 참조를 만들면 문제가 발생하지 않습니다.  
  
 **오류 ID:** BC30955  
  
### 이 오류를 해결하려면  
  
-   프로젝트 참조에 대한 파일 참조를 변경합니다.  
  
## 참고 항목  
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)   
 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)