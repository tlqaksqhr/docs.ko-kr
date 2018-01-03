---
title: "방법: 기본 키 표현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: cf1ba7d0f08d6b0a7dc37af233ad27695cde2a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="dc038-102">방법: 기본 키 표현</span><span class="sxs-lookup"><span data-stu-id="dc038-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="dc038-103">사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 속성 또는 데이터베이스 열에 대 한 기본 키를 나타내는 필드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc038-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="dc038-104">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc038-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="dc038-105">에서는 기본 키로 계산된 열을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc038-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="dc038-106">속성 또는 필드를 기본 키로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="dc038-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="dc038-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc038-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="dc038-108">값을 `true`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc038-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc038-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc038-109">See Also</span></span>  
 [<span data-ttu-id="dc038-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="dc038-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="dc038-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="dc038-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
