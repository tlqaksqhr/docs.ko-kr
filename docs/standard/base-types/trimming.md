---
title: .NET에서 문자열의 문자 트리밍 및 제거
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02704ed5e396e973101bab4e5306d81f5a169d0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a>.NET에서 문자열의 문자 트리밍 및 제거
문장을 개별 단어로 구문 분석할 경우 단어의 끝에 빈 공간(공백이라고도 함)이 있는 단어가 생길 수 있습니다. 이 경우에 **System.String** 클래스에서 trim 메서드 중 하나를 사용하여 문자열에 지정된 위치에서 공백의 수나 다른 문자를 제거할 수 있습니다. 다음 테이블에서는 사용할 수 있는 trim 메서드에 대해 설명합니다.  
  
|메서드 이름|사용|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|문자열의 시작과 끝에서 문자 배열에 지정된 문자 또는 공백을 제거합니다.|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|문자열의 끝에서 문자 배열에 지정된 문자를 제거합니다.|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|문자열의 시작에서 문자 배열에 지정된 문자를 제거합니다.|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|문자열의 지정한 인덱스 위치에서 지정한 개수의 문자를 제거합니다.|  
  
## <a name="trim"></a>Trim  
 다음 예제와 같이 <xref:System.String.Trim%2A?displayProperty=nameWithType> 메서드를 사용하여 문자열의 양쪽 끝에서 공백을 쉽게 제거할 수 있습니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 문자열의 시작과 끝의 문자 배열에서 지정하는 문자를 제거할 수 있습니다. 다음 예제에서는 공백 문자, 마침표 또는 별표를 제거합니다.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a>TrimEnd  
 **String.TrimEnd** 메서드는 새 문자열 개체를 생성하여 문자열의 끝에서 문자를 제거합니다. 문자 배열을 이 메서드에 전달하여 제거할 문자를 지정합니다. 문자 배열에서 요소의 순서는 trim 작업에 영향을 주지 않습니다. 배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.  
  
 다음 예제에서는 **TrimEnd** 메서드를 사용하여 문자열의 마지막 문자를 제거합니다. 이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'r'` 문자 및 `'W'` 문자의 위치는 중요하지 않습니다. 이 코드는 `MyString`의 마지막 단어 및 첫 번째 단어의 일부를 제거합니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 이 코드는 콘솔에 `He`를 표시합니다.  
  
 다음 예제에서는 **TrimEnd** 메서드를 사용하여 문자열의 마지막 단어를 제거합니다. 이 코드에서 쉼표는 `Hello` 단어 뒤에 오면 쉼표가 trim에 대한 문자의 배열에 지정되지 않기 때문에 해당 trim은 쉼표에서 끝나게 됩니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 이 코드는 콘솔에 `Hello,`를 표시합니다.  
  
## <a name="trimstart"></a>TrimStart  
 **String.TrimStart** 메서드는 기존 문자열 개체의 시작 부분에서 문자를 제거하여 새 문자열을 만든다는 점을 제외하고 **String.TrimEnd** 메서드와 유사합니다. 문자 배열을 **TrimStart** 메서드에 전달하여 제거할 문자를 지정합니다. **TrimEnd** 메서드와 마찬가지로 문자 배열에서 요소의 순서는 트리밍 작업에 영향을 주지 않습니다. 배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.  
  
 다음 예제에서는 문자열의 첫 번째 단어를 제거합니다. 이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'l'` 문자 및 `'H'` 문자의 위치는 중요하지 않습니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 이 코드는 콘솔에 `World!`를 표시합니다.  
  
## <a name="remove"></a>제거  
 <xref:System.String.Remove%2A?displayProperty=nameWithType> 메서드는 기존 문자열의 지정된 위치에서 시작하는 지정된 수의 문자를 제거합니다. 이 메서드에서는 0 기반 인덱스를 가정합니다.  
  
 다음 예제에서는 문자열의 0 기반 인덱스 중 5번째 위치에서 시작하는 문자열에서 10개의 문자를 제거합니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
 <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> 메서드를 호출하고 빈 문자열(<xref:System.String.Empty?displayProperty=nameWithType>)을 대체로 지정하여 문자열에서 지정된 문자나 부분 문자열을 제거할 수도 있습니다. 다음 예제에서는 문자열에서 모든 쉼표를 제거합니다.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a>참고 항목  
 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)
