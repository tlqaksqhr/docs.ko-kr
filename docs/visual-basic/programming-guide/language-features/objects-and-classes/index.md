---
title: "Visual Basic의 개체 및 클래스"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
caps.latest.revision: 26
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b71219fff8354497f34930232952262008f6cc78
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="objects-and-classes-in-visual-basic"></a><span data-ttu-id="84d27-102">Visual Basic의 개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="84d27-102">Objects and classes in Visual Basic</span></span>
<span data-ttu-id="84d27-103">*개체*는 하나의 단위로 취급될 수 있는 코드 및 데이터의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-103">An *object* is a combination of code and data that can be treated as a unit.</span></span> <span data-ttu-id="84d27-104">개체는 컨트롤 또는 폼과 같은 응용 프로그램의 부분일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-104">An object can be a piece of an application, like a control or a form.</span></span> <span data-ttu-id="84d27-105">전체 응용 프로그램이 하나의 개체가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-105">An entire application can also be an object.</span></span>

<span data-ttu-id="84d27-106">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 응용 프로그램을 만들 때는 계속해서 개체를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-106">When you create an application in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you constantly work with objects.</span></span> <span data-ttu-id="84d27-107">컨트롤, 폼 및 데이터 액세스 개체와 같은 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 제공하는 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-107">You can use objects provided by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], such as controls, forms, and data access objects.</span></span> <span data-ttu-id="84d27-108">또한 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 응용 프로그램 내에서 다른 응용 프로그램의 개체를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-108">You can also use objects from other applications within your [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] application.</span></span> <span data-ttu-id="84d27-109">개체를 직접 만들고 해당 개체에 대해 추가 속성 및 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-109">You can even create your own objects and define additional properties and methods for them.</span></span> <span data-ttu-id="84d27-110">개체는 프로그램에 대한 조립식 빌딩 블록처럼 작동합니다. 즉, 코드 조각을 한 번 작성한 후 반복해서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-110">Objects act like prefabricated building blocks for programs — they let you write a piece of code once and reuse it over and over.</span></span>  
  
<span data-ttu-id="84d27-111">이 항목에서는 개체에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-111">This topic discusses objects in detail.</span></span>  

## <a name="objects-and-classes"></a><span data-ttu-id="84d27-112">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="84d27-112">Objects and classes</span></span>
<span data-ttu-id="84d27-113">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]의 각 개체는 *클래스*로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-113">Each object in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is defined by a *class*.</span></span> <span data-ttu-id="84d27-114">클래스는 개체의 변수, 속성, 프로시저 및 이벤트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-114">A class describes the variables, properties, procedures, and events of an object.</span></span> <span data-ttu-id="84d27-115">개체는 클래스의 인스턴스입니다. 클래스를 정의한 후에는 필요한 수만큼 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-115">Objects are instances of classes; you can create as many objects you need once you have defined a class.</span></span>

<span data-ttu-id="84d27-116">개체와 해당 클래스 간의 관계를 이해하기 위해 쿠키 커터와 쿠키를 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-116">To understand the relationship between an object and its class, think of cookie cutters and cookies.</span></span> <span data-ttu-id="84d27-117">쿠키 커터는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-117">The cookie cutter is the class.</span></span> <span data-ttu-id="84d27-118">각 쿠키에 대해 크기와 모양 같은 특징을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-118">It defines the characteristics of each cookie, for example size and shape.</span></span> <span data-ttu-id="84d27-119">클래스는 개체를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-119">The class is used to create objects.</span></span> <span data-ttu-id="84d27-120">개체는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-120">The objects are the cookies.</span></span>

<span data-ttu-id="84d27-121">해당 멤버에 액세스하려면 먼저 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-121">You must create an object before you can access its members.</span></span>  

#### <a name="to-create-an-object-from-a-class"></a><span data-ttu-id="84d27-122">클래스에서 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="84d27-122">To create an object from a class</span></span>

1. <span data-ttu-id="84d27-123">개체를 만들려는 클래스를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-123">Determine from which class you want to create an object.</span></span>  

2. <span data-ttu-id="84d27-124">클래스 인스턴스를 할당할 수 있는 변수를 만드는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-124">Write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to create a variable to which you can assign a class instance.</span></span> <span data-ttu-id="84d27-125">변수는 원하는 클래스의 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-125">The variable should be of the type of the desired class.</span></span>

   ```vb
   Dim nextCustomer As customer
   ```

