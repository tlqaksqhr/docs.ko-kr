---
title: "방법: Catch 블록에 특정 예외 사용"
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
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 94e5840ca4bb5f871a0ae91f53404de6a60d749d
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>특정 예외는 catch 블록에서 사용 하는 방법

일반적으로 것이 바람직한 프로그래밍 습관 기본을 사용 하지 않고 특정 형식의 예외를 catch 하려면 `catch` 문.

예외가 발생하면 스택 위로 전달되며 각 catch 블록에 예외를 처리할 수 있는 기회가 제공됩니다. catch 문의 순서가 중요합니다. 특정 예외를 대상으로 하는 catch 블록은 일반 예외 catch 블록 앞에 배치합니다. 그러지 않으면 컴파일러에서 오류가 발생할 수 있습니다. 예외 형식을 catch 블록에 지정된 예외 이름과 비교하여 적절한 catch 블록을 확인합니다. 특정 catch 블록이 없는 경우 일반 catch 블록(있는 경우)에서 예외를 catch합니다.

다음 코드 예제에서는 `try`/`catch` 블록을 사용하여 <xref:System.InvalidCastException>을 catch합니다. 샘플에서는 직원 수준이라는 하나의 속성(`Emlevel`)이 있는 `Employee` 클래스를 만듭니다. `PromoteEmployee` 메서드는 개체를 사용하고 직원 수준을 증가시킵니다. <xref:System.DateTime> 인스턴스가 `PromoteEmployee` 메서드로 전달될 때 <xref:System.InvalidCastException>이 발생합니다.

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a>참고 항목  
[예외](index.md)
