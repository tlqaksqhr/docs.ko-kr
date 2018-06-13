---
title: $ - 문자열 보간(C# 참조)
description: 문자열 보간을 이용한 구문으로 기존의 문자열 합성보다 읽기 쉽고 편리하게 문자열 출력의 서식을 지정할 수 있습니다.
ms.date: 03/26/2018
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 407ca9e4744ea9be45867a08e87c502821226472
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058838"
---
# <a name="---string-interpolation-c-reference"></a>$ - 문자열 보간(C# 참조)

`$`특수 문자는 문자열 리터럴을 *보간된 문자열*로 식별합니다. 보간된 문자열은 *보간된 식*이 포함될 수 있는 문자열 리터럴입니다. 보간된 문자열이 결과 문자열로 해석되면 보간된 식이 있는 항목이 식 결과의 문자열 표현으로 바뀝니다. 이 기능은 컴퓨터 언어 C# 6 이상 버전에서 사용할 수 있습니다.

문자열 보간은 [문자열 합성 서식 지정](../../../standard/base-types/composite-formatting.md) 기능보다 읽기 쉽고 편리하게 서식이 지정된 문자열을 만들 수 있는 구문을 제공합니다. 다음 예제에서는 두 기능을 사용하여 동일한 출력을 생성합니다.

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>보간된 문자열의 구조

문자열 리터럴을 보간된 문자열로 식별하려면 `$` 기호를 사용하여 추가합니다. 문자열 리터럴을 시작하는 `$` 및 `"` 사이에 공백이 없어야 합니다. 이렇게 하면 컴파일 시간 오류가 발생합니다.

보간된 식이 있는 항목의 구조는 다음과 같습니다.

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

대괄호 안의 요소는 선택 사항입니다. 다음 표에서는 각 요소에 대해 설명합니다.

|요소|설명|
|-------------|-----------------|
|`interpolatedExpression`|서식을 지정할 결과를 생성하는 식입니다. `null` 결과의 문자열 표현은 <xref:System.String.Empty?displayProperty=nameWithType>입니다.|
|`alignment`|보간된 식의 결과에 대한 문자열 표현의 최소 문자 수를 정의하는 값을 갖는 상수 식입니다. 양수이면 문자열 표현이 오른쪽에 맞춰지며, 음수이면 왼쪽에 맞춰집니다. 자세한 내용은 [맞춤 구성 요소](../../../standard/base-types/composite-formatting.md#alignment-component)를 참조하세요.|
|`formatString`|식 결과의 형식을 기준으로 지원되는 서식 문자열입니다. 자세한 내용은 [서식 문자열 구성 요소](../../../standard/base-types/composite-formatting.md#format-string-component)를 참조하세요.|

다음 예제에서는 위에 설명된 선택적 서식 지정 구성 요소를 사용합니다.

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>특수 문자

보간된 문자열로 생성된 문자에 중괄호("{" 또는 "}")를 포함하려면 두 개의 중괄호("{{" 또는 "}}")를 사용합니다. 자세한 내용은 [중괄호 이스케이프](../../../standard/base-types/composite-formatting.md#escaping-braces)를 참조하세요.

콜론(":")은 보간된 식 항목에서 특별한 의미가 있으므로, 보간된 식에서 [조건부 연산자](../operators/conditional-operator.md)를 사용하려면 해당 식을 괄호로 묶습니다.

다음 예제에서는 중괄호를 결과 문자열에 포함하는 방법과 보간된 식에서 조건부 연산자를 사용하는 방법을 보여줍니다.

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

약어 보간된 문자열은 `@` 문자가 뒤에 오는 `$` 문자로 시작합니다. 약어 문자열에 대한 자세한 내용은 [문자열](../keywords/string.md) 및 [약어 식별자](verbatim.md) 항목을 참조하세요.

> [!NOTE]
> `$` 토큰은 약어 보간된 문자열에서 `@` 토큰 앞에 나타나야 합니다.

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a>암시적 변환 및 `IFormatProvider` 구현 지정

보간된 문자열에서 다음과 같은 세 가지 암시적 변환을 수행할 수 있습니다.

1. 보간된 문자열을 <xref:System.String> 인스턴스로 변환. 보간된 식 항목을 사용하여 보간된 문자열을 확인한 결과를 올바르게 서식이 지정된 문자열 표현으로 바꾼 것입니다. 이 변환은 현재 문화권을 사용합니다.

1. 보간된 문자열을 서식을 지정할 식 결과와 함께 복합 서식 문자열을 나타내는 <xref:System.FormattableString> 인스턴스로 변환. 이 변수를 사용하면 단일 <xref:System.FormattableString> 인스턴스에서 문화권별 콘텐츠가 포함된 여러 결과 문자열을 만들 수 있습니다. 이렇게 하려면 다음 메서드 중 하나를 호출합니다.

      - <xref:System.Globalization.CultureInfo.CurrentCulture>에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.ToString> 오버로드.
      - <xref:System.Globalization.CultureInfo.InvariantCulture>에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.Invariant%2A> 메서드.
      - 지정된 문화에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.ToString(System.IFormatProvider)> 메서드.

    <xref:System.FormattableString.ToString(System.IFormatProvider)> 메서드를 사용하여 사용자 지정 형식을 지원하는 <xref:System.IFormatProvider> 인터페이스의 사용자 정의 구현을 제공할 수도 있습니다. 자세한 내용은 [ICustomFormatter를 사용한 사용자 지정 형식 지정](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)을 참조하세요.

1. 보간된 문자열을 <xref:System.IFormattable> 인스턴스로 변환. 또한 이 인스턴스를 사용하면 단일 <xref:System.IFormattable> 인스턴스의 문화권별 콘텐츠로 여러 결과 문자열을 만들 수 있습니다.

다음 예제에서는 <xref:System.FormattableString>에 대한 암시적 변환을 사용하여 문화권별 결과 문자열을 만듭니다.

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>추가 자료

문자열 보간을 처음 접하는 경우 [C#의 문자열 보간](../../quick-starts/interpolated-strings.yml)을 참조하세요. 자세한 내용은 [C#의 문자열 보간](../../tutorials/string-interpolation.md) 자습서를 참조하세요.

## <a name="see-also"></a>참고 항목  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [복합 형식 지정](../../../standard/base-types/composite-formatting.md)  
 [문자열](../../programming-guide/strings/index.md)  
 [C# 프로그래밍 가이드](../../programming-guide/index.md)  
 [C# 특수 문자](index.md)  
 [C# 참조](../index.md)  