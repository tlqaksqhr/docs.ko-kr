---
title: "연습:은 관리 되는 Visual Studio (Visual Basic)에서 어셈블리의 형식 포함 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: adc58e081cd9b874a841d84b11d92cbffb6ba6b8
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="7b349-102">연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="7b349-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="7b349-103">강력한 이름의 관리 되는 어셈블리의 형식 정보를 포함 하는 경우에 버전 독립성을 달성 하기 위해 응용 프로그램의 형식을 느슨하게 결합 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="7b349-104">즉, 각 버전에 대해 다시 컴파일할 필요 없이 관리 되는 라이브러리의 여러 버전 형식을 사용 하 여 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="7b349-105">형식 포함 Microsoft Office에서 자동화 개체를 사용 하는 응용 프로그램과 같은 COM interop에 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="7b349-106">서로 다른 컴퓨터에 다른 버전의 Microsoft Office를 사용 하는 프로그램의 동일한 빌드를 사용 하면 형식 정보 포함.</span><span class="sxs-lookup"><span data-stu-id="7b349-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="7b349-107">그러나 형식 포함 된 완전히 관리 되는 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="7b349-108">다음과 같은 특징이 있는 어셈블리에서 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7b349-109">어셈블리는 하나 이상의 공용 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="7b349-110">포함 된 인터페이스 주석을 지정 하 여 한 `ComImport` 특성 및 `Guid` 특성 (및 고유 GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="7b349-111">어셈블리 주석이 추가 되는 `ImportedFromTypeLib` 특성 또는 `PrimaryInteropAssembly` 특성 및 해당 어셈블리 수준 `Guid` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="7b349-112">(기본적으로 Visual Basic 프로젝트 템플릿에 포함 어셈블리 수준의 `Guid` 특성입니다.)</span><span class="sxs-lookup"><span data-stu-id="7b349-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="7b349-113">포함할 수 있는 공용 인터페이스를 지정한 후에 이러한 인터페이스를 구현 하는 런타임 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="7b349-114">클라이언트 프로그램 수는 공용 인터페이스 및 설정을 포함 하는 어셈블리를 참조 하 여 디자인 타임에 이러한 인터페이스에 대 한 형식 정보를 포함 한 다음는 `Embed Interop Types` 속성에 대 한 참조의 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="7b349-115">이 해당 명령줄 컴파일러를 사용 하 고 사용 하 여 어셈블리를 참조 하는 `/link` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="7b349-116">클라이언트 프로그램에서 이러한 인터페이스로 형식화 된 런타임 개체의 인스턴스를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="7b349-117">강력한 이름의 런타임 어셈블리의 새 버전을 만들면 클라이언트 프로그램 없는 업데이트 된 런타임 어셈블리로 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="7b349-118">대신, 클라이언트 프로그램에서 사용 하는 어떤 버전의 런타임 어셈블리를 사용할 수 있는 공용 인터페이스에 포함된 된 형식 정보를 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="7b349-119">COM interop 어셈블리에서 형식 정보를 포함 하도록 지 원하는 형식 포함의 기본 기능은 이기 때문에 완전히 관리 되는 솔루션에서 형식 정보를 포함 하는 경우 다음과 같은 제한 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="7b349-120">COM interop 관련 특성만 포함 됩니다. 다른 특성은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="7b349-121">제네릭 매개 변수를 사용 하는 형식 및 제네릭 매개 변수의 형식이 포함된 된 형식, 해당 형식의 어셈블리 경계를 넘어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="7b349-122">어셈블리 경계를 넘는 경우의 예로 다른 어셈블리에서 메서드 호출 또는 다른 어셈블리에 정의 된 형식에서 파생 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="7b349-123">상수는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="7b349-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>클래스 키로 포함된 된 형식을 지원 하지 않습니다.</xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7b349-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="7b349-125">사용자 고유의 사전 형식 키로 포함된 된 형식을 지원 하기 위해 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="7b349-126">이 연습에서는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="7b349-127">포함할 수 있는 형식 정보를 포함 하는 공용 인터페이스에 강력한 이름의 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="7b349-128">해당 공용 인터페이스를 구현 하는 런타임 강력한 이름의 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="7b349-129">런타임 어셈블리에서 클래스의 인스턴스를 만들고 공용 인터페이스에서 형식 정보를 포함 하는 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="7b349-130">수정 하 고 런타임 어셈블리를 다시 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b349-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="7b349-131">클라이언트 프로그램을 다시 컴파일할 필요 없이 런타임 어셈블리의 새 버전은 사용 하는지 확인 하기 위해 클라이언트 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="7b349-132">인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="7b349-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="7b349-133">형식 동등성 인터페이스 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7b349-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="7b349-134">Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7b349-135">**새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="7b349-136">선택 **클래스 라이브러리** 에 **템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="7b349-137">에 **이름** 상자에 입력 합니다 `TypeEquivalenceInterface`를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="7b349-138">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="7b349-139">**솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="7b349-140">파일을 이름 `ISampleInterface.vb` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="7b349-141">클래스 이름도 바꿉니다 파일의 이름을 바꾸면 `ISampleInterface`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="7b349-142">이 클래스는 클래스에 대 한 공용 인터페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="7b349-143">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="7b349-144">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-144">Click the **Compile** tab.</span></span> <span data-ttu-id="7b349-145">와 같은 개발 컴퓨터에 올바른 위치에 출력 경로 설정 `C:\TypeEquivalenceSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="7b349-146">이 위치는이 연습에서 나중에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="7b349-147">프로젝트 속성을 계속 편집 하는 동안 클릭는 **서명** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="7b349-148">선택 된 **어셈블리에 서명** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="7b349-149">에 **강력한 이름 키 파일 선택** 목록에서 클릭 ** <New...> **.</New...></span><span class="sxs-lookup"><span data-stu-id="7b349-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="7b349-150">에 **키 파일 이름** 상자에 입력 합니다 `key.snk`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="7b349-151">지우기는 **암호로 내 키 파일 보호** 확인란입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="7b349-152">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="7b349-153">ISampleInterface.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-153">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="7b349-154">ISampleInterface 인터페이스를 만드는 ISampleInterface 클래스 파일에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
<span data-ttu-id="7b349-155"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7b349-155"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
7.  <span data-ttu-id="7b349-156">에 **도구** 메뉴를 클릭 하 여 **Guid 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-156">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="7b349-157">에 **GUID 만들기** 대화 상자를 클릭 **레지스트리 형식** 클릭 하 고 **복사**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-157">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="7b349-158">**끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-158">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="7b349-159">에 `Guid` 특성, 샘플 GUID를 삭제 하 고,에서 복사한 GUID에 붙여는 **GUID 만들기** 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-159">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="7b349-160">복사 된 GUID에서 중괄호 ({})를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-160">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="7b349-161">에 **프로젝트** 메뉴를 클릭 하 여 **모든 파일 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-161">On the **Project** menu, click **Show All Files**.</span></span>  
  
10. <span data-ttu-id="7b349-162">**솔루션 탐색기**를 확장 하 고는 **My Project** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-162">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="7b349-163">AssemblyInfo.vb를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-163">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="7b349-164">파일에 다음 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-164">Add the following attribute to the file.</span></span>  
  
<span data-ttu-id="7b349-165"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7b349-165"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="7b349-166">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-166">Save the file.</span></span>  
  
11. <span data-ttu-id="7b349-167">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-167">Save the project.</span></span>  
  
12. <span data-ttu-id="7b349-168">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-168">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="7b349-169">클래스 라이브러리.dll 파일 컴파일되고 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-169">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="7b349-170">런타임 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="7b349-170">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="7b349-171">형식 동등성 런타임 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7b349-171">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="7b349-172">Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-172">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7b349-173">**새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-173">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="7b349-174">선택 **클래스 라이브러리** 에 **템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-174">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="7b349-175">에 **이름** 상자에 입력 합니다 `TypeEquivalenceRuntime`를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-175">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="7b349-176">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-176">The new project is created.</span></span>  
  
3.  <span data-ttu-id="7b349-177">**솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-177">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="7b349-178">파일을 이름 `SampleClass.vb` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-178">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="7b349-179">클래스의 이름을 파일의 이름을 바꾸면 `SampleClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-179">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="7b349-180">이 클래스가 구현 하는 `ISampleInterface` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-180">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="7b349-181">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-181">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="7b349-182">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-182">Click the **Compile** tab.</span></span> <span data-ttu-id="7b349-183">예를 들어 TypeEquivalenceInterface 프로젝트에서 사용한 동일한 위치에 출력 경로 설정 `C:\TypeEquivalenceSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-183">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="7b349-184">프로젝트 속성을 계속 편집 하는 동안 클릭는 **서명** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-184">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="7b349-185">선택 된 **어셈블리에 서명** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-185">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="7b349-186">에 **강력한 이름 키 파일 선택** 목록에서 클릭 ** <New...> **.</New...></span><span class="sxs-lookup"><span data-stu-id="7b349-186">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="7b349-187">에 **키 파일 이름** 상자에 입력 합니다 `key.snk`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-187">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="7b349-188">지우기는 **암호로 내 키 파일 보호** 확인란입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-188">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="7b349-189">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-189">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="7b349-190">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-190">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="7b349-191">클릭 하 고 **찾아보기** 탭 및 출력 경로 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-191">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="7b349-192">TypeEquivalenceInterface.dll 파일을 선택 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-192">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="7b349-193">에 **프로젝트** 메뉴를 클릭 하 여 **모든 파일 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-193">On the **Project** menu, click **Show All Files**.</span></span>  
  
8.  <span data-ttu-id="7b349-194">**솔루션 탐색기**를 확장 하 고는 **참조** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-194">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="7b349-195">TypeEquivalenceInterface 파일에 대 한 참조를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-195">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="7b349-196">TypeEquivalenceInterface 참조에 대 한 속성 창에서 설정 된 **특정 버전** 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-196">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
9. <span data-ttu-id="7b349-197">SampleClass 클래스를 만드는 SampleClass 클래스 파일에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-197">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
<span data-ttu-id="7b349-198"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7b349-198"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
10. <span data-ttu-id="7b349-199">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-199">Save the project.</span></span>  
  
11. <span data-ttu-id="7b349-200">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-200">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="7b349-201">클래스 라이브러리.dll 파일 컴파일되고 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-201">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="7b349-202">클라이언트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7b349-202">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="7b349-203">형식 동등성 클라이언트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7b349-203">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="7b349-204">Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-204">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7b349-205">**새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-205">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="7b349-206">선택 **콘솔 응용 프로그램** 에 **템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-206">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="7b349-207">에 **이름** 상자에 입력 합니다 `TypeEquivalenceClient`를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-207">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="7b349-208">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-208">The new project is created.</span></span>  
  
3.  <span data-ttu-id="7b349-209">TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-209">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="7b349-210">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-210">Click the **Compile** tab.</span></span> <span data-ttu-id="7b349-211">예를 들어 TypeEquivalenceInterface 프로젝트에서 사용한 동일한 위치에 출력 경로 설정 `C:\TypeEquivalenceSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-211">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="7b349-212">TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-212">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="7b349-213">클릭 하 고 **찾아보기** 탭 및 출력 경로 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-213">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="7b349-214">TypeEquivalenceInterface.dll 파일 (TypeEquivalenceRuntime.dll 하지)를 선택 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-214">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="7b349-215">에 **프로젝트** 메뉴를 클릭 하 여 **모든 파일 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-215">On the **Project** menu, click **Show All Files**.</span></span>  
  
