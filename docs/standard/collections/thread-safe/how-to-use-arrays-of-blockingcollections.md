---
title: "방법: 파이프라인에서 차단 컬렉션 배열 사용"
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
helpviewer_keywords: thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab60561372f2c30055aed95ff60599ea80da1eb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>방법: 파이프라인에서 차단 수집 배열 사용
다음 예제에서는 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> 및 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>와 같은 정적 메서드와 함께 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> 개체의 배열을 사용하여 구성 요소 간에 빠르고 유연한 데이터 전송을 구현하는 방법을 보여줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 각 개체에서 동시에 입력 컬렉션으로부터 데이터를 가져와 변환하고 출력 컬렉션에 전달하는 기본 파이프라인 구현을 보여 줍니다.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [스레드로부터 안전한 컬렉션](../../../../docs/standard/collections/thread-safe/index.md)
