---
title: "방법: 제네릭 클래스 사용(Visual Basic) | Microsoft Docs"
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
  - "형식 매개 변수, 정의"
  - "데이터 형식 인수, 정의"
  - "변수 [Visual Basic], 데이터 형식"
  - "Of 키워드, 사용"
  - "제네릭 매개 변수"
  - "데이터 형식 매개 변수"
  - "제네릭 [Visual Basic], 제네릭 정보"
  - "데이터 형식 [Visual Basic], 매개 변수로"
  - "데이터 형식 [Visual Basic], 인수로"
  - "매개 변수, 형식"
  - "형식 [Visual Basic], 제네릭"
  - "매개 변수, 제네릭"
  - "제네릭 [Visual Basic], 제네릭 형식 만들기"
  - "데이터 형식 인수"
  - "매개 변수, 데이터 형식"
  - "데이터 형식 매개 변수, 정의"
  - "형식 인수, 정의"
  - "인수 [Visual Basic], 형식"
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 제네릭 클래스 사용(Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*형식 매개 변수* 를 사용하는 클래스를 *제네릭 클래스*라고 합니다. 제네릭 클래스를 사용 중인 경우 이러한 각 매개 변수에 대해 *형식 인수* 를 제공하여, 여기에서 *생성된 클래스* 를 만들 수 있습니다. 그런 다음 생성된 클래스 형식의 변수를 선언하고, 생성된 클래스의 인스턴스를 만들어 해당 변수에 할당할 수 있습니다.  
  
 클래스 이외에도 제네릭 구조체, 인터페이스, 프로시저 및 대리자도 정의할 수 있습니다.  
  
 다음 절차에서는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 에서 정의한 제네릭 클래스를 가져오고 여기에서 인스턴스를 만듭니다.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>형식 매개 변수를 가져오는 클래스를 사용하려면  
  
1.  소스 파일의 시작 부분에 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 포함하여 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스를 가져옵니다. 이렇게 하면 <xref:System.Collections.Queue?displayProperty=fullName>와 같은 다른 큐 클래스와 차별화하기 위해 정규화하지 않고도 <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> 클래스를 참조할 수 있습니다.  
  
2.  일반적인 방법으로 개체를 만들지만 클래스 이름 바로 뒤에 `(Of` `type``)` 을 추가합니다.  
  
     다음 예에서는 동일한 클래스(<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>)를 사용하여 서로 다른 데이터 형식의 항목을 포함하는 두 개의 큐 개체를 만듭니다. 각 큐의 끝에 항목을 추가한 다음 각 큐의 앞부분부터 항목을 제거하고 표시합니다.  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의](../Topic/How%20to:%20Define%20a%20Class%20That%20Can%20Provide%20Identical%20Functionality%20on%20Different%20Data%20Types%20\(Visual%20Basic\).md)   
 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)