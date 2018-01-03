---
title: "방법: 계산 열 표현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 42afded36f6006f369dfddb7ed3a51598b3fc33a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="34222-102">방법: 계산 열 표현</span><span class="sxs-lookup"><span data-stu-id="34222-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="34222-103">사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성 내용이 계산의 결과 열을 나타내도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="34222-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="34222-104">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34222-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="34222-105">에서는 기본 키로 계산된 열을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34222-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="34222-106">계산된 열을 나타내려면</span><span class="sxs-lookup"><span data-stu-id="34222-106">To represent a computed column</span></span>  
  
1.  <span data-ttu-id="34222-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34222-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="34222-108">수식의 문자열 표현을 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="34222-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34222-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34222-109">See Also</span></span>  
 [<span data-ttu-id="34222-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="34222-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="34222-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="34222-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
