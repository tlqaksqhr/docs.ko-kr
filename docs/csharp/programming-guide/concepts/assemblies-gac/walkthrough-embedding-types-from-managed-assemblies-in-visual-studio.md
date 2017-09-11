---
title: "연습: Visual Studio에서 관리되는 어셈블리의 형식 포함(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7b003e76229a06883adc22f933f08663330f0c9d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="1df2a-102">연습: Visual Studio에서 관리되는 어셈블리의 형식 포함(C#)</span><span class="sxs-lookup"><span data-stu-id="1df2a-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="1df2a-103">강력한 이름의 관리되는 어셈블리에서 형식 정보를 포함하는 경우 응용 프로그램에서 유형을 느슨하게 연결하여 버전 독립성을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="1df2a-104">즉, 각 버전에 대해 컴파일하지 않고도 관리되는 라이브러리의 여러 버전에서 형식을 사용하도록 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="1df2a-105">형식 포함은 Microsoft Office의 자동화 개체를 사용하는 응용 프로그램과 같은 COM interop에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="1df2a-106">형식 정보를 포함하면 서로 다른 컴퓨터의 서로 다른 Microsoft Office 버전에서 동일한 빌드의 프로그램을 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="1df2a-107">그러나 완전하게 관리되는 솔루션에서도 형식 포함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="1df2a-108">다음과 같은 특징이 있는 어셈블리에서 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="1df2a-109">어셈블리는 하나 이상의 공용 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="1df2a-110">포함된 인터페이스는 `ComImport` 특성 및 `Guid` 특성(그리고 고유한 GUID)으로 주석이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="1df2a-111">어셈블리는 `ImportedFromTypeLib` 특성이나 `PrimaryInteropAssembly` 특성, 그리고 어셈블리 수준의 `Guid` 특성으로 주석이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="1df2a-112">기본적으로 Visual C# 프로젝트 템플릿에는 어셈블리 수준의 `Guid` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="1df2a-113">포함할 수 있는 공용 인터페이스를 지정한 후에 이러한 인터페이스를 구현하는 런타임 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="1df2a-114">그런 다음 클라이언트 프로그램은 공용 인터페이스가 포함된 어셈블리를 참조하고 참조의 `Embed Interop Types` 속성을 `True`로 설정하여 디자인 타임에 해당 인터페이스의 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="1df2a-115">이는 명령줄 컴파일러를 사용하고 `/link` 컴파일러 옵션을 사용하여 어셈블리를 참조하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="1df2a-116">그러면 클라이언트 프로그램은 해당 인터페이스로 형식이 지정된 런타임 개체의 인스턴스를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="1df2a-117">강력한 이름의 런타임 어셈블리의 새 버전을 만들면 업데이트된 런타임 어셈블리로 클라이언트 프로그램을 다시 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="1df2a-118">대신, 클라이언트 프로그램은 공용 인터페이스에 대해 포함된 형식 정보를 통해 사용 가능한 런타임 어셈블리 버전을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="1df2a-119">형식 포함의 기본 기능은 COM interop 어셈블리에서 형식 정보를 포함하도록 지원하는 것이므로, 완전히 관리되는 솔루션에 형식 정보를 포함할 때 다음과 같은 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="1df2a-120">COM interop 관련 특성만 포함되고 다른 특성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="1df2a-121">형식이 제네릭 매개 변수를 사용하고 제네릭 매개 변수의 형식이 포함된 형식인 경우 해당 형식을 어셈블리 경계에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="1df2a-122">어셈블리 경계를 넘어가는 예로는 다른 어셈블리에서 메서드를 호출하는 경우 또는 다른 어셈블리에 정의된 형식에서 형식이 파생되는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="1df2a-123">상수는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="1df2a-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 클래스는 포함된 형식을 키로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="1df2a-125">포함된 형식을 키로서 지원하도록 고유한 사전 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="1df2a-126">이 연습에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="1df2a-127">포함할 수 있는 형식 정보가 있는 공개 인터페이스와 함께 강력한 이름의 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="1df2a-128">해당 공용 인터페이스를 구현하는 강력한 이름의 런타임 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="1df2a-129">공용 인터페이스에서 형식 정보를 포함하고 런타임 어셈블리에서 클래스의 인스턴스를 만드는 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="1df2a-130">런타임 어셈블리를 수정하고 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="1df2a-131">클라이언트 프로그램을 실행하여, 클라이언트 프로그램을 다시 컴파일할 필요 없이 런타임 어셈블리의 새 버전이 사용되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="1df2a-132">인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="1df2a-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="1df2a-133">동등한 형식의 인터페이스 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1df2a-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="1df2a-134">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1df2a-135">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1df2a-136">**템플릿** 창에서 **클래스 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="1df2a-137">**이름** 상자에 `TypeEquivalenceInterface`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="1df2a-138">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="1df2a-139">**솔루션 탐색기**에서 Class1.cs 파일을 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="1df2a-140">파일 이름을 `ISampleInterface.cs`로 바꾸고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="1df2a-141">파일 이름을 바꾸면 클래스 이름도 `ISampleInterface`로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="1df2a-142">이 클래스는 클래스에 대한 공용 인터페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="1df2a-143">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="1df2a-144">**빌드** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-144">Click the the **Build** tab.</span></span> <span data-ttu-id="1df2a-145">개발 컴퓨터의 유효한 위치(예: `C:\TypeEquivalenceSample`)로 출력 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="1df2a-146">이 연습의 이후 단계에서도 이 위치가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="1df2a-147">프로젝트 속성을 편집하는 동안 **서명** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="1df2a-148">**어셈블리 서명** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="1df2a-149">**강력한 이름 키 파일 선택** 목록에서 **<새로 만들기...>**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="1df2a-150">**키 파일 이름** 상자에 `key.snk`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="1df2a-151">**암호로 내 키 파일 보호** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="1df2a-152">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="1df2a-153">ISampleInterface.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-153">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="1df2a-154">ISampleInterface 인터페이스를 만드는 ISampleInterface 클래스 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="1df2a-155">**도구** 메뉴에서 **GUID 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-155">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="1df2a-156">**GUID 만들기** 대화 상자에서 **레지스트리 형식**과 **복사**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-156">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="1df2a-157">**끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-157">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="1df2a-158">`Guid` 특성에서 샘플 GUID를 삭제하고, **GUID 만들기** 대화 상자에서 복사한 GUID를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-158">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="1df2a-159">복사된 GUID에서 중괄호({})를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-159">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="1df2a-160">**솔루션 탐색기**에서 **Properties** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-160">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="1df2a-161">AssemblyInfo.cs 파일을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-161">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="1df2a-162">파일에 다음 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-162">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="1df2a-163">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-163">Save the file.</span></span>  
  
