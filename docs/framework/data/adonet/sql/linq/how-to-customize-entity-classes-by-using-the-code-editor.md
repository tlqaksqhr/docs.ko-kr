---
title: '방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정'
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 58544441ec722e5cf0e18c113bbce0bbf40b92bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360493"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="721af-102">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="721af-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="721af-103">Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 를 만들거나 해당 엔터티 클래스 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="721af-104">또한 사용자 고유의 매핑 코드를 작성 하거나 이미 생성 된 코드를 사용자 지정할 수는 Visual Studio 코드 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721af-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="721af-105">자세한 내용은 참조 [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="721af-106">이 단원의 항목에서는 개체 모델을 사용자 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="721af-107">방법: 데이터베이스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="721af-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="721af-108"><xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="721af-109">방법: 클래스로 테이블 표현</span><span class="sxs-lookup"><span data-stu-id="721af-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="721af-110"><xref:System.Data.Linq.Mapping.TableAttribute>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="721af-111">방법: 클래스 멤버로 열 표현</span><span class="sxs-lookup"><span data-stu-id="721af-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="721af-112"><xref:System.Data.Linq.Mapping.ColumnAttribute>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="721af-113">방법: 기본 키 표현</span><span class="sxs-lookup"><span data-stu-id="721af-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="721af-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="721af-115">방법: 데이터베이스 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="721af-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="721af-116"><xref:System.Data.Linq.Mapping.AssociationAttribute> 특성을 사용한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="721af-117">방법: 데이터베이스 생성 값으로 열 표현</span><span class="sxs-lookup"><span data-stu-id="721af-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="721af-118"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="721af-119">방법: 타임스탬프 또는 버전 열로 열 표현</span><span class="sxs-lookup"><span data-stu-id="721af-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="721af-120"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="721af-121">방법: 데이터베이스 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="721af-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="721af-122"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="721af-123">방법: 계산 열 표현</span><span class="sxs-lookup"><span data-stu-id="721af-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="721af-124"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="721af-125">방법: 전용 저장소 필드 지정</span><span class="sxs-lookup"><span data-stu-id="721af-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="721af-126"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="721af-127">방법: NULL 값을 허용하도록 열 표현</span><span class="sxs-lookup"><span data-stu-id="721af-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="721af-128"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="721af-129">방법: 상속 계층 구조 매핑</span><span class="sxs-lookup"><span data-stu-id="721af-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="721af-130">상속 계층 구조를 지정할 수 있는 매핑하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="721af-131">방법: 동시성 충돌 확인 지정</span><span class="sxs-lookup"><span data-stu-id="721af-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="721af-132"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="721af-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721af-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="721af-133">See Also</span></span>  
 [<span data-ttu-id="721af-134">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="721af-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
