---
title: "방법: 숫자 앞에 0으로 채우기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서식 지정[.NET Framework], 숫자"
  - "숫자 형식 지정[.NET Framework]"
  - "숫자[.NET Framework], 형식 문자열"
  - "숫자 형식 문자열[.NET Framework]"
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 숫자 앞에 0으로 채우기
"D" [표준 숫자 서식 문자열](../../../docs/standard/base-types/standard-numeric-format-strings.md)과 함께 전체 자릿수 지정자를 사용하여 앞에 오는 0을 정수에 추가할 수 있습니다.  [사용자 지정 숫자 서식 문자열](../../../docs/standard/base-types/custom-numeric-format-strings.md)을 사용하여 정수와 부동 소수점 숫자 둘 다에 앞에 오는 0을 추가할 수 있습니다.  이 항목에서는 두 개의 메서드를 사용하여 앞에 오는 0으로 숫자를 채우는 방법을 보여 줍니다.  
  
### 앞에 오는 0으로 특정 길이까지 정수를 채우려면  
  
1.  표시할 정수 값의 최소 자릿수를 결정합니다.  이 숫자에 원하는 선행 자릿수를 포함합니다.  
  
2.  정수를 10진수 값으로 표시할지 아니면 16진수 값으로 표시할지를 결정합니다.  
  
    -   정수를 10진수 값으로 표시하려면 해당 `ToString(String)` 메서드를 호출하고 문자열 "D*n*"을 `format` 매개 변수의 값으로 전달합니다. 여기서 *n*은 문자열의 최소 길이를 나타냅니다.  
  
    -   정수를 16진수 값으로 표시하려면 해당 `ToString(String)` 메서드를 호출하고 문자열 "X*n*"을 `format` 매개 변수의 값으로 전달합니다. 여기서 *n*은 문자열의 최소 길이를 나타냅니다.  
  
     또한 [합성 서식 지정](../../../docs/standard/base-types/composite-formatting.md)을 사용하는 메서드에 <xref:System.String.Format%2A> 또는 <xref:System.Console.WriteLine%2A>과 같은 서식 문자열을 사용할 수 있습니다.  
  
 다음 예제에서는 서식이 지정된 숫자의 전체 길이가 8자 이상이 되도록 앞에 오는 0으로 여러 정수 값의 서식을 지정합니다.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### 특정 수의 앞에 오는 0으로 정수를 채우려면  
  
1.  정수 값을 표시하는 데 사용할 앞에 오는 0의 수를 결정합니다.  
  
2.  정수를 10진수 값으로 표시할지 아니면 16진수 값으로 표시할지를 결정합니다.  10진수 값으로 서식을 지정하려면 "D" 표준 서식 지정자를 사용해야 하고, 16진수 값으로 서식을 지정하려면 "X" 표준 서식 지정자를 사용해야 합니다.  
  
3.  정수 값의 `ToString("D").Length` 또는 `ToString("X").Length` 메서드를 호출하여 채워지지 않은 숫자 문자열의 길이를 확인합니다.  
  
4.  서식이 지정된 문자열에 포함할 앞에 오는 0의 수를 채워지지 않은 숫자 문자열의 길이에 추가합니다.  그러면 채워진 문자열의 전체 길이가 정의됩니다.  
  
5.  정수 값의 `ToString(String)` 메서드를 호출하고, 10진수 문자열의 경우 문자열 "D*n*"을 전달하고 16진수 문자열의 경우 "X*n*"을 전달합니다. 여기서 *n*은 채워진 문자열의 전체 길이를 나타냅니다.  또한 합성 서식 지정을 지원하는 메서드에 "D*n*" 또는 "X*n*" 서식 문자열을 사용할 수 있습니다.  
  
 다음 예제에서는 5개의 앞에 오는 0으로 정수 값을 채웁니다.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### 앞에 오는 0으로 특정 길이까지 숫자 값을 채우려면  
  
1.  숫자의 문자열 표현에서 정수 부분을 표시하는 데 사용할 자릿수를 결정합니다.  이 숫자의 전체 자릿수에 원하는 수의 앞에 오는 0을 포함합니다.  
  
2.  0 자리 표시자\("0"\)를 사용하여 0의 최소 수를 나타내는 사용자 지정 숫자 서식 문자열을 정의합니다.  
  
3.  숫자의 `ToString(String)` 메서드를 호출하여 사용자 지정 서식 문자열에 전달합니다.  또한 합성 서식 지정을 지원하는 메서드에 사용자 지정 서식 문자열을 사용할 수 있습니다.  
  
 다음 예제에서는 서식이 지정된 숫자에서 정수 부분의 전체 길이가 8자 이상이 되도록 앞에 오는 0으로 여러 숫자 값의 서식을 지정합니다.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### 특정 수의 앞에 오는 0으로 숫자 값을 채우려면  
  
1.  숫자 값을 표시하는 데 사용할 앞에 오는 0의 수를 결정합니다.  
  
2.  채워지지 않은 숫자 문자열에서 정수 부분의 자릿수를 확인합니다.  이렇게 하려면 다음을 수행합니다.  
  
    1.  숫자의 문자열 표현에 소수점 기호가 포함되어 있는지 확인합니다.  
  
    2.  소수점 기호가 포함되어 있으면 정수 부분에 있는 문자 수를 확인합니다.  
  
         또는  
  
         소수점 기호가 포함되어 있지 않으면 문자열의 길이를 확인합니다.  
  
3.  문자열에 표시할 각 앞에 오는 0에 대해 0 자리 표시자\("0"\)를 사용하고 0 자리 표시자 또는 10진수 자리 표시자\("\#"\)를 사용하여 기본 문자열에 있는 각 자릿수를 나타내는 사용자 지정 서식 문자열을 만듭니다.  
  
4.  사용자 지정 서식 문자열을 숫자의 `ToString(String)` 메서드에 대한 매개 변수 또는 합성 서식 지정을 지원하는 메서드에 대한 매개 변수로 제공합니다.  
  
 다음 예제에서는 5개의 앞에 오는 0으로 두 개의 <xref:System.Double> 값을 채웁니다.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## 참고 항목  
 [사용자 지정 숫자 형식 문자열](../../../docs/standard/base-types/custom-numeric-format-strings.md)   
 [표준 숫자 형식 문자열](../../../docs/standard/base-types/standard-numeric-format-strings.md)   
 [복합 형식 지정](../../../docs/standard/base-types/composite-formatting.md)