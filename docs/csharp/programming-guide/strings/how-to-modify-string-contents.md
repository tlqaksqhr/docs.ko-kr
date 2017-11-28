---
title: "방법: 문자열 내용 수정(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a>방법: 문자열 내용 수정(C# 프로그래밍 가이드)
문자열은 *변경할 수 없으므로*, 안전하지 않은 코드를 사용하지 않으면 문자열 개체가 생성된 후 개체 값을 수정할 수 없습니다. 그러나 문자열 값을 수정하고 그 결과를 새 문자열 개체에 저장하는 여러 가지 방법이 있습니다. <xref:System.String?displayProperty=nameWithType> 클래스는 입력 문자열에서 작동하고 새 문자열 개체를 반환하는 메서드를 제공합니다. 대부분의 경우 원래 문자열이 포함된 변수에 새 개체를 할당할 수 있습니다. <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 클래스는 비슷한 방식으로 작동하는 추가 메서드를 제공합니다. <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스는 “현재 위치”에서 수정할 수 있는 문자 버퍼를 제공합니다. <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> 메서드를 호출하여 버퍼의 현재 내용을 포함하는 새 문자열 개체를 만듭니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 지정된 문자열의 부분 문자열을 바꾸거나 제거하는 다양한 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a>예제  
 배열 표기법을 사용하여 문자열의 개별 문자에 액세스하려면 <xref:System.Text.StringBuilder> 개체를 사용할 수 있습니다. 이 개체는 `[]` 연산자를 오버로드하여 내부 문자 버퍼에 대한 액세스를 제공합니다. <xref:System.String.ToCharArray%2A> 메서드를 사용하여 문자열을 문자 배열로 변환할 수도 있습니다. 다음 예제에서는 `ToCharArray`를 사용하여 배열을 만듭니다. 이 배열의 일부 요소를 수정합니다. 그런 다음 문자 배열을 입력 매개 변수로 사용하는 문자열 생성자를 호출하여 새 문자열을 만듭니다.  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a>예제  
 다음 예제는 C 스타일 문자 배열과 비슷한 방식으로 안전하지 않은 코드를 사용하여 현재 위치에서 문자열을 수정하려는 매우 드문 경우를 위해 제공되었습니다. 이 예제에서는 fixed 키워드를 사용하여 “현재 위치”에서 개별 문자에 액세스하는 방법을 보여 줍니다. 또한 문자열에 대한 안전하지 않은 작업의 가능한 부작용 중 하나를 보여 줍니다. 이 부작용은 C# 컴파일러가 문자열을 내부적으로 저장(intern)하는 방식에서 발생합니다. 일반적으로 이 방식은 반드시 필요한 경우에만 사용해야 합니다.  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문자열](../../../csharp/programming-guide/strings/index.md)
