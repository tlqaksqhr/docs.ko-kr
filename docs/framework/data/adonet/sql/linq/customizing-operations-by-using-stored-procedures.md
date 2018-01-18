---
title: "저장 프로시저를 사용하여 작업 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 105f52b61d6b5c0b05bd08a9a1f6b1c07f94226d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="customizing-operations-by-using-stored-procedures"></a>저장 프로시저를 사용하여 작업 사용자 지정
저장 프로시저는 기본 동작 재정의에 대한 일반적인 접근 방식을 나타냅니다. 이 항목의 예제에서는 저장 프로시저에 대해 생성된 메서드 래퍼를 사용하는 방법과 저장 프로시저를 직접 호출하는 방법을 보여 줍니다.  
  
 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 경우 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 통해 저장 프로시저를 할당하여 삽입, 업데이트 및 삭제 작업을 수행할 수 있습니다.  
  
> [!NOTE]
>  데이터베이스에서 생성된 값을 다시 읽으려면 저장 프로시저에 출력 매개 변수를 사용합니다. 출력 매개 변수를 사용할 수 없는 경우 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서 생성된 재정의를 사용하지 말고 부분 메서드(Partial Method) 구현을 작성합니다. 데이터베이스에서 생성된 값에 매핑된 멤버는 `INSERT` 또는 `UPDATE` 작업이 성공적으로 완료된 후 적절한 값으로 설정되어야 합니다. 자세한 내용은 참조 [는에서 기본 동작 재정의 개발자의 책임](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)합니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예제에서는 파생 클래스의 재정의에 사용되는 저장 프로시저를 호출하기 위한 두 개의 메서드가 `Northwind` 클래스에 포함되어 있다고 가정합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 클래스에서는 재정의를 위해 이러한 메서드를 사용합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 `NorthwindThroughSprocs`와 같은 용도로 `Northwnd`를 사용할 수 있습니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [기본 동작 재정의에서 개발자의 책임](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
