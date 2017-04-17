---
title: "열거형 형식 문자열 | Microsoft Docs"
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
  - "열거형 형식 문자열"
  - "형식 지정자, 열거형 형식 문자열"
  - "서식 지정[.NET Framework], 열거형"
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 열거형 형식 문자열
<xref:System.Enum.ToString%2A?displayProperty=fullName> 메서드를 사용하여 숫자, 16진수 또는 열거형 멤버의 문자열 값을 나타내는 새 문자열 개체를 만들 수 있습니다.  이 메서드는 열거형 형식 문자열 중 하나를 사용하여 반환할 값을 지정합니다.  
  
 다음 표에서는 열거형 형식 문자열과 이들이 반환하는 값을 나열합니다.  이 서식 지정자는 대\/소문자를 구분하지 않습니다.  
  
|형식 문자열|결과|  
|------------|--------|  
|G 또는 g|가능하면 열거 엔트리를 문자열 값으로 표시하고, 그렇지 않으면 현재 인스턴스의 정수 값을 표시합니다.  열거에 **Flags** 특성이 설정되도록 정의하면, 유효한 각 엔트리의 문자열 값이 서로 연결되고 쉼표로 구분됩니다.  **Flags** 특성이 설정되지 않으면 잘못된 값이 숫자 엔트리로 표시됩니다.  다음 예제에서는 G 서식 지정자를 보여 줍니다.<br /><br /> [!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
 [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]|  
|F 또는 f|가능하면 열거 엔트리를 문자열 값으로 표시합니다.  **Flags** 특성이 제시되지 않더라도 값이 열거 엔트리의 합으로 완전히 표시될 수 있으면, 유효한 각 엔트리의 문자열 값은 서로 연결되며 쉼표로 구분됩니다.  열거 엔트리에서 이 값을 완전히 결정할 수 없으면 이 값의 형식은 정수 값으로 지정됩니다.  다음 예제에서는 F 서식 지정자를 보여 줍니다.<br /><br /> [!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
 [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]|  
|D 또는 d|열거 엔트리를 가능한 가장 짧은 정수 값으로 표현합니다.  다음 예제에서는 D 서식 지정자를 보여 줍니다.<br /><br /> [!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
 [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]|  
|X 또는 x|열거 엔트리를 16진수 값으로 표시합니다.  이 값은 최소 8자리로 만들기 위해 앞에 필요한 만큼 0을 붙여서 표시합니다.  다음 예제에서는 X 서식 지정자를 보여 줍니다.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
 [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]|  
  
## 예제  
 다음 예제에서는 `Red`, `Blue` 및 `Green`의 세 엔트리로 구성되는 `Colors`라는 열거형을 정의합니다.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 열거를 정의한 후에는 다음과 같은 방식으로 인스턴스를 선언할 수 있습니다.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 그런 다음 `Color.ToString(System.String)` 메서드를 사용하여 열거형 값에 전달되는 서식 지정자에 따라 서로 다른 방식으로 열거형 값을 표시할 수 있습니다.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## 참고 항목  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)