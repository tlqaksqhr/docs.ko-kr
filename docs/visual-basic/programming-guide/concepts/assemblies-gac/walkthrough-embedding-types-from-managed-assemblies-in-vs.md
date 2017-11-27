---
title: "연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4411b40d8ffbdf2b74c49152db675286d91b43ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="3d6da-102">연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="3d6da-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="3d6da-103">강력한 이름의 관리되는 어셈블리에서 형식 정보를 포함하는 경우 응용 프로그램에서 유형을 느슨하게 연결하여 버전 독립성을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="3d6da-104">즉, 각 버전에 대해 컴파일하지 않고도 관리되는 라이브러리의 여러 버전에서 형식을 사용하도록 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="3d6da-105">형식 포함은 Microsoft Office의 자동화 개체를 사용하는 응용 프로그램과 같은 COM interop에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="3d6da-106">형식 정보를 포함하면 서로 다른 컴퓨터의 서로 다른 Microsoft Office 버전에서 동일한 빌드의 프로그램을 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="3d6da-107">그러나 완전하게 관리되는 솔루션에서도 형식 포함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="3d6da-108">다음과 같은 특징이 있는 어셈블리에서 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="3d6da-109">어셈블리는 하나 이상의 공용 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="3d6da-110">포함된 인터페이스는 `ComImport` 특성 및 `Guid` 특성(그리고 고유한 GUID)으로 주석이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="3d6da-111">어셈블리는 `ImportedFromTypeLib` 특성이나 `PrimaryInteropAssembly` 특성, 그리고 어셈블리 수준의 `Guid` 특성으로 주석이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="3d6da-112">(기본적으로 Visual Basic 프로젝트 템플릿에 포함 어셈블리 수준 `Guid` 특성입니다.)</span><span class="sxs-lookup"><span data-stu-id="3d6da-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="3d6da-113">포함할 수 있는 공용 인터페이스를 지정한 후에 이러한 인터페이스를 구현하는 런타임 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="3d6da-114">그런 다음 클라이언트 프로그램은 공용 인터페이스가 포함된 어셈블리를 참조하고 참조의 `Embed Interop Types` 속성을 `True`로 설정하여 디자인 타임에 해당 인터페이스의 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="3d6da-115">이는 명령줄 컴파일러를 사용하고 `/link` 컴파일러 옵션을 사용하여 어셈블리를 참조하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="3d6da-116">그러면 클라이언트 프로그램은 해당 인터페이스로 형식이 지정된 런타임 개체의 인스턴스를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="3d6da-117">강력한 이름의 런타임 어셈블리의 새 버전을 만들면 업데이트된 런타임 어셈블리로 클라이언트 프로그램을 다시 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="3d6da-118">대신, 클라이언트 프로그램은 공용 인터페이스에 대해 포함된 형식 정보를 통해 사용 가능한 런타임 어셈블리 버전을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="3d6da-119">형식 포함의 기본 기능은 COM interop 어셈블리에서 형식 정보를 포함하도록 지원하는 것이므로, 완전히 관리되는 솔루션에 형식 정보를 포함할 때 다음과 같은 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="3d6da-120">COM interop 관련 특성만 포함되고 다른 특성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="3d6da-121">형식이 제네릭 매개 변수를 사용하고 제네릭 매개 변수의 형식이 포함된 형식인 경우 해당 형식을 어셈블리 경계에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="3d6da-122">어셈블리 경계를 넘어가는 예로는 다른 어셈블리에서 메서드를 호출하는 경우 또는 다른 어셈블리에 정의된 형식에서 형식이 파생되는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="3d6da-123">상수는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="3d6da-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> 클래스는 포함된 형식을 키로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="3d6da-125">포함된 형식을 키로서 지원하도록 고유한 사전 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="3d6da-126">이 연습에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="3d6da-127">포함할 수 있는 형식 정보가 있는 공개 인터페이스와 함께 강력한 이름의 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="3d6da-128">해당 공용 인터페이스를 구현하는 강력한 이름의 런타임 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="3d6da-129">공용 인터페이스에서 형식 정보를 포함하고 런타임 어셈블리에서 클래스의 인스턴스를 만드는 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="3d6da-130">런타임 어셈블리를 수정하고 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="3d6da-131">클라이언트 프로그램을 실행하여, 클라이언트 프로그램을 다시 컴파일할 필요 없이 런타임 어셈블리의 새 버전이 사용되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="3d6da-132">인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="3d6da-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="3d6da-133">동등한 형식의 인터페이스 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3d6da-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="3d6da-134">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3d6da-135">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="3d6da-136">**템플릿** 창에서 **클래스 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="3d6da-137">**이름** 상자에 `TypeEquivalenceInterface`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="3d6da-138">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="3d6da-139">**솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="3d6da-140">파일 이름을 `ISampleInterface.vb`으로 바꾸고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="3d6da-141">파일 이름을 바꾸면 클래스 이름도 `ISampleInterface`로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="3d6da-142">이 클래스는 클래스에 대한 공용 인터페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="3d6da-143">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="3d6da-144">**컴파일** 탭을 클릭합니다. 개발 컴퓨터의 유효한 위치(예: `C:\TypeEquivalenceSample`)로 출력 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="3d6da-145">이 연습의 이후 단계에서도 이 위치가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="3d6da-146">프로젝트 속성을 편집하는 동안 **서명** 탭을 클릭합니다. **어셈블리 서명** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="3d6da-147">**강력한 이름 키 파일 선택** 목록에서 **<새로 만들기...>**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="3d6da-148">**키 파일 이름** 상자에 `key.snk`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="3d6da-149">**암호로 내 키 파일 보호** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="3d6da-150">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="3d6da-151">ISampleInterface.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="3d6da-152">ISampleInterface 인터페이스를 만드는 ISampleInterface 클래스 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```vb  
    Imports System.Runtime.InteropServices  
  
    <ComImport()>  
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>  
    Public Interface ISampleInterface  
        Sub GetUserInput()  
        ReadOnly Property UserInput As String  
    End Interface  
    ```  
  
