---
title: ".NET에서 StringBuilder 클래스 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a>.NET에서 StringBuilder 클래스 사용
<xref:System.String> 개체는 변경할 수 없습니다. 메서드 중 하나를 사용할 때마다는 <xref:System.String?displayProperty=nameWithType> 해당 새 개체에 대 한 공간이 새로 할당 해야 하는 메모리에를 새 string 개체를 만드는 클래스입니다. 문자열에 반복적 수정 해야 하는 경우에는 오버 헤드를 새로 만들 연관 <xref:System.String> 개체 비용이 증가할 수 있습니다. <xref:System.Text.StringBuilder?displayProperty=nameWithType> 새 개체를 만들지 않고 문자열을 수정 하려는 경우에 클래스를 사용할 수 있습니다. 예를 들어,를 사용 하는 <xref:System.Text.StringBuilder> 클래스는 루프에서 많은 문자열을 연결할 때 성능을 높일 수 있습니다.  
  
## <a name="importing-the-systemtext-namespace"></a>System.Text 네임스페이스 가져오기  
 <xref:System.Text.StringBuilder> 클래스에서 발견 되는 <xref:System.Text> 네임 스페이스입니다.  코드에서 정규화 된 형식 이름을 제공할 필요가 없도록를 가져올 수 있습니다는 <xref:System.Text> 네임 스페이스:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>StringBuilder 개체 인스턴스화  
 새 인스턴스를 만들 수 있습니다는 <xref:System.Text.StringBuilder> 클래스에서는 다음 예제와 같이 변수 오버 로드 된 생성자 메서드 중 하나를 초기화 합니다.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>용량 및 길이 설정  
 하지만 <xref:System.Text.StringBuilder> 를 캡슐화 하는 문자열의 문자 수를 확장할 수 있는 동적 개체는 저장할 수 있는 문자의 최대 수에 대 한 값을 지정할 수 있습니다. 이 값은 프로젝트의 용량 이라고 하며 문자열의 길이와 혼동 해서는 안 하는 현재 <xref:System.Text.StringBuilder> 보유 합니다. 예를 들어,의 새 인스턴스를 만들 수는 <xref:System.Text.StringBuilder> 5의 길이 "Hello" 문자열을 사용 하 여 클래스 개체의 25 최대 용량을 지정할 수 있습니다. 수정 하는 경우는 <xref:System.Text.StringBuilder>, 할당 되지 않습니다 크기 자체에 대 한 용량에 도달할 때까지 합니다. 이 경우 새 공간이 자동으로 할당되고 용량이 두 배로 증가합니다. 용량을 지정할 수는 <xref:System.Text.StringBuilder> 클래스 오버 로드 된 생성자 중 하나를 사용 합니다. 다음 예에서는 `MyStringBuilder` 개체를 최대 25개 공간으로 확장할 수 있도록 지정합니다.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 또한 읽기/쓰기를 사용할 수 있습니다 <xref:System.Text.StringBuilder.Capacity%2A> 속성을 개체의 최대 길이 설정 합니다. 다음 예에서는 **Capacity** 속성을 사용하여 최대 개체 길이를 정의합니다.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 <xref:System.Text.StringBuilder.EnsureCapacity%2A> 메서드를 사용 하 여 현재 용량을 확인할 수 **StringBuilder**합니다. 용량이 전달된 값보다 크면 변경되지 않고, 용량이 전달된 값보다 작으면 현재 용량이 전달된 값과 일치하도록 변경됩니다.  
  
 <xref:System.Text.StringBuilder.Length%2A> 속성을 표시 하거나 설정도 있습니다. **Length** 속성을 **Capacity** 속성보다 큰 값으로 설정하면 **Capacity** 속성이 **Length** 속성과 동일한 값으로 자동으로 변경됩니다. **Length** 속성을 현재 **StringBuilder** 내의 문자열 길이보다 작은 값으로 설정하면 문자열이 단축됩니다.  
  
