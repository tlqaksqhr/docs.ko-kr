---
title: "Object 변수 또는 With 블록 변수가 설정 되지 않았다는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4db2c827c3e77cfa6cc51132f0d647a58c93c769
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="06bbb-102">Object 변수 또는 With 블록 변수가 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="06bbb-103">잘못 된 개체 변수가 참조 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="06bbb-104">여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="06bbb-105">변수는 형식을 지정 하지 않고 선언 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="06bbb-106">형식을 지정 하지 않고는 변수가 선언 된 기본값으로 입력 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="06bbb-107">예를 들어 선언 된 변수 `Dim x` 될의 형식은 `Object;` 선언 된 변수 `Dim x As String` 될의 형식은 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="06bbb-108">`Option Strict` 문이 암시적 형식 지정을 허용 하지 않는 한 `Object` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="06bbb-109">형식을 생략 하면 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="06bbb-110">참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="06bbb-111">가로 설정 하는 개체를 참조 하려고 합니다.`Nothing`</span><span class="sxs-lookup"><span data-stu-id="06bbb-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="06bbb-112">입니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-112">.</span></span>  
  
-   <span data-ttu-id="06bbb-113">배열 변수를 올바르게 선언 되지 않은의 요소에 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="06bbb-114">배열으로 선언 하는 예를 들어 `products() As String` 은 배열의 요소를 참조 하려고 하면 오류를 발생 `products(3) = "Widget"`합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="06bbb-115">배열에 요소가 고 개체로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="06bbb-116">액세스 코드를 넣을 `With...End With` 블록 초기화 되기 전에 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="06bbb-117">A `With...End With` 블록을 실행 하 여 초기화 해야는 `With` 문 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06bbb-118">이전 버전의 Visual Basic 또는 VBA에서이 오류도 트리거된 사용 하지 않고 값을 변수에 할당 하 여는 `Set` 키워드 (`x = "name"` 대신 `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="06bbb-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="06bbb-119">`Set` 키워드는 더 이상 Visual Basic.Net에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06bbb-120">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="06bbb-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="06bbb-121">설정 `Option Strict` 에 `On` 파일의 시작 부분에 다음 코드를 추가 하 여:</span><span class="sxs-lookup"><span data-stu-id="06bbb-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="06bbb-122">사용 하지 않으려는 경우 `Option Strict`, 형식을 사용 하지 않고 지정 된 모든 변수의 코드 검색 (`Dim x` 대신 `Dim x As String`) 지정 된 형식 선언에 추가 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="06bbb-123">가로 설정 하는 개체 변수를 참조 하지 확인 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="06bbb-124">키워드에 대 한 코드를 검색 `Nothing`, 개체를 설정 되지 않도록 코드를 수정 하 고 `Nothing` 참조 한 후 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="06bbb-125">액세스 하기 전에 모든 배열 변수는 차원이 구분 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="06bbb-126">배열의 처음 만들 때 차원을 할당 하거나 (`Dim x(5) As String` 대신 `Dim x() As String`), 사용 또는 `ReDim` 처음으로 액세스 하기 전에 배열의 크기를 설정 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="06bbb-127">있는지 확인 하면 `With` 블록을 실행 하 여 초기화는 `With` 문 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="06bbb-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06bbb-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06bbb-128">See Also</span></span>  
 <span data-ttu-id="06bbb-129">[개체 변수 선언](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="06bbb-129">[Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="06bbb-130"> [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="06bbb-130"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="06bbb-131"> [With...End With 문](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="06bbb-131"> [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
