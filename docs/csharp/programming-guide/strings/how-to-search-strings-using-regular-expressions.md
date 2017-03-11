---
title: "방법: 정규식을 사용하여 문자열 검색(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "문자열 검색[C#]"
  - "문자열[C#], RegEx로 검색"
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# 방법: 정규식을 사용하여 문자열 검색(C# 프로그래밍 가이드)
<xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> 클래스를 사용하여 문자열을 검색할 수 있습니다.  매우 단순한 검색에서 정규식을 최대한 활용하는 매우 복잡한 검색까지 다양한 검색을 수행할 수 있습니다.  다음 두 예제에서는 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용하여 문자열을 검색하는 방법을 보여 줍니다.  자세한 내용은 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)을 참조하십시오.  
  
## 예제  
 다음 코드는 배열에서 대\/소문자를 구분하지 않는 단순 문자열 검색을 수행하는 콘솔 응용 프로그램입니다.  정적 메서드인 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName>에서는 검색할 문자열 및 검색 패턴을 포함하는 문자열을 사용하여 검색을 수행합니다.  이 경우에는 세 번째 인수를 사용하여 대\/소문자를 무시하도록 지정합니다.  자세한 내용은 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>을 참조하십시오.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#17)]  
  
## 예제  
 다음 코드는 정규식을 사용하여 배열에서 각 문자열 형식의 유효성을 검사하는 콘솔 응용 프로그램입니다.  유효성 검사를 통과하려면 각 문자열의 형식이 전화 번호와 같아야 합니다. 즉 세 그룹의 숫자가 대시\(\-\)로 구분되어야 하고 처음 두 그룹에는 세 개, 세 번째 그룹에는 네 개의 숫자가 있어야 합니다.  이는 정규식 `^\\d{3}-\\d{3}-\\d{4}$`를 사용하여 수행할 수 있습니다.  자세한 내용은 [정규식 언어 \- 빠른 참조](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md)을 참조하십시오.  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#18)]  
  
## 참고 항목  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)   
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [정규식 언어 \- 빠른 참조](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md)