7.  <span data-ttu-id="3d6da-153">**도구** 메뉴에서 **GUID 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="3d6da-154">**GUID 만들기** 대화 상자에서 **레지스트리 형식**과 **복사**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="3d6da-155">**끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="3d6da-156">`Guid` 특성에서 샘플 GUID를 삭제하고, **GUID 만들기** 대화 상자에서 복사한 GUID를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="3d6da-157">복사된 GUID에서 중괄호({})를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="3d6da-158">**프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-158">On the **Project** menu, click **Show All Files**.</span></span>  
  
10. <span data-ttu-id="3d6da-159">**솔루션 탐색기**를 확장 하 고는 **My Project** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="3d6da-160">AssemblyInfo.vb를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="3d6da-161">파일에 다음 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-161">Add the following attribute to the file.</span></span>  
  
    ```vb  
    <Assembly: ImportedFromTypeLib("")>  
    ```  
  
     <span data-ttu-id="3d6da-162">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-162">Save the file.</span></span>  
  
11. <span data-ttu-id="3d6da-163">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-163">Save the project.</span></span>  
  
12. <span data-ttu-id="3d6da-164">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="3d6da-165">클래스 라이브러리 .dll 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="3d6da-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="3d6da-166">런타임 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="3d6da-166">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="3d6da-167">동등한 형식의 런타임 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3d6da-167">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="3d6da-168">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3d6da-169">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="3d6da-170">**템플릿** 창에서 **클래스 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="3d6da-171">**이름** 상자에 `TypeEquivalenceRuntime`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="3d6da-172">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-172">The new project is created.</span></span>  
  
3.  <span data-ttu-id="3d6da-173">**솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="3d6da-174">파일 이름을 `SampleClass.vb`으로 바꾸고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="3d6da-175">파일 이름을 바꾸면 클래스 이름도 `SampleClass`로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="3d6da-176">이 클래스는 `ISampleInterface` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-176">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="3d6da-177">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="3d6da-178">**컴파일** 탭을 클릭합니다. TypeEquivalenceInterface 프로젝트에서 사용한 것과 같은 위치로 출력 경로를 설정합니다(예: `C:\TypeEquivalenceSample`).</span><span class="sxs-lookup"><span data-stu-id="3d6da-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="3d6da-179">프로젝트 속성을 편집하는 동안 **서명** 탭을 클릭합니다. **어셈블리 서명** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="3d6da-180">**강력한 이름 키 파일 선택** 목록에서 **<새로 만들기...>**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="3d6da-181">**키 파일 이름** 상자에 `key.snk`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="3d6da-182">**암호로 내 키 파일 보호** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="3d6da-183">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-183">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="3d6da-184">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="3d6da-185">**찾아보기** 탭을 클릭하여 출력 경로 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="3d6da-186">TypeEquivalenceInterface.dll 파일을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="3d6da-187">**프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-187">On the **Project** menu, click **Show All Files**.</span></span>  
  
8.  <span data-ttu-id="3d6da-188">**솔루션 탐색기**를 확장하고 **References** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="3d6da-189">TypeEquivalenceInterface 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="3d6da-190">TypeEquivalenceInterface 참조에 대한 속성 창에서 **특정 버전** 속성을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
9. <span data-ttu-id="3d6da-191">다음 코드를 SampleClass 클래스 파일에 추가하여 SampleClass 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
  
    Public Class SampleClass  
        Implements ISampleInterface  
  
        Private p_UserInput As String  
        Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput  
            Get  
                Return p_UserInput  
            End Get  
        End Property  
  
        Public Sub GetUserInput() Implements ISampleInterface.GetUserInput  
            Console.WriteLine("Please enter a value:")  
            p_UserInput = Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
10. <span data-ttu-id="3d6da-192">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-192">Save the project.</span></span>  
  