10. <span data-ttu-id="1df2a-164">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-164">Save the project.</span></span>  
  
11. <span data-ttu-id="1df2a-165">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-165">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="1df2a-166">클래스 라이브러리 .dll 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1df2a-166">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="1df2a-167">런타임 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="1df2a-167">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="1df2a-168">동등한 형식의 런타임 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1df2a-168">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="1df2a-169">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-169">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1df2a-170">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-170">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1df2a-171">**템플릿** 창에서 **클래스 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-171">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="1df2a-172">**이름** 상자에 `TypeEquivalenceRuntime`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-172">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="1df2a-173">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-173">The new project is created.</span></span>  
  
3.  <span data-ttu-id="1df2a-174">**솔루션 탐색기**에서 Class1.cs 파일을 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-174">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="1df2a-175">파일 이름을 `SampleClass.cs`로 바꾸고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-175">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="1df2a-176">파일 이름을 바꾸면 클래스 이름도 `SampleClass`로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-176">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="1df2a-177">이 클래스는 `ISampleInterface` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-177">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="1df2a-178">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-178">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="1df2a-179">**빌드** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-179">Click the **Build** tab.</span></span> <span data-ttu-id="1df2a-180">TypeEquivalenceInterface 프로젝트에서 사용한 것과 같은 위치로 출력 경로를 설정합니다(예: `C:\TypeEquivalenceSample`).</span><span class="sxs-lookup"><span data-stu-id="1df2a-180">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="1df2a-181">프로젝트 속성을 편집하는 동안 **서명** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-181">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="1df2a-182">**어셈블리 서명** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-182">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="1df2a-183">**강력한 이름 키 파일 선택** 목록에서 **<새로 만들기...>**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-183">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="1df2a-184">**키 파일 이름** 상자에 `key.snk`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-184">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="1df2a-185">**암호로 내 키 파일 보호** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-185">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="1df2a-186">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-186">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="1df2a-187">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-187">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="1df2a-188">**찾아보기** 탭을 클릭하여 출력 경로 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-188">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="1df2a-189">TypeEquivalenceInterface.dll 파일을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-189">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="1df2a-190">**솔루션 탐색기**를 확장하고 **References** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-190">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="1df2a-191">TypeEquivalenceInterface 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-191">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="1df2a-192">TypeEquivalenceInterface 참조에 대한 속성 창에서 **특정 버전** 속성을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-192">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="1df2a-193">다음 코드를 SampleClass 클래스 파일에 추가하여 SampleClass 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-193">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. <span data-ttu-id="1df2a-194">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-194">Save the project.</span></span>  
  
10. <span data-ttu-id="1df2a-195">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-195">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="1df2a-196">클래스 라이브러리 .dll 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1df2a-196">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="1df2a-197">클라이언트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="1df2a-197">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="1df2a-198">동등한 형식의 클라이언트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1df2a-198">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="1df2a-199">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-199">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1df2a-200">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-200">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1df2a-201">**템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-201">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="1df2a-202">**이름** 상자에 `TypeEquivalenceClient`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-202">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="1df2a-203">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-203">The new project is created.</span></span>  
  
