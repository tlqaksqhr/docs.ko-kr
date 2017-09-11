---
title: "방법: XML 문서 기능 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="91ade-102">방법: XML 문서 기능 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="91ade-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="91ade-103">다음 샘플은 문서화된 형식에 대한 기본 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91ade-104">예제</span><span class="sxs-lookup"><span data-stu-id="91ade-104">Example</span></span>  
 <span data-ttu-id="91ade-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="91ade-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span></span>  
  
 <span data-ttu-id="91ade-106">**// This .xml file was generated with the previous code sample.**</span><span class="sxs-lookup"><span data-stu-id="91ade-106">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="91ade-107">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="91ade-107">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="91ade-108">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="91ade-108">**\<doc>**</span></span>  
 <span data-ttu-id="91ade-109">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="91ade-109">**\<assembly>**</span></span>  
 <span data-ttu-id="91ade-110">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="91ade-110">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="91ade-111">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="91ade-111">**\</assembly>**</span></span>  
 <span data-ttu-id="91ade-112">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="91ade-112">**\<members>**</span></span>  
 <span data-ttu-id="91ade-113">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="91ade-113">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="91ade-114">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-114">**\<summary>**</span></span>  
 <span data-ttu-id="91ade-115">**Class level summary documentation goes here.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-115">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="91ade-116">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="91ade-116">**\<remarks>**</span></span>  
 <span data-ttu-id="91ade-117">**Longer comments can be associated with a type or member** </span><span class="sxs-lookup"><span data-stu-id="91ade-117">**Longer comments can be associated with a type or member** </span></span>  
 <span data-ttu-id="91ade-118">**through the remarks tag\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="91ade-118">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="91ade-119">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-119">**\</member>**</span></span>  
 <span data-ttu-id="91ade-120">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="91ade-120">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="91ade-121">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-121">**\<summary>**</span></span>  
 <span data-ttu-id="91ade-122">**Store for the name property\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-122">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="91ade-123">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-123">**\</member>**</span></span>  
 <span data-ttu-id="91ade-124">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="91ade-124">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="91ade-125">**\<summary>The class constructor.\</summary>** </span><span class="sxs-lookup"><span data-stu-id="91ade-125">**\<summary>The class constructor.\</summary>** </span></span>  
 <span data-ttu-id="91ade-126">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-126">**\</member>**</span></span>  
 <span data-ttu-id="91ade-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="91ade-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="91ade-128">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-128">**\<summary>**</span></span>  
 <span data-ttu-id="91ade-129">**Description for SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-129">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="91ade-130">**\<param name="s"> Parameter description for s goes here\</param>**</span><span class="sxs-lookup"><span data-stu-id="91ade-130">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="91ade-131">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="91ade-131">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="91ade-132">**You can use the cref attribute on any tag to reference a type or member** </span><span class="sxs-lookup"><span data-stu-id="91ade-132">**You can use the cref attribute on any tag to reference a type or member** </span></span>  
 <span data-ttu-id="91ade-133">**and the compiler will check that the reference exists. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="91ade-133">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="91ade-134">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-134">**\</member>**</span></span>  
 <span data-ttu-id="91ade-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="91ade-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="91ade-136">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-136">**\<summary>**</span></span>  
 <span data-ttu-id="91ade-137">**Some other method. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-137">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="91ade-138">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="91ade-138">**\<returns>**</span></span>  
 <span data-ttu-id="91ade-139">**Return results are described through the returns tag.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="91ade-139">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="91ade-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="91ade-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="91ade-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="91ade-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="91ade-142">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-142">**\</member>**</span></span>  
 <span data-ttu-id="91ade-143">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="91ade-143">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="91ade-144">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-144">**\<summary>**</span></span>  
 <span data-ttu-id="91ade-145">**The entry point for the application.**</span><span class="sxs-lookup"><span data-stu-id="91ade-145">**The entry point for the application.**</span></span>  
 <span data-ttu-id="91ade-146">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-146">**\</summary>**</span></span>  
 <span data-ttu-id="91ade-147">**\<param name="args"> A list of command line arguments\</param>**</span><span class="sxs-lookup"><span data-stu-id="91ade-147">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="91ade-148">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-148">**\</member>**</span></span>  
 <span data-ttu-id="91ade-149">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="91ade-149">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="91ade-150">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-150">**\<summary>**</span></span>  
 <span data-ttu-id="91ade-151">**Name property \</summary>**</span><span class="sxs-lookup"><span data-stu-id="91ade-151">**Name property \</summary>**</span></span>  
 <span data-ttu-id="91ade-152">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="91ade-152">**\<value>**</span></span>  
 <span data-ttu-id="91ade-153">**A value tag is used to describe the property value\</value>**</span><span class="sxs-lookup"><span data-stu-id="91ade-153">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="91ade-154">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91ade-154">**\</member>**</span></span>  
 <span data-ttu-id="91ade-155">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="91ade-155">**\</members>**</span></span>  
<span data-ttu-id="91ade-156">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="91ade-156">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="91ade-157">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="91ade-157">Compiling the Code</span></span>  
 <span data-ttu-id="91ade-158">예제를 컴파일하려면 다음 명령줄을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-158">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="91ade-159">이렇게 하면 TYPE 명령을 사용하거나 브라우저에서 볼 수 있는 XML 파일 XMLsample.xml이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-159">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="91ade-160">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="91ade-160">Robust Programming</span></span>  
 <span data-ttu-id="91ade-161">XML 문서는 ///로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-161">XML documentation starts with ///.</span></span> <span data-ttu-id="91ade-162">새 프로젝트를 만드는 경우 마법사에서 몇 개의 시작 /// 줄을 자동으로 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-162">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="91ade-163">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-163">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="91ade-164">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-164">The documentation must be well-formed XML.</span></span> <span data-ttu-id="91ade-165">XML이 잘 구성되지 않은 경우 경고가 생성되고, 문서 파일에 오류가 발생했다는 주석이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-165">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="91ade-166">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-166">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="91ade-167">권장 태그 집합이 있습니다(추가 정보 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="91ade-167">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="91ade-168">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-168">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="91ade-169">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-169">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="91ade-170">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-170">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="91ade-171">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-171">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="91ade-172">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-172">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="91ade-173">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-173">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="91ade-174">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-174">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="91ade-175">컴파일러는 `cref` 특성에 설명된 형식을 찾을 때 모든 `using` 문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-175">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="91ade-176">\<summary> 태그는 Visual Studio 내의 IntelliSense에서 형식 또는 멤버에 대한 추가 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-176">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="91ade-177">XML 파일은 형식 및 멤버에 대한 전체 정보를 제공하지 않습니다(예: 형식 정보가 포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="91ade-177">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="91ade-178">형식 또는 멤버에 대한 전체 정보를 가져오려면 실제 형식 또는 멤버에 대한 리플렉션과 함께 문서 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91ade-178">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ade-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91ade-179">See Also</span></span>  
 <span data-ttu-id="91ade-180">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="91ade-180">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="91ade-181">[/doc(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="91ade-181">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="91ade-182">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="91ade-182">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

