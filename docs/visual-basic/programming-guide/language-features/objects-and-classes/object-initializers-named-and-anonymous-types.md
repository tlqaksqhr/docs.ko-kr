---
title: "개체 이니셜라이저: 명명 된 형식과 익명 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
dev_langs:
- VB
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d3c89fb0a7b7c535f1b46c208ac47f58513208ba
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="4edc4-102">개체 이니셜라이저: 명명된 형식과 익명 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4edc4-102">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>
<span data-ttu-id="4edc4-103">개체 이니셜라이저를 사용 하는 단일 식을 사용 하 여 복잡 한 개체에 대 한 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-103">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="4edc4-104">명명 된 형식의 및 익명 형식의 인스턴스를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-104">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="4edc4-105">선언</span><span class="sxs-lookup"><span data-stu-id="4edc4-105">Declarations</span></span>  
 <span data-ttu-id="4edc4-106">명명 된 형식과 익명 형식의 인스턴스 선언은 수 거의 동일 보이지만 그 효과가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-106">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="4edc4-107">각 범주에는 기능과 자체의 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-107">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="4edc4-108">다음 예제에서는 선언 하 고 명명된 된 클래스의 인스턴스를 초기화 하는 편리한 방법을 `Customer`, 개체 이니셜라이저 목록을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-108">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="4edc4-109">키워드 다음에 클래스의 이름을 지정 됩니다 `New`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-109">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 <span data-ttu-id="4edc4-110">[!code-vb[VbVbalrObjectInit #&1;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-110">[!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-111">익명 형식에 사용할 수 있는 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-111">An anonymous type has no usable name.</span></span> <span data-ttu-id="4edc4-112">따라서 익명 형식의 인스턴스는 클래스 이름을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-112">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 <span data-ttu-id="4edc4-113">[!code-vb[VbVbalrObjectInit #&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-113">[!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-114">두 선언이의 결과 요구 사항을 동일 하지 않으면.</span><span class="sxs-lookup"><span data-stu-id="4edc4-114">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="4edc4-115">에 대 한 `namedCust`, `Customer` 있는 클래스는 `Name` 속성 이미 있어야 하며, 선언을 해당 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-115">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="4edc4-116">에 대 한 `anonymousCust`, 하나의 속성을 호출 하는 문자열에 있는 새 클래스를 정의 하는 컴파일러 `Name`, 해당 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-116">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="4edc4-117">명명 된 형식</span><span class="sxs-lookup"><span data-stu-id="4edc4-117">Named Types</span></span>  
 <span data-ttu-id="4edc4-118">개체 이니셜라이저는 형식의 생성자를 호출 하 고 다음 단일 문을 일부 또는 모든 속성의 값을 설정 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-118">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="4edc4-119">문에 대 한 적절 한 생성자를 호출 하는 컴파일러: 기본 생성자는 인수가 없는 제공한 또는 하나 이상의 인수를 전송 하는 경우 매개 변수화 된 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-119">The compiler invokes the appropriate constructor for the statement: the default constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="4edc4-120">그런 다음 이니셜라이저 목록에 소개 된 순서에 지정된 된 속성 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-120">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="4edc4-121">이니셜라이저 목록에서 각 초기화 구성 클래스의 멤버에는 초기 값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-121">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="4edc4-122">클래스를 정의 하는 경우 이름, 멤버의 데이터 형식이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-122">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="4edc4-123">다음 예제에서는 `Customer` 클래스 있어야 하며, 라는 멤버가 있어야 `Name` 및 `City` 문자열 값을 받아들일 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-123">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 <span data-ttu-id="4edc4-124">[!code-vb[VbVbalrObjectInit #&3;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-124">[!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-125">또는 다음 코드를 사용 하 여 동일한 결과 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-125">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 <span data-ttu-id="4edc4-126">[!code-vb[VbVbalrObjectInit #&4;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-126">[!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-127">만드는 다음 예제에 해당 하는 이러한 각 선언은 `Customer` 기본 생성자를 사용 하 여 개체를 다음에 대 한 초기 값을 지정는 `Name` 및 `City` 를 사용 하 여 속성을 `With` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-127">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the default constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 <span data-ttu-id="4edc4-128">[!code-vb[VbVbalrObjectInit #&5;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-128">[!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-129">하는 경우는 `Customer` 클래스에 대 한 값에서을 보낼 수 있도록 매개 변수가 있는 생성자를 포함 `Name`, 예를 들어 수 또한 선언 하 고 초기화는 `Customer` 다음과 같은 방법으로 개체:</span><span class="sxs-lookup"><span data-stu-id="4edc4-129">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 <span data-ttu-id="4edc4-130">[!code-vb[VbVbalrObjectInit #&6;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-130">[!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-131">다음 코드와 같이 모든 속성을 초기화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-131">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 <span data-ttu-id="4edc4-132">[!code-vb[VbVbalrObjectInit #&7;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-132">[!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-133">그러나 초기화 목록은 비워 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-133">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="4edc4-134">초기화 되지 않은 속성을 기본값으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-134">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="4edc4-135">명명 된 형식으로 형식 유추</span><span class="sxs-lookup"><span data-stu-id="4edc4-135">Type Inference with Named Types</span></span>  
 <span data-ttu-id="4edc4-136">선언에 대 한 코드를 줄일 수 `cust1` 개체 이니셜라이저 및 지역 형식 유추를 결합 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-136">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="4edc4-137">생략 하면이 `As` 변수 선언 절.</span><span class="sxs-lookup"><span data-stu-id="4edc4-137">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="4edc4-138">변수의 데이터 형식은 할당 하 여 생성 된 개체의 형식에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-138">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="4edc4-139">다음 예에서 유형의 `cust6` 는 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-139">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 <span data-ttu-id="4edc4-140">[!code-vb[VbVbalrObjectInit #&8;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-140">[!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]</span></span>  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="4edc4-141">명명 된 형식에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="4edc4-141">Remarks About Named Types</span></span>  
  
-   <span data-ttu-id="4edc4-142">클래스 멤버는 개체 이니셜라이저 목록에서 한 번 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-142">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="4edc4-143">선언 `cust7` 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-143">The declaration of `cust7` causes an error.</span></span>  
  
     <span data-ttu-id="4edc4-144">[!code-vb[VbVbalrObjectInit #&9;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-144">[!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]</span></span>  
  
-   <span data-ttu-id="4edc4-145">자신 또는 다른 필드를 초기화 하는 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-145">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="4edc4-146">초기화 된에 대 한 다음 선언 처럼 전에 멤버에 액세스 하는 경우 `cust8`, 기본 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-146">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="4edc4-147">개체 이니셜라이저를 사용 하는 선언을 처리 될 때 가장 먼저 발생 하는 주의 적절 한 생성자가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-147">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="4edc4-148">그런 다음 이니셜라이저 목록에서 개별 필드 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-148">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="4edc4-149">다음 예제에서의 기본값에 대 한 `Name` 에 대해 할당 `cust8`, 초기화 된 값에 할당 됩니다 `cust9`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-149">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     <span data-ttu-id="4edc4-150">[!code-vb[VbVbalrObjectInit #&10;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-150">[!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]</span></span>  
  
     <span data-ttu-id="4edc4-151">다음 예제에서는 매개 변수가 있는 생성자를 사용 하 여 `cust3` 및 `cust4` 선언 하 고 초기화 `cust10` 및 `cust11`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-151">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     <span data-ttu-id="4edc4-152">[!code-vb[VbVbalrObjectInit #&11;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-152">[!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]</span></span>  
  
-   <span data-ttu-id="4edc4-153">개체 이니셜라이저를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-153">Object initializers can be nested.</span></span> <span data-ttu-id="4edc4-154">다음 예에서 `AddressClass` 는 두 개의 속성이 있는 클래스 `City` 및 `State`, 및 `Customer` 클래스에는 `Address` 의 인스턴스가 속성 `AddressClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-154">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     <span data-ttu-id="4edc4-155">[!code-vb[VbVbalrObjectInit #&12;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-155">[!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]</span></span>  
  
-   <span data-ttu-id="4edc4-156">초기화 목록은 비워 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-156">The initialization list cannot be empty.</span></span>  
  
-   <span data-ttu-id="4edc4-157">초기화 되는 인스턴스 개체 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-157">The instance being initialized cannot be of type Object.</span></span>  
  
-   <span data-ttu-id="4edc4-158">초기화 되는 클래스 멤버는 공유 멤버, 읽기 전용 멤버, 상수 또는 메서드 호출 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-158">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
-   <span data-ttu-id="4edc4-159">초기화 되는 클래스 멤버는 인덱싱된 하거나 한정 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-159">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="4edc4-160">다음 예제에서는 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-160">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="4edc4-161">익명 형식</span><span class="sxs-lookup"><span data-stu-id="4edc4-161">Anonymous Types</span></span>  
 <span data-ttu-id="4edc4-162">익명 형식을 명시적으로 정의 하지 않은 새 형식 및 이름을의 인스턴스를 만들 개체 이니셜라이저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-162">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="4edc4-163">대신, 컴파일러는 개체 이니셜라이저 목록에서 지정한 속성에 따라 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-163">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="4edc4-164">형식의 이름을 지정 되어 있지 않으므로 것 이라고는 *익명 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-164">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="4edc4-165">예를 들어, 다음 선언을 대 한 이전에 비교 `cust6`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-165">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 <span data-ttu-id="4edc4-166">[!code-vb[VbVbalrObjectInit #&13;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-166">[!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]</span></span>  
  
 <span data-ttu-id="4edc4-167">구문적으로 다른 점은 없습니다 이름이 지정 되 면 `New` 데이터 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-167">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="4edc4-168">그러나 일어나는 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-168">However, what happens is quite different.</span></span> <span data-ttu-id="4edc4-169">컴파일러는 두 개의 속성이 있는 새 익명 형식을 정의 `Name` 및 `City`, 지정된 된 값을 사용 하 여 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-169">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="4edc4-170">형식 유추의 종류를 결정 `Name` 및 `City` 예제 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-170">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4edc4-171">익명 형식의 이름은 컴파일러에 의해 생성 되 고 컴파일할 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-171">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="4edc4-172">코드 사용 하거나 익명 형식의 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-172">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="4edc4-173">사용할 수 없습니다 형식의 이름을 사용할 수 없어서는 `As` 선언 하는 절 `cust13`합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-173">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="4edc4-174">해당 형식 유추 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-174">Its type must be inferred.</span></span> <span data-ttu-id="4edc4-175">런타임에 바인딩을 사용 하지 않고 지역 변수에 익명 형식의 사용이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-175">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="4edc4-176">익명 형식에 대 한 중요 한 지원을 제공 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-176">Anonymous types provide critical support for [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries.</span></span> <span data-ttu-id="4edc4-177">쿼리에서 익명 형식 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 및 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-177">For more information about the use of anonymous types in queries, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="4edc4-178">익명 형식에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="4edc4-178">Remarks About Anonymous Types</span></span>  
  
-   <span data-ttu-id="4edc4-179">일반적으로 익명 형식 선언에서 속성의 전체 또는 대부분 됩니다 키워드를 입력 하 여 표시 되는 키 속성을 `Key` 속성 이름 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-179">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     <span data-ttu-id="4edc4-180">[!code-vb[VbVbalrObjectInit #&14;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-180">[!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]</span></span>  
  
     <span data-ttu-id="4edc4-181">키 속성에 대 한 자세한 내용은 참조 [키](../../../../visual-basic/language-reference/modifiers/key.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-181">For more information about key properties, see [Key](../../../../visual-basic/language-reference/modifiers/key.md).</span></span>  
  
-   <span data-ttu-id="4edc4-182">명명 된 형식과 마찬가지로, 이니셜라이저 목록에 익명 형식 정의 하나 이상의 속성을 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-182">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     <span data-ttu-id="4edc4-183">[!code-vb[VbVbalrObjectInit #&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-183">[!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span></span>  
  
-   <span data-ttu-id="4edc4-184">익명 형식의 인스턴스를 선언 하는 컴파일러는 일치 하는 익명 형식 정의 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-184">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="4edc4-185">이름 및 속성의 데이터 형식을 인스턴스 선언에서 수행 되 고 정의에 컴파일러에 의해 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-185">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="4edc4-186">속성은 라는, 명명 된 형식에 대 한 것 처럼 미리 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-186">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="4edc4-187">형식은 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-187">Their types are inferred.</span></span> <span data-ttu-id="4edc4-188">속성의 데이터 형식을 사용 하 여 지정할 수 없습니다는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="4edc4-188">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
-   <span data-ttu-id="4edc4-189">익명 형식 이름 및 해당 속성의 값 다른 여러 가지 방법으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-189">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="4edc4-190">예를 들어, 익명 형식 속성의 이름 및 변수는 이름 또는 값과 다른 개체의 속성 값을 모두 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-190">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     <span data-ttu-id="4edc4-191">[!code-vb[VbVbalrObjectInit #&15;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="4edc4-191">[!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]</span></span>  
  
     <span data-ttu-id="4edc4-192">익명 형식의 속성을 정의 하기 위한 옵션에 대 한 자세한 내용은 참조 [하는 방법: 익명 형식 선언에서 속성 이름 유추 및 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4edc4-192">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edc4-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4edc4-193">See Also</span></span>  
 <span data-ttu-id="4edc4-194">[지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="4edc4-194">[Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="4edc4-195"> [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="4edc4-195"> [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="4edc4-196"> [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="4edc4-196"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="4edc4-197"> [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md) </span><span class="sxs-lookup"><span data-stu-id="4edc4-197"> [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md) </span></span>  
<span data-ttu-id="4edc4-198"> [키](../../../../visual-basic/language-reference/modifiers/key.md) </span><span class="sxs-lookup"><span data-stu-id="4edc4-198"> [Key](../../../../visual-basic/language-reference/modifiers/key.md) </span></span>  
<span data-ttu-id="4edc4-199"> [방법: 개체 이니셜라이저를 사용하여 개체 선언](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)</span><span class="sxs-lookup"><span data-stu-id="4edc4-199"> [How to: Declare an Object by Using an Object Initializer](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)</span></span>
