---
title: Partial 메서드를 사용하여 비즈니스 논리 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: db18c48d697ae79f8c33c1674544f81cdd1c426a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361453"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="acaf8-102">Partial 메서드를 사용하여 비즈니스 논리 추가</span><span class="sxs-lookup"><span data-stu-id="acaf8-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="acaf8-103">사용자 지정할 수 있습니다 Visual Basic 및 C# 코드에서 생성 된 프로그램 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용 하 여 프로젝트 *부분 메서드*합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="acaf8-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 생성한 코드에는 부분 메서드의 일부로 시그니처를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="acaf8-105">메서드를 구현하려면 사용자 고유의 부분 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="acaf8-106">사용자 고유의 구현을 추가하지 않으면 컴파일러에서는 부분 메서드 시그니처를 취소하고 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 기본 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acaf8-107">Visual Studio를 사용 하는 경우 사용할 수 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 엔터티 클래스에 유효성 검사 및 기타 사용자 지정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-107">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="acaf8-108">예를 들어 Northwind 샘플 데이터베이스의 `Customer` 클래스에 대한 기본 매핑에는 다음 부분 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="acaf8-109">다음과 같은 코드를 사용자 고유의 부분 `Customer` 클래스에 추가하여 사용자 고유의 메서드를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="acaf8-110">이러한 접근 방식은 일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 `Insert`, `Update` 및 `Delete`에 대한 기본 메서드를 재정의하고 개체 수명 주기 이벤트 동안 속성의 유효성을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="acaf8-111">자세한 내용은 참조 [부분 메서드](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) 또는 [부분 (메서드) (C# 참조)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="acaf8-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acaf8-112">예제</span><span class="sxs-lookup"><span data-stu-id="acaf8-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="acaf8-113">설명</span><span class="sxs-lookup"><span data-stu-id="acaf8-113">Description</span></span>  
 <span data-ttu-id="acaf8-114">다음 예제에서는 SQLMetal와 같은 코드 생성 도구에서 정의한 `ExampleClass`를 먼저 보여 준 다음 두 개의 메서드 중 하나만 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="acaf8-115">코드</span><span class="sxs-lookup"><span data-stu-id="acaf8-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="acaf8-116">예제</span><span class="sxs-lookup"><span data-stu-id="acaf8-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="acaf8-117">설명</span><span class="sxs-lookup"><span data-stu-id="acaf8-117">Description</span></span>  
 <span data-ttu-id="acaf8-118">다음 예제에서는 `Shipper`와 `Order` 엔터티 간의 관계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="acaf8-119">메서드 중 부분 메서드는 `InsertShipper`와 `DeleteShipper`입니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="acaf8-120">이러한 메서드는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 매핑을 통해 제공된 기본 부분 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="acaf8-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="acaf8-121">코드</span><span class="sxs-lookup"><span data-stu-id="acaf8-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="acaf8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acaf8-122">See Also</span></span>  
 [<span data-ttu-id="acaf8-123">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="acaf8-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="acaf8-124">삽입, 업데이트 및 삭제 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="acaf8-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
