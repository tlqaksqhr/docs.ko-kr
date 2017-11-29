---
title: "저장 프로시저"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1cf8d155dd04cd4f7b3f860186428c14ce4e462e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="stored-procedures"></a>저장 프로시저
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]개체 모델에서 메서드를 사용 하 여 데이터베이스에 저장된 프로시저를 나타냅니다. 필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 저장 프로시저로 지정합니다. 자세한 내용은 참조 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)합니다.  
  
 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 일반적으로 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 저장 프로시저를 매핑합니다. 이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 응용 프로그램에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: 행 집합 반환](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 데이터의 행을 반환하고 입력 매개 변수를 사용하는 방법에 대해 설명합니다.  
  
 [방법: 매개 변수를 사용 하는 저장된 프로시저를 사용 하 여](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 입력 및 출력 매개 변수를 사용하는 방법에 대해 설명합니다.  
  
 [방법: 여러 결과 도형에 매핑된 저장된 프로시저 사용](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 동일한 저장 프로시저에 다양한 모양의 반환을 제공하는 방법에 대해 설명합니다.  
  
 [방법: 순차적 결과 도형에 매핑된 저장된 프로시저 사용](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 반환 시퀀스에 다양한 모양을 제공하는 방법에 대해 설명합니다.  
  
 [저장된 프로시저를 사용 하 여 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 저장 프로시저를 사용하여 삽입, 업데이트 및 삭제 작업을 구현하는 방법에 대해 설명합니다.  
  
 [저장 프로시저 독점적으로 사용 하 여 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 저장 프로시저만 사용하여 삽입, 업데이트 및 삭제 작업을 구현하는 방법에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로그래밍 가이드](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 만들고 사용하는 방법에 대한 정보를 제공합니다.  
  
 [연습: 저장 프로시저만 사용 (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 Visual Basic에서 저장 프로시저를 사용하는 방법을 보여 주는 절차를 제공합니다.  
  
 [연습: 저장 프로시저만 사용 (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 C#에서 저장 프로시저를 사용하는 방법을 보여 주는 절차를 제공합니다.