3. <span data-ttu-id="84d27-126">[New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 추가하여 변수를 클래스의 새 인스턴스로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-126">Add the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword to initialize the variable to a new instance of the class.</span></span>

   ```vb
   Dim nextCustomer As New customer
   ```

4. <span data-ttu-id="84d27-127">이제 개체 변수를 통해 클래스의 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-127">You can now access the members of the class through the object variable.</span></span>  

   ```vb
   nextCustomer.accountNumber = lastAccountNumber + 1  
   ```

> [!NOTE]
>  <span data-ttu-id="84d27-128">가능하면 항상 할당하려는 클래스 형식으로 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-128">Whenever possible, you should declare the variable to be of the class type you intend to assign to it.</span></span> <span data-ttu-id="84d27-129">이것을 *초기 바인딩*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-129">This is called *early binding*.</span></span> <span data-ttu-id="84d27-130">컴파일 시간의 클래스 형식을 모르는 경우 변수를 [개체 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)으로 선언하여 *런타임에 바인딩*을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-130">If you don't know the class type at compile time, you can invoke *late binding* by declaring the variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="84d27-131">그러나 런타임에 바인딩을 사용하면 성능이 저하되고 런타임 개체 멤버에 대한 액세스가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-131">However, late binding can make performance slower and limit access to the run-time object's members.</span></span> <span data-ttu-id="84d27-132">자세한 내용은 [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-132">For more information, see [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md).</span></span>

### <a name="multiple-instances"></a><span data-ttu-id="84d27-133">여러 인스턴스</span><span class="sxs-lookup"><span data-stu-id="84d27-133">Multiple instances</span></span>
<span data-ttu-id="84d27-134">클래스에서 새로 만든 개체들이 서로 동일한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-134">Objects newly created from a class are often identical to each other.</span></span> <span data-ttu-id="84d27-135">그렇지만 개별 개체로 존재할 경우 다른 인스턴스와 독립적으로 해당 변수 및 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-135">Once they exist as individual objects, however, their variables and properties can be changed independently of the other instances.</span></span> <span data-ttu-id="84d27-136">예를 들어 양식에 세 개의 확인란을 추가하는 경우 각 확인란 개체는 <xref:System.Windows.Forms.CheckBox> 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-136">For example, if you add three check boxes to a form, each check box object is an instance of the <xref:System.Windows.Forms.CheckBox> class.</span></span> <span data-ttu-id="84d27-137">개별 <xref:System.Windows.Forms.CheckBox> 개체는 클래스가 정의하는 공통된 특징 및 기능(속성, 변수, 프로시저 및 이벤트) 집합을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-137">The individual <xref:System.Windows.Forms.CheckBox> objects share a common set of characteristics and capabilities (properties, variables, procedures, and events) defined by the class.</span></span> <span data-ttu-id="84d27-138">그러나 각각은 고유한 이름을 가지며, 개별적으로 사용하거나 사용하지 않도록 설정하고, 폼의 다른 위치에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-138">However, each has its own name, can be separately enabled and disabled, and can be placed in a different location on the form.</span></span>

## <a name="object-members"></a><span data-ttu-id="84d27-139">개체 멤버</span><span class="sxs-lookup"><span data-stu-id="84d27-139">Object members</span></span>
<span data-ttu-id="84d27-140">개체는 응용 프로그램의 요소로, 클래스의 *인스턴스*를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-140">An object is an element of an application, representing an *instance* of a class.</span></span> <span data-ttu-id="84d27-141">필드, 속성, 메서드 및 이벤트는 개체의 구성 요소이며 해당 *멤버*로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-141">Fields, properties, methods, and events are the building blocks of objects and constitute their *members*.</span></span>

### <a name="member-access"></a><span data-ttu-id="84d27-142">멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="84d27-142">Member Access</span></span>
<span data-ttu-id="84d27-143">개체 변수의 이름, 마침표 (`.`) 및 멤버 이름을 순서대로 지정하여 개체 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-143">You access a member of an object by specifying, in order, the name of the object variable, a period (`.`), and the name of the member.</span></span> <span data-ttu-id="84d27-144">다음 예제에서는 <xref:System.Windows.Forms.Control.Text%2A> 개체의 <xref:System.Windows.Forms.Label> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-144">The following example sets the <xref:System.Windows.Forms.Control.Text%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a><span data-ttu-id="84d27-145">IntelliSense 멤버 목록</span><span class="sxs-lookup"><span data-stu-id="84d27-145">IntelliSense listing of members</span></span>
<span data-ttu-id="84d27-146">IntelliSense는 멤버 나열 옵션을 호출할 때(예를 들어 멤버 액세스 연산자로 마침표(`.`)를 입력할 때) 클래스의 멤버를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-146">IntelliSense lists members of a class when you invoke its List Members option, for example when you type a period (`.`) as a member-access operator.</span></span> <span data-ttu-id="84d27-147">해당 클래스의 인스턴스로 선언된 변수 이름 뒤에 마침표를 입력하는 경우 IntelliSense는 공유 멤버가 아닌 모든 인스턴스 멤버를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-147">If you type the period following the name of a variable declared as an instance of that class, IntelliSense lists all the instance members and none of the shared members.</span></span> <span data-ttu-id="84d27-148">클래스 이름 뒤에 마침표를 입력하는 경우 IntelliSense는 인스턴스 멤버가 아닌 모든 공유 멤버를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-148">If you type the period following the class name itself, IntelliSense lists all the shared members and none of the instance members.</span></span> <span data-ttu-id="84d27-149">자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-149">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>

### <a name="fields-and-properties"></a><span data-ttu-id="84d27-150">필드 및 속성</span><span class="sxs-lookup"><span data-stu-id="84d27-150">Fields and properties</span></span>
<span data-ttu-id="84d27-151">*필드* 및 *속성*은 개체에 저장된 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-151">*Fields* and *properties* represent information stored in an object.</span></span> <span data-ttu-id="84d27-152">프로시저에서 지역 변수를 검색하고 설정하는 것과 동일한 방식으로 대입문을 사용하여 해당 값을 검색하고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-152">You retrieve and set their values with assignment statements the same way you retrieve and set local variables in a procedure.</span></span> <span data-ttu-id="84d27-153">다음 예제에서는 <xref:System.Windows.Forms.Control.Width%2A> 속성을 검색하고 <xref:System.Windows.Forms.Label> 개체의 <xref:System.Windows.Forms.Control.ForeColor%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-153">The following example retrieves the <xref:System.Windows.Forms.Control.Width%2A> property and sets the <xref:System.Windows.Forms.Control.ForeColor%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

<span data-ttu-id="84d27-154">필드를 *멤버 변수*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-154">Note that a field is also called a *member variable*.</span></span>
  
<span data-ttu-id="84d27-155">다음 경우에 Property 프로시저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-155">Use property procedures when:</span></span>

- <span data-ttu-id="84d27-156">값을 설정하거나 검색할 시기와 방법을 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-156">You need to control when and how a value is set or retrieved.</span></span>

- <span data-ttu-id="84d27-157">속성에는 유효성을 검사해야 하는 잘 정의된 값 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-157">The property has a well-defined set of values that need to be validated.</span></span>

- <span data-ttu-id="84d27-158">값을 설정하면 `IsVisible` 속성과 같은 개체의 상태가 획기적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-158">Setting the value causes some perceptible change in the object's state, such as an `IsVisible` property.</span></span>

- <span data-ttu-id="84d27-159">속성을 설정하면 다른 내부 변수 또는 다른 속성의 값이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-159">Setting the property causes changes to other internal variables or to the values of other properties.</span></span>

- <span data-ttu-id="84d27-160">속성을 설정하거나 검색하려면 먼저 일련의 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-160">A set of steps must be performed before the property can be set or retrieved.</span></span>

<span data-ttu-id="84d27-161">다음 경우에 필드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-161">Use fields when:</span></span>  

- <span data-ttu-id="84d27-162">값이 자체적으로 유효성을 검사하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-162">The value is of a self-validating type.</span></span> <span data-ttu-id="84d27-163">예를 들어 `True` 또는 `False` 이외의 값이 `Boolean` 변수에 할당되면 오류 또는 자동 데이터 변환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-163">For example, an error or automatic data conversion occurs if a value other than `True` or `False` is assigned to a `Boolean` variable.</span></span>

- <span data-ttu-id="84d27-164">데이터 형식이 지원하는 범위의 모든 값이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-164">Any value in the range supported by the data type is valid.</span></span> <span data-ttu-id="84d27-165">`Single` 또는 `Double` 형식의 많은 속성이 여기에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-165">This is true of many properties of type `Single` or `Double`.</span></span>

- <span data-ttu-id="84d27-166">속성이 `String` 데이터 형식이고 문자열 크기 또는 값에 제약이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-166">The property is a `String` data type, and there is no constraint on the size or value of the string.</span></span>

- <span data-ttu-id="84d27-167">자세한 내용은 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-167">For more information, see [Property Procedures](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md).</span></span>

### <a name="methods"></a><span data-ttu-id="84d27-168">메서드</span><span class="sxs-lookup"><span data-stu-id="84d27-168">Methods</span></span>
<span data-ttu-id="84d27-169">*메서드*는 개체에서 수행할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-169">A *method* is an action that an object can perform.</span></span> <span data-ttu-id="84d27-170">예를 들어 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>는 콤보 상자에 새 항목을 추가하는 <xref:System.Windows.Forms.ComboBox> 개체의 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-170">For example, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> is a method of the <xref:System.Windows.Forms.ComboBox> object that adds a new entry to a combo box.</span></span>

<span data-ttu-id="84d27-171">다음 예제에서는 <xref:System.Windows.Forms.Timer> 개체의 <xref:System.Windows.Forms.Timer.Start%2A> 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-171">The following example demonstrates the <xref:System.Windows.Forms.Timer.Start%2A> method of a <xref:System.Windows.Forms.Timer> object.</span></span>

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

<span data-ttu-id="84d27-172">메서드는 개체에 의해 노출되는 *프로시저*일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-172">Note that a method is simply a *procedure* that is exposed by an object.</span></span>

<span data-ttu-id="84d27-173">자세한 내용은 [프로시저](../../../../visual-basic/programming-guide/language-features/procedures/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-173">For more information, see [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md).</span></span>

### <a name="events"></a><span data-ttu-id="84d27-174">이벤트</span><span class="sxs-lookup"><span data-stu-id="84d27-174">Events</span></span>
<span data-ttu-id="84d27-175">이벤트는 마우스 클릭이나 키 누르기와 같이 개체가 인식하는 동작이며 응답하기 위해 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-175">An event is an action recognized by an object, such as clicking the mouse or pressing a key, and for which you can write code to respond.</span></span> <span data-ttu-id="84d27-176">이벤트는 사용자 동작 또는 프로그램 코드의 결과로 발생하거나 시스템에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-176">Events can occur as a result of a user action or program code, or they can be caused by the system.</span></span> <span data-ttu-id="84d27-177">이벤트에 신호를 보내는 코드를 이벤트 *발생*이라고 하고, 신호에 응답하는 코드를 *처리*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-177">Code that signals an event is said to *raise* the event, and code that responds to it is said to *handle* it.</span></span>

<span data-ttu-id="84d27-178">개체에 의해 발생하고 다른 개체에서 처리되는 사용자 지정 이벤트를 개발할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-178">You can also develop your own custom events to be raised by your objects and handled by other objects.</span></span> <span data-ttu-id="84d27-179">자세한 내용은 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-179">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>

### <a name="instance-members-and-shared-members"></a><span data-ttu-id="84d27-180">인스턴스 멤버 및 공유 멤버</span><span class="sxs-lookup"><span data-stu-id="84d27-180">Instance members and shared members</span></span>
<span data-ttu-id="84d27-181">클래스에서 개체를 만들 때 결과는 해당 클래스의 인스턴스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-181">When you create an object from a class, the result is an instance of that class.</span></span> <span data-ttu-id="84d27-182">[Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드로 선언되지 않은 멤버는 해당 특정 인스턴스에 반드시 속하는 *인스턴스 멤버*입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-182">Members that are not declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword are *instance members*, which belong strictly to that particular instance.</span></span> <span data-ttu-id="84d27-183">한 인스턴스의 인스턴스 멤버는 동일한 클래스의 다른 인스턴스에 있는 동일한 멤버와 무관합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-183">An instance member in one instance is independent of the same member in another instance of the same class.</span></span> <span data-ttu-id="84d27-184">예를 들어 인스턴스 멤버 변수는 서로 다른 인스턴스에서 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-184">An instance member variable, for example, can have different values in different instances.</span></span>

<span data-ttu-id="84d27-185">`Shared` 키워드로 선언된 멤버는 특정 인스턴스가 아니라 전체 클래스에 속하는 *공유 멤버*입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-185">Members declared with the `Shared` keyword are *shared members*, which belong to the class as a whole and not to any particular instance.</span></span> <span data-ttu-id="84d27-186">공유 멤버는 사용자가 만드는 클래스의 인스턴스 수에 관계 없이, 사용자가 인스턴스를 만들지 않더라도 한 번만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-186">A shared member exists only once, no matter how many instances of its class you create, or even if you create no instances.</span></span> <span data-ttu-id="84d27-187">예를 들어 공유 멤버 변수는 클래스에 액세스할 수 있는 모든 코드에서 사용할 수 있는 하나의 값만 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-187">A shared member variable, for example, has only one value, which is available to all code that can access the class.</span></span>

#### <a name="accessing-nonshared-members"></a><span data-ttu-id="84d27-188">비공유 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="84d27-188">Accessing nonshared members</span></span>  

###### <a name="to-access-a-nonshared-member-of-an-object"></a><span data-ttu-id="84d27-189">개체의 비공유 멤버에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="84d27-189">To access a nonshared member of an object</span></span>

1. <span data-ttu-id="84d27-190">개체가 해당 클래스에서 생성되고 개체 변수에 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-190">Make sure the object has been created from its class and assigned to an object variable.</span></span>

   ```vb
   Dim secondForm As New System.Windows.Forms.Form  
   ```  

2. <span data-ttu-id="84d27-191">멤버에 액세스하는 문에서 개체 변수 이름 다음에 *멤버-액세스 연산자*(`.`)를 지정한 후 멤버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-191">In the statement that accesses the member, follow the object variable name with the *member-access operator* (`.`) and then the member name.</span></span>

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a><span data-ttu-id="84d27-192">공유 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="84d27-192">Accessing shared members</span></span>

###### <a name="to-access-a-shared-member-of-an-object"></a><span data-ttu-id="84d27-193">개체의 공유 멤버에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="84d27-193">To access a shared member of an object</span></span>

- <span data-ttu-id="84d27-194">클래스 이름 뒤에 *멤버-액세스 연산자*(`.`)를 지정한 다음 멤버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-194">Follow the class name with the *member-access operator* (`.`) and then the member name.</span></span> <span data-ttu-id="84d27-195">항상 클래스 이름을 통해 직접적으로 개체의 `Shared` 멤버에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-195">You should always access a `Shared` member of the object directly through the class name.</span></span>

   ```vb
   MsgBox("This computer is called " & Environment.MachineName)  
   ```

- <span data-ttu-id="84d27-196">클래스에서 개체를 이미 만들었으면 개체의 변수를 통해 `Shared` 멤버에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-196">If you have already created an object from the class, you can alternatively access a `Shared` member through the object's variable.</span></span>

### <a name="differences-between-classes-and-modules"></a><span data-ttu-id="84d27-197">클래스와 모듈 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="84d27-197">Differences between classes and modules</span></span>
<span data-ttu-id="84d27-198">클래스와 모듈 간의 주요 차이점은 클래스는 개체로 인스턴스화할 수 있지만 표준 모듈은 그럴 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-198">The main difference between classes and modules is that classes can be instantiated as objects while standard modules cannot.</span></span> <span data-ttu-id="84d27-199">표준 모듈의 데이터 복사본은 하나만 있으므로 프로그램의 한 부분이 표준 모듈의 공용 변수를 변경하면 프로그램의 다른 부분은 해당 변수를 읽을 때 동일한 값을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-199">Because there is only one copy of a standard module's data, when one part of your program changes a public variable in a standard module, any other part of the program gets the same value if it then reads that variable.</span></span> <span data-ttu-id="84d27-200">반면 개체 데이터는 인스턴스화된 각 개체에 대해 개별적으로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-200">In contrast, object data exists separately for each instantiated object.</span></span> <span data-ttu-id="84d27-201">또 다른 차이점은 표준 모듈과 달리 클래스는 인터페이스를 구현할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-201">Another difference is that unlike standard modules, classes can implement interfaces.</span></span>

> [!NOTE]
> <span data-ttu-id="84d27-202">`Shared` 한정자가 클래스 멤버에 적용되면 클래스의 특정 인스턴스가 아닌 클래스 자체에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-202">When the `Shared` modifier is applied to a class member, it is associated with the class itself instead of a particular instance of the class.</span></span> <span data-ttu-id="84d27-203">모듈 멤버에 액세스하는 것과 같은 방식으로 멤버에도 클래스 이름을 사용하여 직접 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-203">The member is accessed directly by using the class name, the same way module members are accessed.</span></span>

<span data-ttu-id="84d27-204">클래스와 모듈은 또한 해당 멤버의 범위가 각기 다를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-204">Classes and modules also use different scopes for their members.</span></span> <span data-ttu-id="84d27-205">클래스 내에 정의된 멤버는 클래스의 특정 인스턴스 범위를 벗어나지 않으며 개체의 수명 동안만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-205">Members defined within a class are scoped within a specific instance of the class and exist only for the lifetime of the object.</span></span> <span data-ttu-id="84d27-206">클래스 외부에서 클래스 멤버에 액세스하려면 *개체*.*멤버* 형식의 정규화된 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-206">To access class members from outside a class, you must use fully qualified names in the format of *Object*.*Member*.</span></span>

<span data-ttu-id="84d27-207">반면에 모듈 내에서 선언된 멤버는 기본적으로 공개적으로 액세스할 수 있으며 모듈에 액세스할 수 있는 모든 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-207">On the other hand, members declared within a module are publicly accessible by default, and can be accessed by any code that can access the module.</span></span> <span data-ttu-id="84d27-208">즉, 표준 모듈의 변수는 프로젝트의 모든 위치에서 볼 수 있으며 프로그램의 수명 동안 존재하기 때문에 결과적으로 전역 변수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-208">This means that variables in a standard module are effectively global variables because they are visible from anywhere in your project, and they exist for the life of the program.</span></span>

## <a name="reusing-classes-and-objects"></a><span data-ttu-id="84d27-209">클래스 및 개체 다시 사용</span><span class="sxs-lookup"><span data-stu-id="84d27-209">Reusing classes and objects</span></span>  
<span data-ttu-id="84d27-210">개체를 사용하면 변수 및 프로시저를 한 번 선언한 후 필요할 때마다 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-210">Objects let you declare variables and procedures once and then reuse them whenever needed.</span></span> <span data-ttu-id="84d27-211">예를 들어 응용 프로그램에 맞춤법 검사기를 추가하려는 경우 모든 변수 및 지원 함수를 정의하여 맞춤법 검사 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-211">For example, if you want to add a spelling checker to an application you could define all the variables and support functions to provide spell-checking functionality.</span></span> <span data-ttu-id="84d27-212">맞춤법 검사기를 클래스로 만드는 경우 컴파일된 어셈블리에 대한 참조를 추가하여 다른 응용 프로그램에서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-212">If you create your spelling checker as a class, you can then reuse it in other applications by adding a reference to the compiled assembly.</span></span> <span data-ttu-id="84d27-213">다른 사람이 이미 개발한 맞춤법 검사기 클래스를 사용하여 일부 작업을 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-213">Better yet, you may be able to save yourself some work by using a spelling checker class that someone else has already developed.</span></span>

<span data-ttu-id="84d27-214">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]에서는 사용할 수 있는 다양한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-214">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provides many examples of components that are available for use.</span></span> <span data-ttu-id="84d27-215">다음 예제에서는 <xref:System> 네임스페이스의 <xref:System.TimeZone> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-215">The following example uses the <xref:System.TimeZone> class in the <xref:System> namespace.</span></span> <span data-ttu-id="84d27-216"><xref:System.TimeZone>에서는 현재 컴퓨터 시스템의 표준 시간대에 대한 정보를 검색할 수 있도록 하는 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-216"><xref:System.TimeZone> provides members that allow you to retrieve information about the time zone of the current computer system.</span></span>

```vb
Public Sub examineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    MsgBox(s)
End Sub
```

<span data-ttu-id="84d27-217">앞의 예제에서 첫 번째 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)은 <xref:System.TimeZone> 형식의 개체 변수를 선언하고 이를 <xref:System.TimeZone.CurrentTimeZone%2A> 속성에 의해 반환된 <xref:System.TimeZone> 개체에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-217">In the preceding example, the first [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declares an object variable of type <xref:System.TimeZone> and assigns to it a <xref:System.TimeZone> object returned by the <xref:System.TimeZone.CurrentTimeZone%2A> property.</span></span>

