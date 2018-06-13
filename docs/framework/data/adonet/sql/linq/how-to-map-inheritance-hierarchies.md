---
title: '방법: 상속 계층 구조 매핑'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 627baf61902877390b0b2c88bf25438cb26c6491
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355361"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="62f01-102">방법: 상속 계층 구조 매핑</span><span class="sxs-lookup"><span data-stu-id="62f01-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="62f01-103">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]에서 상속 매핑을 구현하려면 다음 단계의 설명과 같이 상속 계층 구조의 루트 클래스에 특성 및 특성 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-103">To implement inheritance mapping in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="62f01-104">Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 상속 계층 구조를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-104">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span> <span data-ttu-id="62f01-105">참조 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62f01-106">서브클래스에는 특수 특성 또는 속성이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="62f01-107">특히 서브클래스에는 <xref:System.Data.Linq.Mapping.TableAttribute> 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="62f01-108">상속 계층 구조를 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="62f01-108">To map an inheritance hierarchy</span></span>  
  
1.  <span data-ttu-id="62f01-109">루트 클래스에 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2.  <span data-ttu-id="62f01-110">또한 루트 클래스에 계층 구조의 각 클래스에 대한 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3.  <span data-ttu-id="62f01-111">각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="62f01-112">이 속성에는 이 데이터 행이 속한 클래스 또는 서브클래스를 나타내기 위해 데이터베이스 테이블의 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 열에 표시되는 값이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4.  <span data-ttu-id="62f01-113">또한 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="62f01-114">이 속성에는 키 값이 의미하는 클래스 또는 서브클래스를 지정하는 값이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5.  <span data-ttu-id="62f01-115"><xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성 중 하나의 특성에만 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="62f01-116">이 속성은 지정 하는 *대체 (fallback)* 데이터베이스 테이블의 판별자 값 하나라도 일치 하지 않는 경우 매핑 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 상속 매핑의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6.  <span data-ttu-id="62f01-117"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 특성에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="62f01-118">이 속성은 열에 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 값이 저장됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62f01-119">예제</span><span class="sxs-lookup"><span data-stu-id="62f01-119">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62f01-120">Visual Studio를 사용 하는 경우 사용할 수 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 상속을 구성 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-120">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to configure inheritance.</span></span> <span data-ttu-id="62f01-121">참조 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="62f01-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="62f01-122">다음 코드 예제에서는 `Vehicle`이 루트 클래스로 정의되어 있으며 이전 단계는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 계층 구조를 설명하기 위해 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62f01-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="62f01-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62f01-123">See Also</span></span>  
 [<span data-ttu-id="62f01-124">상속 지원</span><span class="sxs-lookup"><span data-stu-id="62f01-124">Inheritance Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)  
 [<span data-ttu-id="62f01-125">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="62f01-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
