---
title: "선언된 요소 참조(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9b3847164b4e577a9265a746b9329218b4af928b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="03078-102">선언된 요소 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03078-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="03078-103">코드에서 선언 된 요소를 참조 하는 경우는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에서 참조를 해당 이름의 적절 한 선언에 있는 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-103">When your code refers to a declared element, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="03078-104">이름이 같은 둘 이상의 요소가 선언 된 경우 요소를 참조할 수는 제어할 수 있습니다 *조건에 맞는* 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="03078-105">컴파일러는 이름 선언에 대 한 이름 참조를 일치 시 키 려 고 *가장 좁은 범위*합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="03078-106">즉 못하여 참조가 코드로 시작 하 고 다음 요소가 포함 된 수준을 통해 바깥쪽으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="03078-107">다음 예제에서는 이름이 같은 두 변수에 대 한 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03078-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="03078-108">이 예제에서는 두 개의 변수 선언, 각각의 명명 `totalCount`, 서로 다른 수준의 모듈의 범위 내에서 `container`합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="03078-109">때 프로시저 `showCount` 표시 `totalCount` 한정자 없이 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러는 로컬 선언 내부 즉 가장 좁은 범위에서 선언에 대 한 참조를 확인 `showCount`합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-109">When the procedure `showCount` displays `totalCount` without qualification, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="03078-110">모듈인 `totalCount` 포함 하는 모듈와 `container`, 컴파일러는 광범위 한 범위에서 선언에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="03078-111">요소 이름 한정</span><span class="sxs-lookup"><span data-stu-id="03078-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="03078-112">이 검색 프로세스를 무시 하 고 수행 해야 더 넓은 범위에 선언 된 이름을 지정 하려는 경우 *한정* 포함 하는 요소로 더 넓은 범위의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="03078-113">경우에 따라 포함 하는 요소를 정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="03078-114">하면 이름이 한정 앞에 대상 요소가 정의 되어 식별 하는 정보가 소스 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="03078-115">이 정보 라고는 *한정 문자열*합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="03078-116">하나를 포함 하거나 더 많은 네임 스페이스 및 모듈의 경우, 클래스 또는 구조체.</span><span class="sxs-lookup"><span data-stu-id="03078-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="03078-117">한정 문자열 모듈, 클래스 또는 대상 요소가 포함 된 구조체에 명확 하 게 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="03078-118">컨테이너는 다시 다른 포함 하는 요소, 일반적으로 네임 스페이스에에서 위치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="03078-119">한정 문자열에 여러 포함 된 요소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="03078-120">해당 이름을 정규화 하 여 선언 된 요소에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="03078-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="03078-121">요소가 정의 된 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="03078-122">여기에 네임 스페이스 또는 네임 스페이스의 계층 구조가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="03078-123">가장 낮은 수준의 네임 스페이스 내에서 요소는 모듈, 클래스 또는 구조체에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="03078-124">대상 요소의 위치에 따라 한정 경로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="03078-125">최상위 네임 스페이스를 가진 시작한 가장 낮은 수준의 네임 스페이스에 계속 모듈, 클래스 또는 구조체를 포함 하는 대상 요소 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="03078-126">경로 있는 각 요소에는 뒤에 오는 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="03078-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="03078-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="03078-128">대상 요소에 대 한 한정 문자열을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="03078-129">에 마침표 (`.`) 경로 있는 모든 요소 뒤 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="03078-130">응용 프로그램에서 한정 문자열의 모든 요소에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="03078-131">식 또는 대입문이 일반적인 방법으로 참조 하는 대상 요소를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="03078-132">대상 요소 이름을 한정 문자열 앞에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="03078-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="03078-133">이름은 마침표 다음에 나와야 (`.`) 모듈, 클래스 또는 구조는 요소가 포함 된 다음에 오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="03078-134">컴파일러를 대상 요소 참조 일치 시킬 수는 명확 하 고 명확한 선언의 찾을 한정 문자열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="03078-135">또한 응용 프로그램에 동일한 이름을 가진 둘 이상의 프로그래밍 요소에 액세스 하는 경우 이름 참조를 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="03078-136">예를 들어는 <xref:System.Windows.Forms> 및 <xref:System.Web.UI.WebControls> 두 네임 스페이스를 포함 한 `Label` 클래스 (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> 및 <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="03078-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="03078-137">응용 프로그램 모두를 사용 하거나 자체 정의 하는 경우 `Label` 클래스를 서로 다른 구별 해야 `Label` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="03078-138">변수 선언에 네임 스페이스 또는 가져오기 별칭을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="03078-139">다음 예제에서는 가져오기 별칭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="03078-140">포함 된 요소의 다른 멤버</span><span class="sxs-lookup"><span data-stu-id="03078-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="03078-141">다른 클래스 또는 구조체의 공유 되지 않는 멤버를 사용 하면 먼저 변수 또는 구조체 또는 클래스의 인스턴스를 가리키는 식을 사용 하 여 멤버 이름을 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="03078-142">다음 예에서 `demoClass` 라는 클래스의 인스턴스가 `class1`합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="03078-143">클래스 이름 자체는 되지 않은 멤버를 한 정하는 데 사용할 수 없습니다 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="03078-144">개체 변수에 인스턴스를 먼저 만들어야 (이 경우 `demoClass`) 변수 이름으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="03078-145">클래스 또는 구조체에는 `Shared` 멤버 클래스 또는 구조체 이름 또는 변수 또는 인스턴스를 가리키는 식과 해당 멤버를 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="03078-146">모듈에는 별도 모든 인스턴스가 하 고 모든 해당 멤버는 `Shared` 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="03078-147">따라서 모듈 이름으로 모듈 멤버를 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="03078-148">다음 예제에서는 모듈 멤버 프로시저에 대 한 정규화 된 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03078-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="03078-149">이 예제에서는 두 개의 선언 `Sub` 이라는 프로시저 `perform`, 서로 다른 모듈에 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="03078-150">각 모듈 자체 내에서 한정 하지 않고 지정할 수 있지만 다른 곳에서 참조 하는 경우 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="03078-151">마지막에 참조 `module3` 사용할 수 없는 `perform`, 컴파일러에서 해당 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="03078-152">프로젝트에 대 한 참조</span><span class="sxs-lookup"><span data-stu-id="03078-152">References to Projects</span></span>  
 <span data-ttu-id="03078-153">사용 하도록 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 다른 프로젝트에 정의 된 요소를 먼저 설정 해야는 *참조* 해당 프로젝트의 어셈블리 또는 형식 라이브러리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="03078-154">참조를 설정 하려면 클릭 **참조 추가** 에 **프로젝트** 메뉴를 사용 하거나 사용 하 여는 [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 명령줄 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="03078-155">예를 들어의 XML 개체 모델을 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="03078-156">대 한 참조를 설정 하는 경우는 <xref:System.Xml> 네임 스페이스를 선언 하 고 사용할 수의 해당 클래스와 같은 <xref:System.Xml.XmlDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="03078-157">다음 예제에서는 <xref:System.Xml.XmlDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="03078-158">요소를 포함 하는 가져오기</span><span class="sxs-lookup"><span data-stu-id="03078-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="03078-159">사용할 수는 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 를 *가져올* 모듈이 나 사용 하려는 클래스를 포함 하는 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="03078-160">이 이름을 정규화 하지 않고 가져온된 네임 스페이스에 정의 된 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="03078-161">다음 예제에서는 이전 예제를 가져오려면 다시 작성 한는 <xref:System.Xml> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="03078-162">또한는 `Imports` 문에서 정의할 수 있습니다는 *가져오기 별칭* 각 가져온된 네임 스페이스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="03078-163">이 소스 코드를 더 짧게 만들어 더 쉽게 읽을 수 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="03078-164">다음 예제에서는 다시 사용 하도록 이전 예제의 작성 `xD` 별칭으로는 <xref:System.Xml> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="03078-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="03078-165">`Imports` 문으로 하지 요소 만들 다른 프로젝트에서 응용 프로그램에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="03078-166">즉, 참조 설정의 현재 위치를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="03078-167">네임 스페이스를 방금 가져오면 해당 네임 스페이스에 정의 된 이름을 정규화 하는 요구 사항을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="03078-168">사용할 수도 있습니다는 `Imports` 모듈, 클래스, 구조체 및 열거형을 가져올 계정.</span><span class="sxs-lookup"><span data-stu-id="03078-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="03078-169">다음 한정자 없이 가져온 요소의 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="03078-170">그러나 비공유 멤버의 클래스와 구조체는 변수 또는 구조체 또는 클래스의 인스턴스를 가리키는 식으로 항상 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="03078-171">명명 지침</span><span class="sxs-lookup"><span data-stu-id="03078-171">Naming Guidelines</span></span>  
 <span data-ttu-id="03078-172">동일한 이름의 두 개 이상의 프로그래밍 요소를 정의 하는 경우는 *이름 모호성* 컴파일러에서이 이름에 대 한 참조를 확인 하려고 할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="03078-173">범위를 하나 정의 두 번 이상 또는 정의가 없는 범위에 포함 된 경우 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="03078-174">예를 들어이 도움말 페이지에 "정규화 된 참조 예"를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="03078-175">모든 요소에 고유한 이름을 지정 하 여 이름 모호성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="03078-176">다음 네임 스페이스, 모듈 또는 클래스를 사용 하 여 이름을 한정 하지 않고도 모든 요소에 대 한 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="03078-177">실수로 잘못 된 요소를 참조 하는 가능성 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="03078-178">섀도잉</span><span class="sxs-lookup"><span data-stu-id="03078-178">Shadowing</span></span>  
 <span data-ttu-id="03078-179">두 개의 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나가 숨길 수, 또는 *그림자*, 다른 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03078-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="03078-180">숨겨진된는 요소는 참조;에 사용할 수 없습니다. 대신, 코드 섀도잉 된 요소 이름을 사용의 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러 숨기는 요소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="03078-181">보다 자세한 내용 및 예제를 참조 하십시오. [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03078-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03078-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03078-182">See Also</span></span>  
 [<span data-ttu-id="03078-183">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="03078-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="03078-184">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="03078-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="03078-185">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="03078-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="03078-186">변수</span><span class="sxs-lookup"><span data-stu-id="03078-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="03078-187">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="03078-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="03078-188">New 연산자</span><span class="sxs-lookup"><span data-stu-id="03078-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="03078-189">공용</span><span class="sxs-lookup"><span data-stu-id="03078-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