## <a name="relationships-among-objects"></a><span data-ttu-id="84d27-218">개체 간 관계</span><span class="sxs-lookup"><span data-stu-id="84d27-218">Relationships among objects</span></span>  
<span data-ttu-id="84d27-219">개체는 여러 가지 방법으로 서로 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-219">Objects can be related to each other in several ways.</span></span> <span data-ttu-id="84d27-220">관계의 주요 종류로는 *계층적* 및 *포함*이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-220">The principal kinds of relationship are *hierarchical* and *containment*.</span></span>

### <a name="hierarchical-relationship"></a><span data-ttu-id="84d27-221">계층적 관계</span><span class="sxs-lookup"><span data-stu-id="84d27-221">Hierarchical relationship</span></span>
<span data-ttu-id="84d27-222">클래스가 보다 기본적인 클래스에서 파생되면 *계층적 관계*에 있다고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-222">When classes are derived from more fundamental classes, they are said to have a *hierarchical relationship*.</span></span> <span data-ttu-id="84d27-223">클래스 계층 구조는 보다 일반적인 클래스의 하위 항목을 설명하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-223">Class hierarchies are useful when describing items that are a subtype of a more general class.</span></span>

<span data-ttu-id="84d27-224">다음 예제에서는 일반적인 <xref:System.Windows.Forms.Button>처럼 작동하지만 전경색 및 배경색을 거꾸로 뒤집는 메서드도 제공하는 특수한 종류의 <xref:System.Windows.Forms.Button>을 정의하려 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-224">In the following example, suppose you want to define a special kind of <xref:System.Windows.Forms.Button> that acts like a normal <xref:System.Windows.Forms.Button> but also exposes a method that reverses the foreground and background colors.</span></span>

