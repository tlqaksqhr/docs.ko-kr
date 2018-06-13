---
title: typeof(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 4203b597d7045a13ffed9e61ddbbde57e2113c23
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171943"
---
# <a name="typeof-c-reference"></a>typeof(C# 참조)
형식의 `System.Type` 개체를 가져오는 데 사용됩니다. `typeof` 식의 형식은 다음과 같습니다.  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>설명  
 식의 런타임 형식을 가져오려면 다음 예제와 같이 .NET Framework 메서드 <xref:System.Object.GetType%2A>을 사용할 수 있습니다.  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 `typeof` 연산자를 오버로드할 수 없습니다.  
  
 열린 제네릭 형식에서 `typeof` 연산자를 사용할 수도 있습니다. 둘 이상의 형식 매개 변수가 있는 형식의 사양에 적절한 개수의 쉼표가 있어야 합니다. 다음 예제에서는 메서드의 반환 형식이 제네릭 <xref:System.Collections.Generic.IEnumerable%601>인지 여부를 확인하는 방법을 보여 줍니다. 메서드는 MethodInfo 형식의 인스턴스라고 가정합니다.  
  
```csharp  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a>예  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>예  
 이 샘플에서는 <xref:System.Object.GetType%2A> 메서드를 사용하여 숫자 계산의 결과를 포함하는 데 사용되는 형식을 결정합니다. 이 형식은 결과 숫자의 저장소 요구 사항에 따라 달라집니다.  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Type?displayProperty=nameWithType>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)
