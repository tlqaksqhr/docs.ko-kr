---
title: "방법: Finally 블록 사용"
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
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 325be4836d661369326fbe3ea1f8b252bf251f3c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-finally-blocks"></a>Finally 블록을 사용하는 방법

예외가 발생하면 실행이 중단되고 해당 예외 처리기에 제어가 제공됩니다. 이 경우 대체로 실행될 것으로 예상한 코드 줄을 건너뜁니다. 파일 닫기와 같은 일부 리소스 정리 작업은 예외가 throw된 경우에도 수행해야 합니다. 이 작업을 위해 `finally` 블록을 사용할 수 있습니다. `finally` 블록은 예외가 throw되었는지 여부에 관계없이 항상 실행됩니다.

다음 코드 예제에서는 `try`/`catch` 블록을 사용하여 <xref:System.ArgumentOutOfRangeException>을 catch합니다. `Main` 메서드는 두 개의 배열을 만들고 한 배열을 다른 배열에 복사하려고 합니다. 작업에서 <xref:System.ArgumentOutOfRangeException>이 발생하고 콘솔에 오류가 기록됩니다. `finally` 블록은 복사 작업의 결과에 관계없이 실행됩니다.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>참고 항목  
[예외](index.md)   
