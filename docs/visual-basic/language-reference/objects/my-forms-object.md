---
title: "My.Forms 개체"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fe548caacf2c8e7498e3b7abc814b4f89af9b3d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="68449-102">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="68449-102">My.Forms Object</span></span>
<span data-ttu-id="68449-103">현재 프로젝트에 선언 된 각 Windows form의 인스턴스에 액세스 하기 위한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68449-104">설명</span><span class="sxs-lookup"><span data-stu-id="68449-104">Remarks</span></span>  
 <span data-ttu-id="68449-105">`My.Forms` 개체는 현재 프로젝트에 각 폼의 인스턴스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="68449-106">속성의 이름 속성에 액세스 하는 폼의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="68449-107">제공한 폼에 액세스할 수 있습니다는 `My.Forms` 한정 하지 않고 폼의 이름을 사용 하 여 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="68449-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="68449-108">동일 하기 때문에 속성 이름에서 폼의 형식 이름으로, 이렇게 하면 기본 인스턴스가 이전의 처럼 폼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="68449-109">예를 들어 `My.Forms.Form1.Show`은 `Form1.Show`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="68449-110">`My.Forms` 개체는 현재 프로젝트와 관련 된 양식에을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="68449-111">참조 된 Dll에 선언 된 폼에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="68449-112">DLL을 제공 하는 폼에 액세스 하려면로 작성 된 폼의 정규화 된 이름을 사용 해야 *DllName*. *생략*합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="68449-113">사용할 수는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> 속성 응용 프로그램의 모든 열려 있는 폼의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68449-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="68449-114">개체와 해당 속성은 Windows 응용 프로그램에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="68449-115">속성</span><span class="sxs-lookup"><span data-stu-id="68449-115">Properties</span></span>  
 <span data-ttu-id="68449-116">각 속성은 `My.Forms` 개체는 현재 프로젝트에 폼의 인스턴스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="68449-117">속성의 이름 속성에 액세스 하는 폼의 이름과 동일 이며 속성 형식은 폼의 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68449-118">이름 충돌이 발생 하는 경우 폼에 액세스할 수 속성 이름이 *RootNamespace*_*Namespace*\_*생략*합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="68449-119">예를 들어 이라는 두 개의 폼 `Form1.`루트 네임 스페이스에 다음이 형식 중 하나가 것 `WindowsApplication1` 및 네임 스페이스에 `Namespace1`, 해당 폼을 통해 액세스 하는 것 `My.Forms.WindowsApplication1_Namespace1_Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="68449-120">`My.Forms` 개체는 시작 시에 생성 된 응용 프로그램의 기본 폼의 인스턴스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="68449-121">다른 모든 폼에 대 한는 `My.Forms` 개체에 액세스 하 고 저장할 때 폼의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68449-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="68449-122">해당 속성에 액세스 하는 후속 시도 폼의 해당 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="68449-123">할당 하 여 폼의 삭제할 수 있습니다 `Nothing` 해당 폼에 대 한 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="68449-124">속성 setter 호출은 <xref:System.Windows.Forms.Form.Close%2A> 메서드는 폼의 다음 할당 `Nothing` 은 저장 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="68449-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="68449-125">이외의 모든 값을 할당 하는 경우 `Nothing` 속성 setter를 throw 한 <xref:System.ArgumentException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="68449-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="68449-126">속성이 있는지 여부를 테스트할 수 있습니다는 `My.Forms` 개체를 사용 하 여 폼의 인스턴스는 저장 된 `Is` 또는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="68449-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="68449-127">이러한 연산자를 사용 하 여 속성의 값이 인지 확인 하기 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68449-128">일반적으로 `Is` 또는 `IsNot` 연산자에는 비교를 수행 하는 속성의 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68449-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="68449-129">그러나 현재 저장 하는 경우 `Nothing`, 속성 폼의 새 인스턴스를 만들고 다음 해당 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="68449-130">Visual Basic 컴파일러의 속성을 처리 하는 반면는 `My.Forms` 알리고 다르게 개체는 `Is` 또는 `IsNot` 연산자를 해당 값을 변경 하지 않고 속성의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68449-131">예</span><span class="sxs-lookup"><span data-stu-id="68449-131">Example</span></span>  
 <span data-ttu-id="68449-132">이 예제에서는 기본 제목을 변경 `SidebarMenu` 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="68449-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="68449-133">이 예제가 작동 하려면 프로젝트 라는 폼 있어야 `SidebarMenu`합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="68449-134">이 코드는 Windows 응용 프로그램 프로젝트에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="68449-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68449-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68449-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="68449-136">프로젝트 형식에 따라 가용성</span><span class="sxs-lookup"><span data-stu-id="68449-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="68449-137">프로젝트 형식</span><span class="sxs-lookup"><span data-stu-id="68449-137">Project type</span></span>|<span data-ttu-id="68449-138">사용 가능</span><span class="sxs-lookup"><span data-stu-id="68449-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="68449-139">Windows 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="68449-139">Windows Application</span></span>|<span data-ttu-id="68449-140">**예**</span><span class="sxs-lookup"><span data-stu-id="68449-140">**Yes**</span></span>|  
|<span data-ttu-id="68449-141">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="68449-141">Class Library</span></span>|<span data-ttu-id="68449-142">아니요</span><span class="sxs-lookup"><span data-stu-id="68449-142">No</span></span>|  
|<span data-ttu-id="68449-143">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="68449-143">Console Application</span></span>|<span data-ttu-id="68449-144">아니요</span><span class="sxs-lookup"><span data-stu-id="68449-144">No</span></span>|  
|<span data-ttu-id="68449-145">Windows 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="68449-145">Windows Control Library</span></span>|<span data-ttu-id="68449-146">아니요</span><span class="sxs-lookup"><span data-stu-id="68449-146">No</span></span>|  
|<span data-ttu-id="68449-147">웹 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="68449-147">Web Control Library</span></span>|<span data-ttu-id="68449-148">아니요</span><span class="sxs-lookup"><span data-stu-id="68449-148">No</span></span>|  
|<span data-ttu-id="68449-149">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="68449-149">Windows Service</span></span>|<span data-ttu-id="68449-150">아니요</span><span class="sxs-lookup"><span data-stu-id="68449-150">No</span></span>|  
|<span data-ttu-id="68449-151">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="68449-151">Web Site</span></span>|<span data-ttu-id="68449-152">아니요</span><span class="sxs-lookup"><span data-stu-id="68449-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68449-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68449-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="68449-154">개체</span><span class="sxs-lookup"><span data-stu-id="68449-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="68449-155">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="68449-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="68449-156">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="68449-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="68449-157">응용 프로그램 폼 액세스</span><span class="sxs-lookup"><span data-stu-id="68449-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
