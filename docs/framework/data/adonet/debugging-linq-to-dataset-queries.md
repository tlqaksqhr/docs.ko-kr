---
title: "LINQ to DataSet 쿼리 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 964a4d051600621d581e05dcf6b518b2766e2750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="debugging-linq-to-dataset-queries"></a>LINQ to DataSet 쿼리 디버깅
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]은 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드 디버깅을 지원합니다. 그러나 몇 가지 디버깅 차이점 있습니다 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드 및 비-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 관리 코드입니다. 대부분의 디버깅 기능을 사용할 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문, 단계별 실행, 중단점 설정 및 디버거 창에 표시 된 결과 보기를 포함 합니다. 지연된 쿼리 실행에는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드를 디버깅할 때 고려해야 하는 몇 가지 의도하지 않은 결과가 발생할 수 있으며 편집하며 계속하기 사용과 관련된 몇 가지 제한이 있습니다. 이 항목에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]이 아닌 관리 코드와 비교하여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에 고유한 디버깅 특성에 대해 설명합니다.  
  
## <a name="viewing-results"></a>결과 보기  
 DataTips, 조사식 창 및 간략한 조사식 대화 상자를 사용하여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문의 결과를 볼 수 있습니다. 소스 창을 사용할 때 소스 창의 쿼리 위에 포인터를 올려 놓으면 DataTips가 나타납니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 변수를 복사하여 조사식 창이나 간략한 조사식 대화 상자에 붙여 넣을 수 있습니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서 쿼리는 작성되거나 선언될 때 계산되는 것이 아니라 쿼리가 실행될 때에만 계산됩니다. 이 라고 *지연 된 실행*합니다. 따라서 쿼리가 계산되기 전까지는 쿼리 변수에 값이 없습니다. 자세한 내용은 참조 [LINQ to DataSet에서에서 쿼리](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)합니다.  
  
 쿼리 결과를 표시하려면 디버거에서 쿼리를 계산해야 합니다. 디버거에서 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 결과를 보면 이러한 암시적 계산이 수행되며, 여기에는 몇 가지 고려해야 할 사항이 있습니다. 쿼리를 계산할 때마다 일정 시간이 소요됩니다. 결과 노드를 확장할 때 일정 시간이 소요됩니다. 일부 쿼리의 경우 계산을 반복하면 성능이 상당히 저하될 수 있습니다. 쿼리를 계산할 때 데이터의 값이나 프로그램의 상태가 변경되는 의도하지 않은 결과가 나타날 수 있습니다. 모든 쿼리에서 예기치 않은 결과가 나타나는 것은 아닙니다. 부작용 없이 쿼리를 안전 하 게 계산할 수 있는지를 확인 하려면 쿼리를 구현 하는 코드를 이해 해야 합니다. 자세한 내용은 참조 [부작용과 식](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e)합니다.  
  
## <a name="edit-and-continue"></a>편집하며 계속하기  
 편집하며 계속하기에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 변경할 수 없습니다. 디버깅 세션 중에 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문을 추가, 제거 또는 변경하면 이러한 변경이 편집하며 계속하기에서 지원되지 않는다는 대화 상자가 표시됩니다. 이때 변경 내용을 취소할 수도 있고, 디버깅 세션을 중지하고 편집된 코드로 새 세션을 다시 시작할 수도 있습니다.  
  
 또한 편집하며 계속하기에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문에 사용된 변수의 형식 또는 값을 변경할 수 없습니다. 이 경우에도 변경 내용을 취소할 수도 있고, 디버깅 세션을 중지하고 다시 시작할 수도 있습니다.  
  
 Visual C#에서 Visual Studio에서 사용할 수 없습니다 편집 하며 계속 하기에 들어 있는 메서드의 어떠한 코드에에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 합니다.  
  
 Visual Studio에서 Visual basic에서 사용할 수 있습니다 편집 하며 계속 하기에서 비-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드를 포함 하는 메서드가 에서도 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 합니다. 또한 변경 작업으로 인해 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리의 줄 번호가 변경되는 경우에도 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문 앞에 코드를 추가하거나 제거할 수 있습니다. Visual Basic 디버깅에 대 한 환경 이외[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드 동일 하 게 유지 하기 전의 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 도입 되었습니다. 그러나 디버깅을 중지하고 변경 내용을 적용하는 경우가 아니면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 변경, 추가 또는 제거할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드 디버그](/visualstudio/debugger/debugging-managed-code)  
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