6.  <span data-ttu-id="7b349-216">**솔루션 탐색기**를 확장 하 고는 **참조** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-216">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="7b349-217">TypeEquivalenceInterface 파일에 대 한 참조를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-217">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="7b349-218">TypeEquivalenceInterface 참조에 대 한 속성 창에서 설정 된 **Interop 형식 포함** 속성을 **True**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-218">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
7.  <span data-ttu-id="7b349-219">클라이언트 프로그램을 만드는 Module1.vb 파일에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-219">Add the following code to the Module1.vb file to create the client program.</span></span>  
  
<span data-ttu-id="7b349-220"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7b349-220"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
8.  <span data-ttu-id="7b349-221">빌드하고 프로그램을 실행 하려면 CTRL + f&5;를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-221">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="7b349-222">인터페이스 수정</span><span class="sxs-lookup"><span data-stu-id="7b349-222">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="7b349-223">인터페이스를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="7b349-223">To modify the interface</span></span>  
  
1.  <span data-ttu-id="7b349-224">Visual Studio에서에 **파일** 메뉴에서 **열려**를 클릭 하 고 **프로젝트/솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-224">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="7b349-225">에 **프로젝트 열기** 대화 상자 TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-225">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="7b349-226">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-226">Click the **Application** tab.</span></span> <span data-ttu-id="7b349-227">클릭 하 고 **어셈블리 정보** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-227">Click the **Assembly Information** button.</span></span> <span data-ttu-id="7b349-228">변경 된 **어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-228">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="7b349-229">ISampleInterface.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-229">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="7b349-230">ISampleInterface 인터페이스에 다음 코드 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-230">Add the following line of code to the ISampleInterface interface.</span></span>  
  
