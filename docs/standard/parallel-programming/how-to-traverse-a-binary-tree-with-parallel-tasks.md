---
title: "방법: 병렬 작업을 사용하여 이진 트리 트래버스"
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
helpviewer_keywords: tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c029a763faaa0b4d6ea5612efe079e47415b6fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>방법: 병렬 작업을 사용하여 이진 트리 트래버스
다음 예제에서는 트리 데이터 구조를 트래버스해야 하 병렬 작업 사용 될 수 있는 두 가지 방법으로 보여 줍니다. 트리 자체 생성 연습으로 그대로 유지 됩니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 두 방법 기능적으로 동일 합니다. 사용 하 여는 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> 만들어 작업을 실행 하는 메서드는 해당 작업에서 대기 하 고 예외를 처리 하는 데 사용할 수 있는 작업에서 핸들을 다시 가져온 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