##### <a name="to-define-a-class-is-derived-from-an-already-existing-class"></a><span data-ttu-id="84d27-225">클래스가 기존 클래스에서 파생된다고 정의하려면</span><span class="sxs-lookup"><span data-stu-id="84d27-225">To define a class is derived from an already existing class</span></span>

1. <span data-ttu-id="84d27-226">[Class 문](../../../../visual-basic/language-reference/statements/class-statement.md)을 사용하여 필요한 개체를 만들 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-226">Use a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md) to define a class from which to create the object you need.</span></span>

   ```vb
   Public Class reversibleButton
   ```

   <span data-ttu-id="84d27-227">`End Class` 문은 클래스의 마지막 코드 줄 다음에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-227">Be sure an `End Class` statement follows the last line of code in your class.</span></span> <span data-ttu-id="84d27-228">기본적으로 IDE(통합 개발 환경)는 사용자가 `Class` 문을 입력하면 `End Class`를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-228">By default, the integrated development environment (IDE) automatically generates an `End Class` when you enter a `Class` statement.</span></span>

2. <span data-ttu-id="84d27-229">`Class` 문 바로 다음에 [Inherits 문](../../../../visual-basic/language-reference/statements/inherits-statement.md)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-229">Follow the `Class` statement immediately with an [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span> <span data-ttu-id="84d27-230">새 클래스가 파생되는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-230">Specify the class from which your new class derives.</span></span>  
  
   ```vb
   Inherits System.Windows.Forms.Button
   ```

  <span data-ttu-id="84d27-231">새 클래스는 기본 클래스에서 정의하는 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-231">Your new class inherits all the members defined by the base class.</span></span>