11. <span data-ttu-id="3d6da-193">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="3d6da-194">클래스 라이브러리 .dll 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="3d6da-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="3d6da-195">클라이언트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="3d6da-195">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="3d6da-196">동등한 형식의 클라이언트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3d6da-196">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="3d6da-197">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3d6da-198">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="3d6da-199">**템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="3d6da-200">**이름** 상자에 `TypeEquivalenceClient`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="3d6da-201">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-201">The new project is created.</span></span>  
  
3.  <span data-ttu-id="3d6da-202">TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="3d6da-203">**컴파일** 탭을 클릭합니다. TypeEquivalenceInterface 프로젝트에서 사용한 것과 같은 위치로 출력 경로를 설정합니다(예: `C:\TypeEquivalenceSample`).</span><span class="sxs-lookup"><span data-stu-id="3d6da-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="3d6da-204">TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="3d6da-205">**찾아보기** 탭을 클릭하여 출력 경로 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="3d6da-206">TypeEquivalenceInterface.dll 파일(TypeEquivalenceRuntime.dll 아님)을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d6da-207">**프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-207">On the **Project** menu, click **Show All Files**.</span></span>  
  
6.  <span data-ttu-id="3d6da-208">**솔루션 탐색기**를 확장하고 **References** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="3d6da-209">TypeEquivalenceInterface 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="3d6da-210">TypeEquivalenceInterface 참조에 대한 속성 창에서 **Interop 형식 포함** 속성을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
7.  <span data-ttu-id="3d6da-211">클라이언트 프로그램을 만드는 Module1.vb 파일에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-211">Add the following code to the Module1.vb file to create the client program.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
    Imports System.Reflection  
  
    Module Module1  
  
        Sub Main()  
            Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")  
            Dim sampleClass As ISampleInterface = CType( _  
                sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)  
            sampleClass.GetUserInput()  
            Console.WriteLine(sampleClass.UserInput)  
            Console.WriteLine(sampleAssembly.GetName().Version)  
            Console.ReadLine()  
        End Sub  
  
    End Module  
    ```  
  
8.  <span data-ttu-id="3d6da-212">Ctrl+F5를 눌러 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-212">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="3d6da-213">인터페이스 수정</span><span class="sxs-lookup"><span data-stu-id="3d6da-213">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="3d6da-214">인터페이스를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="3d6da-214">To modify the interface</span></span>  
  
1.  <span data-ttu-id="3d6da-215">Visual Studio의 **파일** 메뉴에서 **열기**를 가리킨 다음 **프로젝트/솔루션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="3d6da-216">**프로젝트 열기** 대화 상자에서 TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="3d6da-217">**응용 프로그램** 탭을 클릭합니다. **어셈블리 정보** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="3d6da-218">**어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="3d6da-219">ISampleInterface.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="3d6da-220">ISampleInterface 인터페이스에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-220">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```vb  
    Function GetDate() As Date  
    ```  
  
     <span data-ttu-id="3d6da-221">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-221">Save the file.</span></span>  
  
4.  <span data-ttu-id="3d6da-222">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-222">Save the project.</span></span>  
  
5.  <span data-ttu-id="3d6da-223">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="3d6da-224">클래스 라이브러리 .dll 파일의 새 버전이 컴파일되고 지정한 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="3d6da-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="3d6da-225">런타임 클래스 수정</span><span class="sxs-lookup"><span data-stu-id="3d6da-225">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="3d6da-226">런타임 클래스를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="3d6da-226">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="3d6da-227">Visual Studio의 **파일** 메뉴에서 **열기**를 가리킨 다음 **프로젝트/솔루션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="3d6da-228">**프로젝트 열기** 대화 상자에서 TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="3d6da-229">**응용 프로그램** 탭을 클릭합니다. **어셈블리 정보** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="3d6da-230">**어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="3d6da-231">SampleClass.vbfile를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-231">Open the SampleClass.vbfile.</span></span> <span data-ttu-id="3d6da-232">SampleClass 클래스에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-232">Add the following lines of code to the SampleClass class.</span></span>  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  <span data-ttu-id="3d6da-233">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-233">Save the project.</span></span>  
  
5.  <span data-ttu-id="3d6da-234">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-234">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="3d6da-235">클래스 라이브러리 .dll 파일의 업데이트된 버전이 컴파일되고 앞서 지정한 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="3d6da-235">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="3d6da-236">파일 탐색기에서 출력 경로 폴더를 엽니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="3d6da-236">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="3d6da-237">TypeEquivalenceClient.exe를 두 번 클릭하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-237">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="3d6da-238">다시 컴파일하지 않고도 이 프로그램은 TypeEquivalenceRuntime 어셈블리의 새 버전을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6da-238">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6da-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d6da-239">See Also</span></span>  
 [<span data-ttu-id="3d6da-240">/link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d6da-240">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="3d6da-241">프로그래밍 개념</span><span class="sxs-lookup"><span data-stu-id="3d6da-241">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="3d6da-242">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3d6da-242">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="3d6da-243">어셈블리와 전역 어셈블리 캐시(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d6da-243">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
