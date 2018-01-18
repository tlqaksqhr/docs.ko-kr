---
title: "기본 데이터 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9249a98c8a6c60d51039b6348a41c4f5805865f0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="basic-data-types"></a><span data-ttu-id="69aa6-102">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="69aa6-102">Basic Data Types</span></span>
<span data-ttu-id="69aa6-103">LINQ to SQL 쿼리는 Microsoft SQL Server에서 실행되기 전에 Transact-SQL로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-103">Because LINQ to SQL queries translate to Transact-SQL before they are executed on the Microsoft SQL Server.</span></span> <span data-ttu-id="69aa6-104">따라서 LINQ to SQL에서는 SQL Server에서 기본 데이터 형식에 대해 지원하는 기본 제공 함수 대부분을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-104">LINQ to SQL supports much of the same built-in functionality that SQL Server does for basic data types.</span></span>  
  
## <a name="casting"></a><span data-ttu-id="69aa6-105">캐스팅</span><span class="sxs-lookup"><span data-stu-id="69aa6-105">Casting</span></span>  
 <span data-ttu-id="69aa6-106">SQL Server 내에 비슷한 유효한 변환이 있는 경우 암시적 또는 명시적 캐스팅을 사용하여 소스 CLR 형식에서 대상 CLR 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-106">Implicit or explicit casts are enabled from a source CLR type to a target CLR type if there is a similar valid conversion within SQL Server.</span></span> <span data-ttu-id="69aa6-107">CLR 캐스팅에 대 한 자세한 내용은 참조 [CType 함수](~/docs/visual-basic/language-reference/functions/ctype-function.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) 및 [으로](~/docs/csharp/language-reference/keywords/as.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-107">For more information about CLR casting, see [CType Function](~/docs/visual-basic/language-reference/functions/ctype-function.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and [as](~/docs/csharp/language-reference/keywords/as.md).</span></span> <span data-ttu-id="69aa6-108">변환 후 캐스팅은 CLR 식에서 수행된 작업 동작을 변경하여 기본적으로 대상 형식에 매핑되는 다른 CLR 식의 동작과 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-108">After conversion, casts change the behavior of operations performed on a CLR expression to match the behavior of other CLR expressions that naturally map to the destination type.</span></span> <span data-ttu-id="69aa6-109">캐스팅은 또한 상속 매핑의 컨텍스트에서 변환 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-109">Casts are also translatable in the context of inheritance mapping.</span></span> <span data-ttu-id="69aa6-110">개체는 보다 구체적인 엔터티 하위 형식에 캐스팅되어 하위 형식의 특정 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-110">Objects can be cast to more specific entity subtypes so that their subtype-specific data can be accessed.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="69aa6-111">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="69aa6-111">Equality Operators</span></span>  
 <span data-ttu-id="69aa6-112">LINQ to SQL에서는 LINQ to SQL 쿼리 내의 기본 데이터 형식에 다음과 같은 같음 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-112">LINQ to SQL supports the following equality operators on basic data types inside LINQ to SQL queries:</span></span>  
  
-   <span data-ttu-id="69aa6-113">같음 연산자 및 같지 않음 연산자: 같음 연산자 및 같지 않음 연산자는 숫자 <xref:System.Boolean>, <xref:System.DateTime> 및 <xref:System.TimeSpan> 형식에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-113">Equal and Inequality Operator: Equality and inequality operators are supported for numeric <xref:System.Boolean>, <xref:System.DateTime>, and <xref:System.TimeSpan> types.</span></span> <span data-ttu-id="69aa6-114">에 대 한 자세한 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 연산자 `=` 및 `<>`, 참조 [비교 연산자](~/docs/visual-basic/language-reference/operators/comparison-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-114">For more about [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] operators `=` and `<>`, see [Comparison Operators](~/docs/visual-basic/language-reference/operators/comparison-operators.md).</span></span> <span data-ttu-id="69aa6-115">C# 비교 연산자에 대 한 자세한 내용은 `==` 및 `!=`, 참조 [= = 연산자](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) 및 [! = 연산자](~/docs/csharp/language-reference/operators/not-equal-operator.md)각각</span><span class="sxs-lookup"><span data-stu-id="69aa6-115">For more information about C# comparison operators `==` and `!=`, see [== Operator](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) and [!= Operator](~/docs/csharp/language-reference/operators/not-equal-operator.md), respectively</span></span>  
  
-   <span data-ttu-id="69aa6-116">Is 연산자: `IS` 연산자에서는 상속 매핑이 사용되는 경우 변환이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-116">Is operator: The `IS` operator has a supported translation when inheritance mapping is being used.</span></span> <span data-ttu-id="69aa6-117">개체가 특정 엔터티 형식인지 여부를 확인하기 위해 판별자 열을 직접 테스트하는 대신에 사용되어 판별자 열에 대한 확인으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-117">It can be used instead of directly testing the discriminator column to determine whether an object is of a specific entity type, and is translated to a check on the discriminator column.</span></span> <span data-ttu-id="69aa6-118">Visual Basic 및 C#은 연산자에 대 한 자세한 내용은 참조 [Is 연산자](~/docs/visual-basic/language-reference/operators/is-operator.md) 및 [은](~/docs/csharp/language-reference/keywords/is.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa6-118">For more information about the Visual Basic and C# Is operators, see [Is Operator](~/docs/visual-basic/language-reference/operators/is-operator.md) and [is](~/docs/csharp/language-reference/keywords/is.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69aa6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69aa6-119">See Also</span></span>  
 [<span data-ttu-id="69aa6-120">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="69aa6-120">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="69aa6-121">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="69aa6-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