<span data-ttu-id="7b349-231"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7b349-231"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="7b349-232">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-232">Save the file.</span></span>  
  
4.  <span data-ttu-id="7b349-233">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-233">Save the project.</span></span>  
  
5.  <span data-ttu-id="7b349-234">TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-234">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="7b349-235">클래스 라이브러리.dll 파일의 새 버전 컴파일되고 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-235">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="7b349-236">런타임 클래스 수정</span><span class="sxs-lookup"><span data-stu-id="7b349-236">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="7b349-237">런타임 클래스를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="7b349-237">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="7b349-238">Visual Studio에서에 **파일** 메뉴에서 **열려**를 클릭 하 고 **프로젝트/솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-238">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="7b349-239">에 **프로젝트 열기** 대화 상자 TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-239">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="7b349-240">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-240">Click the **Application** tab.</span></span> <span data-ttu-id="7b349-241">클릭 하 고 **어셈블리 정보** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-241">Click the **Assembly Information** button.</span></span> <span data-ttu-id="7b349-242">변경 된 **어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-242">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="7b349-243">SampleClass.vbfile를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-243">Open the SampleClass.vbfile.</span></span> <span data-ttu-id="7b349-244">SampleClass 클래스에 다음 코드 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-244">Add the following lines of code to the SampleClass class.</span></span>  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  <span data-ttu-id="7b349-245">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-245">Save the project.</span></span>  
  
5.  <span data-ttu-id="7b349-246">TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-246">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="7b349-247">클래스 라이브러리.dll 파일의 업데이트 된 버전 컴파일되고 이전에 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-247">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="7b349-248">파일 탐색기에서 출력 경로 폴더 (예를 들어 C:\TypeEquivalenceSample)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-248">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="7b349-249">프로그램을 실행 하려면 TypeEquivalenceClient.exe를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-249">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="7b349-250">프로그램은 다시 컴파일되지 않았이 필요 없이 TypeEquivalenceRuntime 어셈블리의 새 버전을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b349-250">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b349-251">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b349-251">See Also</span></span>  
 <span data-ttu-id="7b349-252">[/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md) </span><span class="sxs-lookup"><span data-stu-id="7b349-252">[/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md) </span></span>  
<span data-ttu-id="7b349-253"> [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b349-253"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="7b349-254"> [어셈블리를 사용한 프로그래밍](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6) </span><span class="sxs-lookup"><span data-stu-id="7b349-254"> [Programming with Assemblies](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6) </span></span>  
<span data-ttu-id="7b349-255"> [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="7b349-255"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>

