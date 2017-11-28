---
title: "방법: 정규식을 사용하여 문자열 검색(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>방법: 정규식을 사용하여 문자열 검색(C# 프로그래밍 가이드)
<xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 클래스를 사용하여 문자열을 검색할 수 있습니다. 이러한 검색의 복잡성은 매우 간단한 수준부터 정규식 전체 활용까지 다양할 수 있습니다. 다음은 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용한 문자열 검색의 두 가지 예입니다. 자세한 내용은 [.NET Framework 정규식](https://msdn.microsoft.com/library/hs600312)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드는 배열에서 대/소문자를 구분하지 않는 단순 문자열 검색을 수행하는 콘솔 응용 프로그램입니다. 정적 메서드 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>는 검색할 문자열과 검색 패턴을 포함하는 문자열이 제공될 경우 검색을 수행합니다. 이 경우 세 번째 인수는 대/소문자를 무시하도록 나타내는 데 사용됩니다. 자세한 내용은 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>을 참조하십시오.  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>예제  
 다음 코드는 정규식을 사용하여 배열에서 각 문자열 형식의 유효성을 검사하는 콘솔 응용 프로그램입니다. 유효성 검사에서는 각 문자열이 전화 번호의 형식을 사용하도록 요구합니다. 이 경우 3개의 숫자 그룹이 대시로 구분되고, 처음 두 그룹에는 세 자리 숫자가 포함되며, 세 번째 그룹에는 네 자리 숫자가 포함됩니다. 이 작업은 `^\\d{3}-\\d{3}-\\d{4}$` 정규식을 사용하여 수행됩니다. 자세한 내용은 [정규식 언어 - 빠른 참조](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)를 참조하세요.  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문자열](../../../csharp/programming-guide/strings/index.md)  
 [.NET Framework 정규식](https://msdn.microsoft.com/library/hs600312)  
 [정규식 언어 - 빠른 참조](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)