3.  <span data-ttu-id="1df2a-204">TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-204">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="1df2a-205">**빌드** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-205">Click the **Build** tab.</span></span> <span data-ttu-id="1df2a-206">TypeEquivalenceInterface 프로젝트에서 사용한 것과 같은 위치로 출력 경로를 설정합니다(예: `C:\TypeEquivalenceSample`).</span><span class="sxs-lookup"><span data-stu-id="1df2a-206">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="1df2a-207">TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-207">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="1df2a-208">**찾아보기** 탭을 클릭하여 출력 경로 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-208">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="1df2a-209">TypeEquivalenceInterface.dll 파일(TypeEquivalenceRuntime.dll 아님)을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-209">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="1df2a-210">**솔루션 탐색기**를 확장하고 **References** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-210">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="1df2a-211">TypeEquivalenceInterface 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-211">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="1df2a-212">TypeEquivalenceInterface 참조에 대한 속성 창에서 **Interop 형식 포함** 속성을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-212">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="1df2a-213">다음 코드를 Program.cs 파일에 추가하여 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-213">Add the following code to the Program.cs file to create the client program.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="1df2a-214">Ctrl+F5를 눌러 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-214">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="1df2a-215">인터페이스 수정</span><span class="sxs-lookup"><span data-stu-id="1df2a-215">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="1df2a-216">인터페이스를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="1df2a-216">To modify the interface</span></span>  
  
1.  <span data-ttu-id="1df2a-217">Visual Studio의 **파일** 메뉴에서 **열기**를 가리킨 다음 **프로젝트/솔루션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-217">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="1df2a-218">**프로젝트 열기** 대화 상자에서 TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-218">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="1df2a-219">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-219">Click the **Application** tab.</span></span> <span data-ttu-id="1df2a-220">**어셈블리 정보** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-220">Click the **Assembly Information** button.</span></span> <span data-ttu-id="1df2a-221">**어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-221">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="1df2a-222">SampleInterface.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-222">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="1df2a-223">ISampleInterface 인터페이스에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-223">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="1df2a-224">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-224">Save the file.</span></span>  
  
4.  <span data-ttu-id="1df2a-225">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-225">Save the project.</span></span>  
  
5.  <span data-ttu-id="1df2a-226">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-226">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="1df2a-227">클래스 라이브러리 .dll 파일의 새 버전이 컴파일되고 지정한 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1df2a-227">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="1df2a-228">런타임 클래스 수정</span><span class="sxs-lookup"><span data-stu-id="1df2a-228">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="1df2a-229">런타임 클래스를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="1df2a-229">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="1df2a-230">Visual Studio의 **파일** 메뉴에서 **열기**를 가리킨 다음 **프로젝트/솔루션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-230">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="1df2a-231">**프로젝트 열기** 대화 상자에서 TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-231">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="1df2a-232">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-232">Click the **Application** tab.</span></span> <span data-ttu-id="1df2a-233">**어셈블리 정보** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-233">Click the **Assembly Information** button.</span></span> <span data-ttu-id="1df2a-234">**어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-234">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="1df2a-235">SampleClass.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-235">Open the SampleClass.cs file.</span></span> <span data-ttu-id="1df2a-236">SampleClass 클래스에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-236">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="1df2a-237">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-237">Save the file.</span></span>  
  
4.  <span data-ttu-id="1df2a-238">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-238">Save the project.</span></span>  
  
5.  <span data-ttu-id="1df2a-239">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-239">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="1df2a-240">클래스 라이브러리 .dll 파일의 업데이트된 버전이 컴파일되고 앞서 지정한 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1df2a-240">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="1df2a-241">파일 탐색기에서 출력 경로 폴더를 엽니다(예: C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1df2a-241">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="1df2a-242">TypeEquivalenceClient.exe를 두 번 클릭하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-242">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="1df2a-243">다시 컴파일하지 않고도 이 프로그램은 TypeEquivalenceRuntime 어셈블리의 새 버전을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="1df2a-243">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df2a-244">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1df2a-244">See Also</span></span>  
 <span data-ttu-id="1df2a-245">[/link(C# 컴파일러 옵션)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="1df2a-245">[/link (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span></span>  
 <span data-ttu-id="1df2a-246">[C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1df2a-246">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1df2a-247">[어셈블리를 사용한 프로그래밍](../../../../framework/app-domains/programming-with-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="1df2a-247">[Programming with Assemblies](../../../../framework/app-domains/programming-with-assemblies.md) </span></span>  
 [<span data-ttu-id="1df2a-248">어셈블리 및 전역 어셈블리 캐시(C#)</span><span class="sxs-lookup"><span data-stu-id="1df2a-248">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

