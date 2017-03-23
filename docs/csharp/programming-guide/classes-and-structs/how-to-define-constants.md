---
title: "방법: C#에서 상수 정의 | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 상수"
  - "상수[C#]"
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# 방법: C#에서 상수 정의
상수는 컴파일 타임에 값이 설정되는 필드이므로 변경될 수 없습니다.  상수를 사용하여 특별한 값에 대해 숫자 리터럴\("마법수"\) 대신 의미 있는 이름을 지정합니다.  
  
> [!NOTE]
>  C\#에서 [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 전처리기 지시문은 C 및 C\+\+에서 일반적으로 사용되는 방식으로 상수를 정의할 수 없습니다.  
  
 `int`, `byte` 등과 같은 정수 계열 형식의 상수 값을 정의하려면 열거 형식을 사용하십시오.  자세한 내용은 [enum](../../../csharp/language-reference/keywords/enum.md)을 참조하십시오.  
  
 비정수 상수를 정의하는 방법 중 하나는 이름이 `Constants`인 단일 정적 클래스로 그룹화하는 것입니다.  다음 예제와 같이 상수에 대한 모든 참조는 클래스 이름으로 시작되어야 합니다.  
  
## 예제  
 [!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 클래스 이름 한정자를 사용하면 상수를 사용하는 사용자에게 그것이 상수 이고 상수를 수정할 수 없음을 이해하는데 도움이 됩니다.  
  
## 참고 항목  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)