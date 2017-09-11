---
title: "함수 변환 (Visual Basic)의 적응성 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 3b74e134-e19b-44bc-8d06-e26c48305040
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 45e83c86b2cfd7bceef57dbf354e29cc35c56051
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="applicability-of-functional-transformation-visual-basic"></a><span data-ttu-id="09f94-102">함수 변환 (Visual Basic)의 적용 여부</span><span class="sxs-lookup"><span data-stu-id="09f94-102">Applicability of Functional Transformation (Visual Basic)</span></span>
<span data-ttu-id="09f94-103">순수 함수 변형은 광범위한 상황에서 적용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-103">Pure functional transformations are applicable in a wide variety of situations.</span></span>  
  
 <span data-ttu-id="09f94-104">함수 변환 방법은 구조화된 데이터의 쿼리와 조작에 이상적으로 적합하므로 LINQ 기술과 함께 사용하기에 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-104">The functional transformation approach is ideally suited for querying and manipulating structured data; therefore it fits well with LINQ technologies.</span></span> <span data-ttu-id="09f94-105">그러나 함수 변환은 LINQ보다 적용 가능성이 훨씬 큽니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-105">However, functional transformation has a much wider applicability than use with LINQ.</span></span> <span data-ttu-id="09f94-106">데이터를 변환하는 데 주로 집중하는 프로세스는 함수 변환의 대상으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-106">Any process where the main focus is on transforming data from one form to another should probably be considered as a candidate for functional transformation.</span></span>  
  
 <span data-ttu-id="09f94-107">이 방법은 처음에는 적합한 대상으로 보이지 않을 수 있는 많은 문제에 적용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-107">This approach is applicable to many problems that might not appear at first glance to be a candidate.</span></span> <span data-ttu-id="09f94-108">함수 변환을 LINQ와 함께 사용하거나 별도로 사용하는 경우 다음 영역에 대한 함수 변환을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-108">Used in conjunction with or separately from LINQ, functional transformation should be considered for the following areas:</span></span>  
  
-   <span data-ttu-id="09f94-109">XML 기반 문서.</span><span class="sxs-lookup"><span data-stu-id="09f94-109">XML-based documents.</span></span> <span data-ttu-id="09f94-110">XML 언어의 제대로 구성된 데이터는 함수 변형을 통해 쉽게 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-110">Well-formed data of any XML dialect can be easily manipulated through functional transformation.</span></span> <span data-ttu-id="09f94-111">자세한 내용은 참조 [함수 변환의 XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-111">For more information, see [Functional Transformation of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md).</span></span>  
  
-   <span data-ttu-id="09f94-112">다른 구조화된 파일 형식.</span><span class="sxs-lookup"><span data-stu-id="09f94-112">Other structured file formats.</span></span> <span data-ttu-id="09f94-113">Windows.ini 파일에서 일반 텍스트 문서에 이르는 대부분의 파일에는 분석과 변환에 적합한 구조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-113">From Windows.ini files to plain text documents, most files have some structure that lends itself to analysis and transformation.</span></span>  
  
-   <span data-ttu-id="09f94-114">데이터 스트리밍 프로토콜.</span><span class="sxs-lookup"><span data-stu-id="09f94-114">Data streaming protocols.</span></span> <span data-ttu-id="09f94-115">데이터를 통신 프로토콜로 인코딩하고 통신 프로토콜에서 데이터를 디코딩하는 작업을 간단한 함수 변환으로 나타낼 수 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-115">Encoding data into and decoding data from communication protocols can often be represented by a simple functional transform.</span></span>  
  
-   <span data-ttu-id="09f94-116">RDBMS 및 OODBMS 데이터.</span><span class="sxs-lookup"><span data-stu-id="09f94-116">RDBMS and OODBMS data.</span></span> <span data-ttu-id="09f94-117">XML과 같은 개체 지향 데이터베이스와 관계형 데이터베이스는 널리 사용되는 구조화된 데이터 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-117">Relational and object-oriented databases, just like XML, are widely-used structured data sources.</span></span>  
  
-   <span data-ttu-id="09f94-118">수학, 통계 및 과학 솔루션.</span><span class="sxs-lookup"><span data-stu-id="09f94-118">Mathematic, statistic, and science solutions.</span></span> <span data-ttu-id="09f94-119">이러한 분야에서는 중요한 문제를 시각화하거나, 예측하거나, 실제로 해결하는 데 도움을 주기 위해 큰 데이터 집합을 조작하는 일이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-119">These fields tend to manipulate large data sets to assist the user in visualizing, estimating, or actually solving non-trivial problems.</span></span>  
  
 <span data-ttu-id="09f94-120">에 설명 된 대로 [리팩터링에 순수 함수 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md), 순수 함수를 사용 하 여은 함수형 프로그래밍의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-120">As described in [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md), using pure functions is an example of functional programming.</span></span> <span data-ttu-id="09f94-121">순수 함수를 사용하면 즉각적인 혜택을 얻을 수 있을 뿐만 아니라 함수 변형 관점에서 문제에 대해 생각하는 귀중한 경험을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-121">In additional to their immediate benefits, using pure functions provides valuable experience in thinking about problems from a functional transformation perspective.</span></span> <span data-ttu-id="09f94-122">이 방법은 프로그램과 클래스 디자인에도 중요한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-122">This approach can also have major impact on program and class design.</span></span> <span data-ttu-id="09f94-123">이는 문제가 위에서 설명한 데이터 변환 솔루션에 적합한 경우 특히 해당되는 사실입니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-123">This is especially true when a problem lends itself to a data transformation solution as described above.</span></span>  
  
 <span data-ttu-id="09f94-124">이 자습서의 범위를 벗어나긴 하지만, 함수 변형 관점의 영향을 받는 디자인은 행위자로 개체보다 프로세스에 중점을 두는 경향이 있으며, 생성되는 솔루션은 개별 개체 상태 변경 대신 일련의 대규모 변형으로 구현되기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-124">Although they are beyond the scope of this tutorial, designs that are influenced by the functional transformation perspective tend to center on processes more than on objects as actors, and the resulting solution tends to be implemented as series of large-scale transformations, rather than individual object state changes.</span></span>  
  
 <span data-ttu-id="09f94-125">Visual Basic 명령형 방법과 함수형 방법의 지원 하므로 응용 프로그램에 최적인 디자인의 요소가 모두 통합 될 수 있습니다 반드시 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f94-125">Again, remember that Visual Basic supports both imperative and functional approaches, so the best design for your application might incorporate elements of both.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f94-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09f94-126">See Also</span></span>  
 <span data-ttu-id="09f94-127">[순수 함수 변환 (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="09f94-127">[Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
<span data-ttu-id="09f94-128"> [XML (Visual Basic)의 함수 변환](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="09f94-128"> [Functional Transformation of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md) </span></span>  
<span data-ttu-id="09f94-129"> [(Visual Basic) 순수 함수로 리팩터링](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="09f94-129"> [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)</span></span>
