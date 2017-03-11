---
title: "Visual Basic Limitations | Microsoft Docs"
ms.custom: ""
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
  - "limits"
  - "limitations, Visual Basic"
  - "limitations"
  - "limits, Visual Basic code"
  - "Visual Basic code, limitations"
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Visual Basic Limitations
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이전 버전의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 변수 이름 길이, 모듈에 허용되는 변수의 개수, 모듈 크기 등의 코드 제한 사항이 있었습니다.  그러나 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서는 이러한 제한이 없어졌으므로 코드를 훨씬 자유롭게 쓰고 정렬할 수 있습니다.  
  
 물리적 한계는 컴파일 타임 고려 사항보다는 런타임 메모리에 따라 좌우됩니다.  잘 구성된 프로그램을 사용하고 크기가 큰 응용 프로그램을 여러 클래스 및 모듈로 나누는 경우에는 내부적 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 제한 사항이 발생할 확률이 거의 없습니다.  
  
 다음은 극단적인 경우에 발생할 수도 있는 몇 가지 제한 사항입니다.  
  
-   **이름 길이.** 선언된 모든 프로그래밍 요소 이름의 최대 문자 수입니다.  이 최대 문자 수는 요소 이름이 한정된 경우 전체 한정 문자열에 적용됩니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.  
  
-   **줄 길이.** 소스 코드의 물리적 줄에 입력 가능한 최대 문자 수\(65535\)입니다.  논리적 소스 코드 줄은 줄 연속 문자를 사용하는 경우 더 길어질 수 있습니다.  [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)를 참조하십시오.  
  
-   **배열 차원.** 배열에 선언할 수 있는 최대 차원 수입니다.  이는 배열 요소를 지정하는 데 사용할 수 있는 인덱스 수를 제한합니다.  [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)를 참조하십시오.  
  
-   **문자열 길이.** 단일 문자열에 저장할 수 있는 최대 유니코드 문자 수입니다.  [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)를 참조하십시오.  
  
-   **환경 문자열 길이.** 명령줄 인수로 사용되는 환경 문자열의 최대 문자 수\(32768\)입니다.  이는 모든 플랫폼에 적용되는 제한 사항입니다.  
  
## 참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)