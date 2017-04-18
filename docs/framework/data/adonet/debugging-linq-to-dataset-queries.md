---
title: "LINQ to DataSet 쿼리 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# LINQ to DataSet 쿼리 디버깅
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]은 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드 디버깅을 지원합니다.  하지만 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드와 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]이 아닌 관리 코드 디버깅 간에는 몇 가지 차이점이 있습니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문으로 단계별 실행, 중단점 설정 및 디버거 창에 표시된 결과 보기와 같은 대부분의 디버깅 기능을 사용할 수 있지만,  지연된 쿼리 실행에는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 코드를 디버깅할 때 고려해야 하는 몇 가지 의도하지 않은 결과가 발생할 수 있으며 편집하며 계속하기 사용과 관련된 몇 가지 제한이 있습니다.  이 항목에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]이 아닌 관리 코드와 비교하여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에 고유한 디버깅 특성에 대해 설명합니다.  
  
## 결과 보기  
 DataTips, 조사식 창 및 간략한 조사식 대화 상자를 사용하여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문의 결과를 볼 수 있습니다.  소스 창을 사용할 때 소스 창의 쿼리 위에 포인터를 올려 놓으면 DataTips가 나타납니다.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 변수를 복사하여 조사식 창이나 간략한 조사식 대화 상자에 붙여 넣을 수 있습니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서 쿼리는 작성되거나 선언될 때 계산되는 것이 아니라 쿼리가 실행될 때에만 계산됩니다.  이를 *지연된 실행*이라고 합니다.  따라서 쿼리가 계산되기 전까지는 쿼리 변수에 값이 없습니다.  자세한 내용은 [LINQ to DataSet의 쿼리](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)을 참조하세요.  
  
 쿼리 결과를 표시하려면 디버거에서 쿼리를 계산해야 합니다.  디버거에서 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 결과를 보면 이러한 암시적 계산이 수행되며, 여기에는 몇 가지 고려해야 할 사항이 있습니다.  쿼리를 계산할 때마다 일정 시간이 소요됩니다.  결과 노드를 확장할 때 일정 시간이 소요됩니다.  일부 쿼리의 경우 계산을 반복하면 성능이 상당히 저하될 수 있습니다.  쿼리를 계산할 때 데이터의 값이나 프로그램의 상태가 변경되는 의도하지 않은 결과가 나타날 수 있습니다.  모든 쿼리에서 예기치 않은 결과가 나타나는 것은 아닙니다.  의도하지 않은 결과가 나타나지 않고 쿼리를 안전하게 계산할 수 있는지 확인하려면 쿼리를 구현하는 코드를 이해해야 합니다.  자세한 내용은 [파생 작업과 식](../Topic/Side%20Effects%20and%20Expressions.md)을 참조하세요.  
  
## 편집하며 계속하기  
 편집하며 계속하기에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 변경할 수 없습니다.  디버깅 세션 중에 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문을 추가, 제거 또는 변경하면 이러한 변경이 편집하며 계속하기에서 지원되지 않는다는 대화 상자가 표시됩니다.  이때 변경 내용을 취소할 수도 있고, 디버깅 세션을 중지하고 편집된 코드로 새 세션을 다시 시작할 수도 있습니다.  
  
 또한 편집하며 계속하기에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문에 사용된 변수의 형식 또는 값을 변경할 수 없습니다.  이 경우에도 변경 내용을 취소할 수도 있고, 디버깅 세션을 중지하고 다시 시작할 수도 있습니다.  
  
 Visual Studio의 Visual C\#에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리가 들어 있는 메서드의 어떠한 코드에 대해서도 편집하며 계속하기를 사용할 수 없습니다.  
  
 Visual Studio의 Visual Basic에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]이 아닌 코드에 대해 편집하며 계속하기를 사용할 수 있습니다. 이는 메서드에 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리가 있는 경우에도 가능합니다.  또한 변경 작업으로 인해 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리의 줄 번호가 변경되는 경우에도 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 문 앞에 코드를 추가하거나 제거할 수 있습니다.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]이 아닌 코드에 대한 Visual Basic 디버깅 환경은 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]이 도입되기 전과 동일합니다.  그러나 디버깅을 중지하고 변경 내용을 적용하는 경우가 아니면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 변경, 추가 또는 제거할 수 없습니다.  
  
## 참고 항목  
 [관리 코드 디버깅](../Topic/Debugging%20Managed%20Code.md)   
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)