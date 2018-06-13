---
title: '&#39;&lt;typename&gt; &#39; 대리자 형식이'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595650"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="ed557-102">&#39;&lt;typename&gt; &#39; 대리자 형식이</span><span class="sxs-lookup"><span data-stu-id="ed557-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="ed557-103">'\<형식 이름 >' 대리자 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed557-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="ed557-104">대리자 구문에는 인수 목록으로 단일 AddressOf 식만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed557-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="ed557-105">종종 AddressOf 식은 대리자 구문 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed557-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="ed557-106">A `New` 대리자 클래스의 인스턴스를 만드는 절 대리 생성자에는 잘못 된 인수 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed557-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="ed557-107">한 번만 제공할 수 있습니다 `AddressOf` 새 대리자 인스턴스를 만들 때 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed557-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="ed557-108">전달 하지 않으면 모든 인수는 대리 생성자에 단일 인수를 전달 하는 경우 올바르지 않은 한 또는 둘 이상의 인수를 전달 하는 경우이 오류가 발생할 수 있습니다 `AddressOf` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed557-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="ed557-109">**오류 ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="ed557-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed557-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ed557-110">To correct this error</span></span>  
  
-   <span data-ttu-id="ed557-111">단일을 사용 하 여 `AddressOf` 대리자 클래스에 대 한 인수 목록에서 식의 `New` 절.</span><span class="sxs-lookup"><span data-stu-id="ed557-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed557-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed557-112">See Also</span></span>  
 [<span data-ttu-id="ed557-113">New 연산자</span><span class="sxs-lookup"><span data-stu-id="ed557-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="ed557-114">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="ed557-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="ed557-115">대리자</span><span class="sxs-lookup"><span data-stu-id="ed557-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="ed557-116">방법: 대리자 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="ed557-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