## <a name="modifying-the-stringbuilder-string"></a>StringBuilder 문자열 수정  
 다음 표에서는 **StringBuilder**의 내용을 수정하는 데 사용할 수 있는 메서드를 보여 줍니다.  
  
|메서드 이름|기능|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|현재 **StringBuilder**의 끝에 정보를 추가합니다.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|문자열에 전달된 서식 지정자를 서식 있는 텍스트로 바꿉니다.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|현재 **StringBuilder**의 지정된 인덱스에 문자열 또는 개체를 삽입합니다.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|현재 **StringBuilder**에서 지정된 수의 문자를 제거합니다.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|지정된 인덱스에서 지정된 문자를 바꿉니다.|  
  
### <a name="append"></a>추가  
 **Append** 메서드를 사용 하 여 텍스트 또는 개체의 문자열 표현이 현재 문자열의 끝에 추가할 수 **StringBuilder**합니다. 다음 예에서는 **StringBuilder**를 "Hello World"로 초기화한 다음 개체의 끝에 일부 텍스트를 추가합니다. 필요한 경우 공간이 자동으로 할당됩니다.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> 의 끝에 텍스트를 추가 하는 메서드는 <xref:System.Text.StringBuilder> 개체입니다. 복합 서식 지정 기능을 지원 (자세한 내용은 참조 [합성 서식 지정](../../../docs/standard/base-types/composite-formatting.md))를 호출 하 여는 <xref:System.IFormattable> 의 서식을 지정 하는 개체를 구현 합니다. 따라서 숫자, 날짜 및 시간, 열거형 값에 대한 표준 서식 문자열, 숫자, 날짜 및 시간 값에 대한 사용자 지정 서식 문자열, 사용자 지정 형식에 대해 정의된 서식 문자열을 허용합니다. 서식 지정에 대한 자세한 내용은 [서식 지정 형식](../../../docs/standard/base-types/formatting-types.md)을 참조하세요. 이 메서드를 사용 하 여 변수의 서식을 사용자 지정 하 고 해당 값을 추가 하는 <xref:System.Text.StringBuilder>합니다. 다음 예제에서는 <xref:System.Text.StringBuilder.AppendFormat%2A> 의 끝에 통화 값으로 서식이 지정 된 정수 값을 배치 하는 메서드는 <xref:System.Text.StringBuilder> 개체입니다.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 <xref:System.Text.StringBuilder.Insert%2A> 현재에서 지정 된 위치에 문자열 또는 개체를 추가 하는 메서드 <xref:System.Text.StringBuilder> 개체입니다. 다음 예제에서는이 메서드를 사용 하 여 단어의 6 번째 위치에 삽입 하는 <xref:System.Text.StringBuilder> 개체입니다.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>제거  
 사용할 수는 **제거** 현재에서 지정한 개수의 문자를 제거 하는 메서드 <xref:System.Text.StringBuilder> 개체, 지정 된 인덱스에서 시작 합니다. 다음 예제에서는 **제거** 길이를 단축할 메서드는 <xref:System.Text.StringBuilder> 개체입니다.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>바꾸기  
 **대체** 메서드 내에서 문자를 바꾸는 데 사용할 수는 <xref:System.Text.StringBuilder> 개체를 다른 문자를 지정 합니다. 다음 예제에서는 **대체** 검색 하는 메서드는 <xref:System.Text.StringBuilder> 개체에서 느낌표 함수의 모든 인스턴스의 문자 (!) 및 물음표 문자 (?)으로 바꾸세요.  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>StringBuilder 개체를 문자열로 변환  
 변환 해야 합니다는 <xref:System.Text.StringBuilder> 개체를 <xref:System.String> 이 나타내는 문자열을 전달할 수 전에 개체는 <xref:System.Text.StringBuilder> 개체 변수가 있는 메서드를 한 <xref:System.String> 매개 변수 또는 사용자 인터페이스에 표시 합니다. 이 변환을 호출 하 여 수행 된 <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> 메서드. 다음 예제에서는 다양 한 <xref:System.Text.StringBuilder> 메서드 및 호출은 <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> 메서드 문자열 표시를 합니다.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)
