---
title: 형식화된 데이터 집합
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 67c1d3a190c5a4f046d7c7da5ebbf98395a96341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="typed-datasets"></a><span data-ttu-id="2f5d1-102">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="2f5d1-102">Typed DataSets</span></span>
<span data-ttu-id="2f5d1-103"><xref:System.Data.DataSet>에서는 약한 형식의 변수를 통해 런타임에 바인딩하여 값에 액세스할 수도 있고 강력한 형식의 메타포를 통해 데이터에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="2f5d1-104">테이블 및 열에 속하는 **DataSet** 알기 쉬운 이름을 사용 하 여 액세스할 수 있으며 강력한 형식의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="2f5d1-105">형식화 된 **DataSet** 에서 파생 되는 클래스는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="2f5d1-106">따라서 모든 메서드, 이벤트 및 속성을 상속는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="2f5d1-107">또한 형식화 된 **DataSet** 강력한 형식의 메서드, 이벤트 및 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="2f5d1-108">즉, 컬렉션 기반의 메서드 대신 이름을 사용하여 테이블과 열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="2f5d1-109">형식화 된 코드의 가독성도 개선된 되지만 **DataSet** 에서는 VISUAL Studio 코드 편집기에 입력할 때 줄을 자동으로 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="2f5d1-110">또한 강력한 형식의 **DataSet** 컴파일 타임에 올바른 형식으로 값에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="2f5d1-111">강력한 형식의 **DataSet**, 코드 실행 시간 보다는 컴파일된은 때 형식 불일치 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f5d1-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2f5d1-112">In This Section</span></span>  
 [<span data-ttu-id="2f5d1-113">강력한 형식의 데이터 집합 생성</span><span class="sxs-lookup"><span data-stu-id="2f5d1-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="2f5d1-114">만들고 강력한 형식의 사용 하는 방법에 설명 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="2f5d1-115">형식화된 데이터 집합에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="2f5d1-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="2f5d1-116">강력한 형식의 생성 하는 데 XML 스키마 정의 언어 (XSD) 스키마에 주석을 추가 하는 방법을 설명 **데이터 집합**, 부여할 **데이터 집합** 기본 스키마를 변경 하지 않고 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d1-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5d1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f5d1-117">See Also</span></span>  
 [<span data-ttu-id="2f5d1-118">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="2f5d1-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="2f5d1-119">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="2f5d1-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
