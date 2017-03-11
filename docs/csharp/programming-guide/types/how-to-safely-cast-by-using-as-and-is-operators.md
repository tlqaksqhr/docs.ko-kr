---
title: "방법: AS 및 IS 연산자를 사용한 안전한 캐스팅(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "as 연산자[C#]"
  - "캐스트 연산자[C#], as 및 is 연산자"
  - "Is 연산자[C#]"
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# 방법: AS 및 IS 연산자를 사용한 안전한 캐스팅(C# 프로그래밍 가이드)
개체는 다형성이므로 기본 클래스 형식의 변수는 파생 형식을 가질 수 있습니다.  파생 형식의 메서드에 액세스하려면 값을 파생 형식으로 다시 캐스팅해야 합니다.  그러나 이러한 경우 단순한 캐스팅을 시도하려면 <xref:System.InvalidCastException>이 throw될 수 있는 위험을 감수해야 합니다.  이 때문에 C\#은 [is](../../../csharp/language-reference/keywords/is.md) 및 [as](../../../csharp/language-reference/keywords/as.md) 연산자를 제공합니다.  이러한 연산자를 사용하면 예외를 throw시키지 않고 캐스트 성공 여부를 테스트할 수 있습니다.  일반적으로 캐스트가 성공하면 실제로 캐스트 값을 반환하는 `as` 연산자가 훨씬 효율적입니다.  `is` 연산자는 부울 값만 반환합니다.  따라서 이 연산자는 개체 형식을 결정하고 실제로 캐스트하지는 않는 경우에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 예외가 throw될 위험 없이 `is` 및 `as` 연산자를 사용하여 참조 형식에서 다른 형식으로 캐스트하는 방법을 보여 줍니다.  또한 이 예제에서는 null 허용 값 형식과 함께 `as` 연산자를 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-safely-cast-by-us_1.cs)]  
  
## 참고 항목  
 [형식](../../../csharp/programming-guide/types/index.md)   
 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)