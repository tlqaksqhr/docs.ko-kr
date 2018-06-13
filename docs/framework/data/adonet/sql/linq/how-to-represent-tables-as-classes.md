---
title: '방법: 클래스로 테이블 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 363efa4e4a6e3e7cfb757ee554e24a7963882278
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362979"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="96dad-102">방법: 클래스로 테이블 표현</span><span class="sxs-lookup"><span data-stu-id="96dad-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="96dad-103">사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 데이터베이스 테이블과 연결 된 엔터티 클래스로 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96dad-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="96dad-104">데이터베이스 테이블에 클래스를 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="96dad-104">To map a class to a database table</span></span>  
  
-   <span data-ttu-id="96dad-105"><xref:System.Data.Linq.Mapping.TableAttribute> 특성을 클래스 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96dad-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96dad-106">예제</span><span class="sxs-lookup"><span data-stu-id="96dad-106">Example</span></span>  
 <span data-ttu-id="96dad-107">다음 코드에서는 `Customer` 클래스를 `Customers` 데이터베이스 테이블과 연결된 엔터티 클래스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96dad-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="96dad-108">이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96dad-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="96dad-109">이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="96dad-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96dad-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96dad-110">See Also</span></span>  
 [<span data-ttu-id="96dad-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="96dad-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="96dad-112">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="96dad-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