3. <span data-ttu-id="84d27-232">파생 클래스가 노출하는 추가 멤버에 대한 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-232">Add the code for the additional members your derived class exposes.</span></span> <span data-ttu-id="84d27-233">예를 들어 `reverseColors` 메서드를 추가할 수 있으며 이 경우 파생 클래스는 다음과 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-233">For example, you might add a `reverseColors` method, and your derived class might look as follows:</span></span>

   ```vb
   Public Class reversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub reverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   <span data-ttu-id="84d27-234">`reversibleButton` 클래스에서 개체를 만드는 경우 <xref:System.Windows.Forms.Button> 클래스의 모든 멤버뿐 아니라 `reverseColors` 메서드와 `reversibleButton`에 정의한 다른 모든 새 멤버에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-234">If you create an object from the `reversibleButton` class, it can access all the members of the <xref:System.Windows.Forms.Button> class, as well as the `reverseColors` method and any other new members you define on `reversibleButton`.</span></span>

<span data-ttu-id="84d27-235">파생 클래스는 해당 클래스의 기준이 되는 클래스에서 멤버를 상속하므로 클래스 계층 구조가 점점 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-235">Derived classes inherit members from the class they are based on, allowing you to add complexity as you progress in a class hierarchy.</span></span> <span data-ttu-id="84d27-236">자세한 내용은 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-236">For more information, see [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>

#### <a name="compiling-the-code"></a><span data-ttu-id="84d27-237">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="84d27-237">Compiling the code</span></span>
<span data-ttu-id="84d27-238">컴파일러에서 새 클래스를 파생하려는 원본 클래스에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-238">Be sure the compiler can access the class from which you intend to derive your new class.</span></span> <span data-ttu-id="84d27-239">이것은 이름을 완전히 한정하거나 앞의 예제에서와 같이 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)에서 해당 네임스페이스를 식별하는 것을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-239">This might mean fully qualifying its name, as in the preceding example, or identifying its namespace in an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="84d27-240">클래스가 다른 프로젝트에 있으면 해당 프로젝트에 대한 참조를 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-240">If the class is in a different project, you might need to add a reference to that project.</span></span> <span data-ttu-id="84d27-241">자세한 내용은 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d27-241">For more information, see [Managing references in a project](/visualstudio/ide/managing-references-in-a-project).</span></span>

### <a name="containment-relationship"></a><span data-ttu-id="84d27-242">포함 관계</span><span class="sxs-lookup"><span data-stu-id="84d27-242">Containment relationship</span></span>
<span data-ttu-id="84d27-243">개체를 연관지을 수 있는 또 다른 방법은 *포함 관계*입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-243">Another way that objects can be related is a *containment relationship*.</span></span> <span data-ttu-id="84d27-244">컨테이너 개체는 논리적으로 다른 개체를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-244">Container objects logically encapsulate other objects.</span></span> <span data-ttu-id="84d27-245">예를 들어 <xref:System.OperatingSystem> 개체에 논리적으로 <xref:System.Version> 개체를 포함하며, 이는 해당 <xref:System.OperatingSystem.Version%2A> 속성을 통해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-245">For example, the <xref:System.OperatingSystem> object logically contains a <xref:System.Version> object, which it returns through its <xref:System.OperatingSystem.Version%2A> property.</span></span> <span data-ttu-id="84d27-246">컨테이너 개체가 다른 개체를 물리적으로 포함하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-246">Note that the container object does not physically contain any other object.</span></span>

#### <a name="collections"></a><span data-ttu-id="84d27-247">컬렉션</span><span class="sxs-lookup"><span data-stu-id="84d27-247">Collections</span></span>
<span data-ttu-id="84d27-248">특정 형식의 개체 포함을 *컬렉션*으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-248">One particular type of object containment is represented by *collections*.</span></span> <span data-ttu-id="84d27-249">컬렉션은 열거할 수 있는 유사한 개체의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-249">Collections are groups of similar objects that can be enumerated.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="84d27-250">에서는 컬렉션의 항목을 반복할 수 있는 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)의 특수 구문을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-250"> supports a specific syntax in the [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) that allows you to iterate through the items of a collection.</span></span> <span data-ttu-id="84d27-251">또한 컬렉션을 사용하면<xref:Microsoft.VisualBasic.Collection.Item%2A>을 사용하여 인덱스별로 또는 고유 문자열에 연결하여 요소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-251">Additionally, collections often allow you to use an <xref:Microsoft.VisualBasic.Collection.Item%2A> to retrieve elements by their index or by associating them with a unique string.</span></span> <span data-ttu-id="84d27-252">컬렉션은 인덱스를 사용하지 않고도 항목을 추가 또는 제거할 수 있도록 하므로 배열보다 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-252">Collections can be easier to use than arrays because they allow you to add or remove items without using indexes.</span></span> <span data-ttu-id="84d27-253">사용 편의성 때문에 컬렉션을 폼 및 컨트롤을 저장하는 데 종종 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-253">Because of their ease of use, collections are often used to store forms and controls.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84d27-254">관련 항목</span><span class="sxs-lookup"><span data-stu-id="84d27-254">Related topics</span></span>  
 [<span data-ttu-id="84d27-255">연습: 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="84d27-255">Walkthrough: Defining Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)  
 <span data-ttu-id="84d27-256">클래스를 만드는 방법에 대한 단계별 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-256">Provides a step-by-step description of how to create a class.</span></span>  

 [<span data-ttu-id="84d27-257">오버로드된 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="84d27-257">Overloaded Properties and Methods</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods.md)  
 <span data-ttu-id="84d27-258">오버로드된 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="84d27-258">Overloaded Properties and Methods</span></span>  

 [<span data-ttu-id="84d27-259">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="84d27-259">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 <span data-ttu-id="84d27-260">상속 한정자, 메서드 및 속성 재정의, MyClass 및 MyBase에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-260">Covers inheritance modifiers, overriding methods and properties, MyClass, and MyBase.</span></span>  

 [<span data-ttu-id="84d27-261">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="84d27-261">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 <span data-ttu-id="84d27-262">클래스 인스턴스의 생성 및 삭제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-262">Discusses creating and disposing of class instances.</span></span>  

 [<span data-ttu-id="84d27-263">익명 형식</span><span class="sxs-lookup"><span data-stu-id="84d27-263">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 <span data-ttu-id="84d27-264">익명 형식을 만들고 사용하여 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-264">Describes how to create and use anonymous types, which allow you to create objects without writing a class definition for the data type.</span></span>  

 [<span data-ttu-id="84d27-265">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="84d27-265">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 <span data-ttu-id="84d27-266">단일 식을 사용하여 명명된 형식 및 무명 형식의 인스턴스를 만드는 데 사용되는 개체 이니셜라이저에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-266">Discusses object initializers, which are used to create instances of named and anonymous types by using a single expression.</span></span>  

 [<span data-ttu-id="84d27-267">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="84d27-267">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 <span data-ttu-id="84d27-268">무명 형식 선언에서 속성 이름 및 형식을 유추하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-268">Explains how to infer property names and types in anonymous type declarations.</span></span> <span data-ttu-id="84d27-269">성공 및 실패한 유추의 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84d27-269">Provides examples of successful and unsuccessful inference.</span></span>

