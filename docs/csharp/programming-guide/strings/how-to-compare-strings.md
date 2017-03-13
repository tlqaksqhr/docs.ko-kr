---
title: "방법: 문자열 비교(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "문자열 비교[C#]"
  - "문자열[C#], 비교"
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# 방법: 문자열 비교(C# 프로그래밍 가이드)
문자열을 비교할 경우 한 문자열이 다른 문자열보다 크거나 작거나 같다는 결과를 얻게 됩니다.  결과를 결정하는 규칙은 *서수 비교*를 수행하는지 *문화권 구분 비교*를 수행하는지에 따라 달라집니다.  따라서 특정 작업에 올바른 비교를 사용하는 것이 중요합니다.  
  
 언어 규칙을 고려하지 않고 두 문자열 값을 비교하거나 정렬해야 하는 경우 기본 서수 비교를 사용합니다.  기본 서수 비교\(`System.StringComparison.Ordinal`\)는 대\/소문자를 구분합니다. 즉, 두 문자열의 각 문자가 서로 일치해야 합니다. 예를 들어 "and"는 "And"나 "AND"와 같지 않습니다.  자주 사용하는 변형으로 `System.StringComparison.OrdinalIgnoreCase`가 있습니다. 이 경우에는 "and", "And" 및 "AND"가 일치합니다.  `StringComparison.OrdinalIgnoreCase`는 파일 이름, 경로 이름, 네트워크 경로 및 사용자 컴퓨터의 로캘에 따라 값이 변경되지 않는 기타 문자열을 비교할 때 자주 사용됩니다.  자세한 내용은 <xref:System.StringComparison?displayProperty=fullName>을 참조하십시오.  
  
 일반적으로 문화권 구분 비교는 최종 사용자가 입력한 문자열을 비교하고 정렬할 때 사용됩니다. 이것은 이러한 문자열의 문자 및 정렬 규칙이 사용자 컴퓨터의 로캘에 따라 달라질 수 있기 때문입니다.  현재 스레드의 문화권에 따라 동일한 문자를 포함하는 문자열도 다르게 정렬될 수 있습니다.  
  
> [!NOTE]
>  문자열을 비교할 경우 수행하려는 비교 종류를 명시적으로 지정하는 메서드를 사용해야 합니다.  이렇게 하면 코드를 보다 쉽게 읽고 유지 관리할 수 있습니다.  가능한 경우 수행할 비교의 종류를 지정할 수 있도록 <xref:System.StringComparison> 열거형 매개 변수를 사용하는 <xref:System.String?displayProperty=fullName> 및 <xref:System.Array?displayProperty=fullName> 클래스의 메서드 오버로드를 사용해야 합니다.  문자열을 비교할 때는 `==` 및 `!=` 연산자를 사용하지 않는 것이 좋습니다.  또한 <xref:System.String.CompareTo%2A?displayProperty=fullName> 인스턴스 메서드는 오버로드가 <xref:System.StringComparison>을 사용하지 않으므로 사용하지 않는 것이 좋습니다.  
  
## 예제  
 다음 예제에서는 사용자 컴퓨터의 로캘에 따라 값이 변경되지 않는 문자열을 올바르게 비교하는 방법을 보여 줍니다.  또한 이 예제에서는 C\#의 *문자열 인터닝* 기능을 보여 줍니다.  프로그램이 둘 이상의 동일한 문자열 변수를 선언한 경우 컴파일러는 해당 변수를 모두 동일한 위치에 저장합니다.  <xref:System.Object.ReferenceEquals%2A> 메서드를 호출하면 두 문자열이 실제로 메모리의 동일한 개체를 참조한다는 것을 확인할 수 있습니다.  인터닝을 방지하려면 다음 예제와 같이 <xref:System.String.Copy%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
 [!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]  
  
## 예제  
 다음 코드 예제에서는 <xref:System.StringComparison> 열거형을 사용하는 <xref:System.String?displayProperty=fullName> 메서드를 통해 원하는 방식으로 문자열을 비교하는 방법을 보여 줍니다.  <xref:System.String.CompareTo%2A?displayProperty=fullName> 인스턴스 메서드는 해당 오버로드가 <xref:System.StringComparison>을 사용하지 않으므로 이 예제에 사용되지 않습니다.  
  
 [!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.StringComparer?displayProperty=fullName> 매개 변수를 사용하는 정적 <xref:System.Array> 메서드를 통해 문화권 구분 방식으로 배열에서 문자열을 정렬하고 검색하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]  
  
 <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 및 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 등의 컬렉션 클래스에는 요소나 키의 형식이 `string`일 경우 <xref:System.StringComparer?displayProperty=fullName> 매개 변수를 사용하는 생성자가 있습니다.  일반적으로 가능한 경우에는 항상 이러한 생성자를 사용하여 `Ordinal` 또는 `OrdinalIgnoreCase`를 지정해야 합니다.  
  
## 참고 항목  
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [문자열](../../../csharp/programming-guide/strings/index.md)   
 [문자열 비교](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)   
 [응용 프로그램 전역화 및 지역화](/visual-studio/ide/globalizing-and-localizing-applications)