---
title: "연속 키를 기준으로 결과 그룹화"
description: "연속 키를 기준으로 결과를 그룹화하는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: cdd06a6fad037291bbc5aa011b47bb668fa2f062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="group-results-by-contiguous-keys"></a>연속 키를 기준으로 결과 그룹화

다음 예제에서는 연속 키의 하위 시퀀스를 나타내는 청크로 요소를 그룹화하는 방법을 보여 줍니다. 예를 들어 키-값 쌍의 다음 시퀀스가 제공된다고 가정합니다.  
  
|Key|값|  
|---------|-----------|  
|A|수|  
|A|think|  
|A|that|  
|B|Linq|  
|C|is|  
|A|really|  
|B|cool|  
|B|!|  
  
 다음 그룹이 이 순서로 만들어집니다.  
  
1.  We, think, that  
  
2.  Linq  
  
3.  is  
  
4.  really  
  
5.  cool, !  
  
 솔루션은 스레드로부터 안전하고 결과를 스트리밍 방식으로 반환하는 확장 메서드로 구현됩니다. 즉, 솔루션은 소스 시퀀스를 거치면서 그룹을 생성합니다. `group` 또는 `orderby` 연산자와 달리 모든 시퀀스를 다 읽기 전에 그룹을 호출자에 반환하기 시작할 수 있습니다.  
  
 스레드로부터의 안전성을 달성하려면 소스 코드 요소에 설명된 대로 소스 시퀀스가 반복됨에 따라 각 그룹 또는 청크의 복사본을 만듭니다. 소스 시퀀스에 연속 항목의 큰 시퀀스가 포함된 경우 공용 언어 런타임이 <xref:System.OutOfMemoryException>을 throw할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 확장 메서드 및 이 메서드를 사용하는 클라이언트 코드를 보여 줍니다.  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 프로젝트에서 확장 메서드를 사용하려면 `MyExtensions` 정적 클래스를 신규 또는 기존 소스 코드 파일에 복사하고, 필요한 경우 해당 메서드가 있는 네임스페이스에 대한 `using` 지시문을 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)  
 
