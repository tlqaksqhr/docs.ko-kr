---
title: '방법: 변수에 두 개 이상의 값 사용(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 783c75ed4577831b7ca444870c97063e8a057346
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646684"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="0e071-102">방법: 변수에 두 개 이상의 값 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e071-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="0e071-103">변수에 둘 이상의 값으로 선언 하는 경우는 *복합 데이터 형식을*합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="0e071-104">[복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) 구조, 배열 및 클래스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="0e071-105">복합 데이터 형식의 변수에 기본 데이터 형식 및 기타 복합 형식의 조합을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="0e071-106">구조체와 클래스 코드 뿐만 아니라 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="0e071-107">변수에 두 개 이상의 값을</span><span class="sxs-lookup"><span data-stu-id="0e071-107">To hold more than one value in a variable</span></span>  
  
1.  <span data-ttu-id="0e071-108">변수를 사용 하려면 복합 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2.  <span data-ttu-id="0e071-109">복합 데이터 형식이 아직 정의 되지 않은 정의 변수에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="0e071-110">구조체를 정의 [Structure 문을](../../../../visual-basic/language-reference/statements/structure-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="0e071-111">정의 된 배열을 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="0e071-112">클래스를 정의 [Class 문](../../../../visual-basic/language-reference/statements/class-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3.  <span data-ttu-id="0e071-113">사용 하 여 변수를 선언는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="0e071-113">Declare your variable with a `Dim` statement.</span></span>  
  
4.  <span data-ttu-id="0e071-114">변수 이름 뒤에 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="0e071-114">Follow the variable name with an `As` clause.</span></span>  
  
5.  <span data-ttu-id="0e071-115">에 따라는 `As` 키워드와 적절 한 복합 데이터 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e071-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e071-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e071-116">See Also</span></span>  
 [<span data-ttu-id="0e071-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0e071-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="0e071-118">형식 문자</span><span class="sxs-lookup"><span data-stu-id="0e071-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="0e071-119">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0e071-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="0e071-120">구조체</span><span class="sxs-lookup"><span data-stu-id="0e071-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="0e071-121">배열</span><span class="sxs-lookup"><span data-stu-id="0e071-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="0e071-122">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="0e071-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="0e071-123">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="0e071-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
