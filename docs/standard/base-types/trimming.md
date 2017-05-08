---
title: ".NET Framework에서 문자열의 문자 트리밍 및 제거 | Microsoft Docs"
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
  - "Remove 메서드"
  - "문자 제거"
  - "문자열[.NET Framework], 문자 제거"
  - "Trim 메서드"
  - "TrimEnd 메서드"
  - "문자 트리밍"
  - "TrimStart 메서드"
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# .NET Framework에서 문자열의 문자 트리밍 및 제거
문장을 개별 단어로 구문 분석할 때 앞쪽이나 뒤쪽에 공백이 있는 단어가 생길 수 있습니다.  **System.String** 클래스의 트리밍 메서드를 사용하여 문자열의 지정된 위치에서 모든 공백이나 다른 문자를 제거하면 이러한 문제를 해결할 수 있습니다.  다음 표에는 트리밍에 사용할 수 있는 메서드 및 설명이 나와 있습니다.  
  
|메서드 이름|기능|  
|------------|--------|  
|<xref:System.String.Trim%2A?displayProperty=fullName>|문자열의 시작과 끝 부분에서 문자나 공백을 제거합니다.|  
|<xref:System.String.TrimEnd%2A?displayProperty=fullName>|문자열 끝 부분에서 문자를 제거하며, 제거할 문자는 문자 배열에 넣어 전달됩니다.|  
|<xref:System.String.TrimStart%2A?displayProperty=fullName>|문자열의 시작 부분에서 문자를 제거하며, 제거할 문자는 문자 배열에 넣어 전달됩니다.|  
|<xref:System.String.Remove%2A?displayProperty=fullName>|문자열의 지정된 인덱스 위치에서 지정된 수만큼의 문자를 제거합니다.|  
  
## Trim  
 다음 예제와 같이 <xref:System.String.Trim%2A?displayProperty=fullName> 메서드를 사용하여 문자열 양쪽의 공백을 간편하게 제거할 수 있습니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 또한 지정한 문자 배열에서 문자열의 시작과 끝에 있는 문자를 제거할 수 있습니다.  다음 예제에서는 공백 문자, 마침표 또는 별표를 제거합니다.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## TrimEnd  
 **String.TrimEnd** 메서드에서는 문자열 끝 부분에서 문자를 제거하여 새로운 문자열 개체를 만듭니다.  제거할 문자를 지정하는 문자 배열을 이 메서드에 전달합니다.  문자 배열에 있는 요소의 순서는 트리밍 작업에 영향을 미치지 않습니다.  배열에 지정하지 않은 문자가 발견되면 트리밍이 중단됩니다.  
  
 다음 예제에서는 **TrimEnd** 메서드를 사용하여 문자열의 마지막 문자를 제거합니다.  이 예제에서는 배열에 있는 문자의 순서가 중요하지 않다는 것을 보여 주기 위해 `'r'`와 `'W'`의 위치를 서로 바꿨습니다.  이 코드에서는 `MyString`에 있는 두 번째 단어 및 첫 번째 단어의 일부를 제거합니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 이 코드를 실행하면 `He`가 콘솔에 출력됩니다.  
  
 다음 코드 예제에서는 **TrimEnd** 메서드를 사용하여 문자열에서 마지막 단어를 제거합니다.  이 코드에서 `Hello` 다음에는 쉼표가 있지만 트리밍할 문자 배열에 쉼표를 지정하지 않았기 때문에 쉼표는 제거되지 않습니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 이 코드를 실행하면 `Hello,`가 콘솔에 출력됩니다.  
  
## TrimStart  
 **String.TrimStart** 메서드는 기존 문자열 개체의 시작 부분에서 문자를 제거하여 새로운 문자열을 만든다는 점만 제외하면 **String.TrimEnd** 메서드와 비슷합니다.  제거할 문자를 지정하는 문자 배열을 **TrimStart** 메서드에 전달합니다.  **TrimEnd** 메서드와 마찬가지로 문자 배열에 있는 요소의 순서는 트리밍 작업에 영향을 주지 않습니다.  배열에 지정하지 않은 문자가 발견되면 트리밍이 중단됩니다.  
  
 다음 예제에서는 문자열의 첫 번째 단어를 제거합니다.  이 예제에서는 배열에 있는 문자의 순서가 중요하지 않다는 것을 보여 주기 위해 `'l'`와 `'H'`의 위치를 서로 바꿨습니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 이 코드를 실행하면 `World!`가 콘솔에 출력됩니다.  
  
## 제거  
 <xref:System.String.Remove%2A?displayProperty=fullName> 메서드는 기존 문자열의 지정된 위치에서 시작하여 지정된 수만큼의 문자를 제거합니다.  이 메서드에서는 0에서 시작하는 인덱스를 사용합니다.  
  
 다음 예제에서는 0에서 시작하는 인덱스를 사용하며, 문자열의 5번 인덱스 위치에서 시작하여 열 개의 문자를 제거합니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
 또한 문자열에서 지정한 문자 또는 부분 문자열을 <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=fullName> 메서드를 호출하여 제거할 수 있고 빈 문자열을 \(<xref:System.String.Empty?displayProperty=fullName>\)로 교체할 수도 있습니다.  다음 예제에서는 문자열에서 모든 쉼표를 제거합니다.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## 참고 항목  
 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)