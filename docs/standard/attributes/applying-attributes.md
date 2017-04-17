---
title: "특성 적용 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 특성"
  - "특성[.NET Framework], 적용"
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# 특성 적용
코드 요소에 특성을 적용하는 방법을 설명합니다.  
  
1.  새 특성을 정의하거나 .NET Framework에서 기존 특성의 네임스페이스를 가져옵니다.  
  
2.  코드 요소 바로 앞에 특성을 배치하는 방법으로 요소에 특성을 적용합니다.  
  
     특성 구문은 언어에 따라 다릅니다.  C\+\+ 및 C\#에서는 특성을 대괄호로 묶고 공백으로 요소와 구분하며 특성 안에서 줄 바꿈을 사용할 수 있습니다.  Visual Basic에서는 특성을 꺾쇠괄호로 묶으며 같은 논리 줄에 입력해야 합니다. 줄 바꿈이 필요할 경우에는 줄 연속 문자를 사용할 수 있습니다.  J\#에서는 특수 주석 구문을 사용하여 특성을 추가할 수 있습니다.  
  
3.  특성에는 위치 매개 변수와 명명된 매개 변수를 지정합니다.  
  
     위치 매개 변수는 필수 요소로, 명명된 매개 변수 앞에 와야 하며 특성 생성자 중 하나의 매개 변수에 해당합니다.  명명된 매개 변수는 선택적 요소로, 특성의 읽기\/쓰기 속성에 해당합니다.  C\+\+, C\# 및 J\#에서는 각 선택적 매개 변수에 `name`\=`value`를 지정합니다. 여기서 `name`은 속성의 이름입니다.  Visual Basic에서는 `name`:\=`value`를 지정합니다.  
  
 특성은 코드를 컴파일할 때 메타데이터로 내보내지며 공용 언어 런타임이나 기타 사용자 지정 도구 또는 응용 프로그램에서 런타임 리플렉션 서비스를 통해 사용할 수 있습니다.  
  
 모든 특성 이름은 규칙에 따라 Attribute로 끝납니다.  하지만 Visual Basic 및 C\# 같이 런타임을 목적으로 하는 일부 언어에서는 특성의 전체 이름을 지정할 필요가 없습니다.  예를 들어, <xref:System.ObsoleteAttribute?displayProperty=fullName>를 초기화하려면 해당 특성을 **Obsolete**로 참조하기만 하면 됩니다.  
  
## 메서드에 특성 적용  
 다음 코드 예제는 코드를 오래된 것으로 표시하는 **System.ObsoleteAttribute**의 선언 방법을 보여 줍니다.  `"Will be removed in next version"` 문자열이 특성에 전달됩니다.  이 특성이 설명하는 코드가 호출되면 전달된 문자열을 표시하는 컴파일러 경고가 발생합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## 어셈블리 수준에 특성 적용  
 어셈블리에 특성을 적용하려면 **Assembly** \(Visual Basic에선`Assembly` \) 키워드를 사용합니다.  다음 코드는 어셈블리에 적용된 **AssemblyNameAttribute** 에 대해 보여줍니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 이 특성이 적용되면 문자열 `"My Assembly"`가 해당 파일의 메타데이터 부분에 있는 어셈블리 매니페스트에 놓입니다.  [MSIL 디스어셈블러\(Ildasm.exe\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하거나 특성을 검색하는 사용자 지정 프로그램을 만들면 이 특성을 볼 수 있습니다.  
  
## 참고 항목  
 [특성](../../../docs/standard/attributes/index.md)   
 [특성에 저장된 정보 검색](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)   
 [Concepts](../Topic/Attributed%20Programming%20Concepts.md)   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)