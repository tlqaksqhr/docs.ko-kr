---
title: "방법: 여러 문자열 연결(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "문자열 연결[C#]"
  - "문자열 조인[C#]"
  - "문자열[C#], 연결"
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 방법: 여러 문자열 연결(C# 프로그래밍 가이드)
*연결*은 한 문자열을 다른 문자열의 끝에 추가하는 프로세스입니다.  `+` 연산자를 사용하여 문자열 리터럴이나 문자열 상수를 연결하면 컴파일러가 단일 문자열을 생성합니다.  런타임 연결은 발생하지 않습니다.  하지만 문자열 변수는 런타임에만 연결할 수 있습니다.  이 경우 다양한 접근 방식이 성능에 미치는 영향을 이해해야 합니다.  
  
## 예제  
 다음 예제에서는 긴 문자열 리터럴을 더 짧은 문자열로 분할하여 소스 코드의 가독성을 향상시키는 방법을 보여 줍니다.  분할된 문자열은 컴파일 타임에 단일 문자열로 연결됩니다.  이 경우 처리되는 문자열 수가 런타임 성능에 미치는 영향은 없습니다.  
  
 [!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## 예제  
 문자열 변수를 연결하려면 `+` 또는 `+=` 연산자를 사용하거나 <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> 또는 <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> 메서드를 사용할 수 있습니다.  `+` 연산자는 쉽게 사용할 수 있으며 코드 가독성을 높여 줍니다.  한 문장에서 \+ 연산자를 여러 개 사용해도 문자열 내용은 한 번만 복사됩니다.  그러나 반복문 등에서 이 연산을 여러 번 반복하면 효율성이 저하될 수도 있습니다.  예를 들어, 다음 코드를 참조하십시오.  
  
 [!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  문자열 연결 연산에서 C\# 컴파일러는 null 문자열을 빈 문자열과 같은 것으로 처리하지만 원래 null 문자열의 값을 변환하지는 않습니다.  
  
 루프에서와 같이 많은 수의 문자열을 연결하는 경우가 아니라면 이 코드의 성능 비용은 그리 크지 않을 것입니다.  같은 기준이 <xref:System.String.Concat%2A?displayProperty=fullName> 및 <xref:System.String.Format%2A?displayProperty=fullName> 메서드에도 적용됩니다.  
  
 하지만 성능이 중요한 경우에는 항상 <xref:System.Text.StringBuilder> 클래스를 사용하여 문자열을 연결해야 합니다.  다음 코드에서는 `+` 연산자와 같은 성능 영향이 없는 <xref:System.Text.StringBuilder> 클래스의 <xref:System.Text.StringBuilder.Append%2A> 메서드를 사용하여 문자열을 연결합니다.  
  
 [!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## 참고 항목  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)