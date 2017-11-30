---
title: "방법: XML 문서 기능 사용(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb647a275a5cd5fac2316706591440d9792861b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="04276-102">방법: XML 문서 기능 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="04276-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="04276-103">다음 샘플은 문서화된 형식에 대한 기본 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04276-104">예제</span><span class="sxs-lookup"><span data-stu-id="04276-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 <span data-ttu-id="04276-105">**// This .xml file was generated with the previous code sample.**</span><span class="sxs-lookup"><span data-stu-id="04276-105">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="04276-106">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="04276-106">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="04276-107">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="04276-107">**\<doc>**</span></span>  
 <span data-ttu-id="04276-108">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="04276-108">**\<assembly>**</span></span>  
 <span data-ttu-id="04276-109">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="04276-109">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="04276-110">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="04276-110">**\</assembly>**</span></span>  
 <span data-ttu-id="04276-111">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="04276-111">**\<members>**</span></span>  
 <span data-ttu-id="04276-112">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="04276-112">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="04276-113">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-113">**\<summary>**</span></span>  
 <span data-ttu-id="04276-114">**Class level summary documentation goes here.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-114">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="04276-115">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="04276-115">**\<remarks>**</span></span>  
 <span data-ttu-id="04276-116">**긴 설명은 형식 또는 멤버와 연결 가능**</span><span class="sxs-lookup"><span data-stu-id="04276-116">**Longer comments can be associated with a type or member**</span></span>  
 <span data-ttu-id="04276-117">**through the remarks tag\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="04276-117">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="04276-118">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-118">**\</member>**</span></span>  
 <span data-ttu-id="04276-119">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="04276-119">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="04276-120">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-120">**\<summary>**</span></span>  
 <span data-ttu-id="04276-121">**Store for the name property\</summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-121">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="04276-122">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-122">**\</member>**</span></span>  
 <span data-ttu-id="04276-123">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="04276-123">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="04276-124">**\<요약 > 클래스 생성자입니다. \<요약/>**</span><span class="sxs-lookup"><span data-stu-id="04276-124">**\<summary>The class constructor.\</summary>**</span></span>  
 <span data-ttu-id="04276-125">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-125">**\</member>**</span></span>  
 <span data-ttu-id="04276-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="04276-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="04276-127">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-127">**\<summary>**</span></span>  
 <span data-ttu-id="04276-128">**Description for SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-128">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="04276-129">**\<param name="s"> Parameter description for s goes here\</param>**</span><span class="sxs-lookup"><span data-stu-id="04276-129">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="04276-130">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="04276-130">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="04276-131">**태그 cref 특성을 사용 하 여 형식 또는 멤버를 참조할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="04276-131">**You can use the cref attribute on any tag to reference a type or member**</span></span>  
 <span data-ttu-id="04276-132">**and the compiler will check that the reference exists. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="04276-132">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="04276-133">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-133">**\</member>**</span></span>  
 <span data-ttu-id="04276-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="04276-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="04276-135">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-135">**\<summary>**</span></span>  
 <span data-ttu-id="04276-136">**Some other method. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-136">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="04276-137">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="04276-137">**\<returns>**</span></span>  
 <span data-ttu-id="04276-138">**Return results are described through the returns tag.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="04276-138">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="04276-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="04276-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="04276-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="04276-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="04276-141">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-141">**\</member>**</span></span>  
 <span data-ttu-id="04276-142">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="04276-142">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="04276-143">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-143">**\<summary>**</span></span>  
 <span data-ttu-id="04276-144">**The entry point for the application.**</span><span class="sxs-lookup"><span data-stu-id="04276-144">**The entry point for the application.**</span></span>  
 <span data-ttu-id="04276-145">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-145">**\</summary>**</span></span>  
 <span data-ttu-id="04276-146">**\<param name="args"> A list of command line arguments\</param>**</span><span class="sxs-lookup"><span data-stu-id="04276-146">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="04276-147">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-147">**\</member>**</span></span>  
 <span data-ttu-id="04276-148">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="04276-148">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="04276-149">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-149">**\<summary>**</span></span>  
 <span data-ttu-id="04276-150">**Name property \</summary>**</span><span class="sxs-lookup"><span data-stu-id="04276-150">**Name property \</summary>**</span></span>  
 <span data-ttu-id="04276-151">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="04276-151">**\<value>**</span></span>  
 <span data-ttu-id="04276-152">**A value tag is used to describe the property value\</value>**</span><span class="sxs-lookup"><span data-stu-id="04276-152">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="04276-153">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="04276-153">**\</member>**</span></span>  
 <span data-ttu-id="04276-154">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="04276-154">**\</members>**</span></span>  
<span data-ttu-id="04276-155">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="04276-155">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="04276-156">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="04276-156">Compiling the Code</span></span>  
 <span data-ttu-id="04276-157">예제를 컴파일하려면 다음 명령줄을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-157">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="04276-158">이렇게 하면 TYPE 명령을 사용하거나 브라우저에서 볼 수 있는 XML 파일 XMLsample.xml이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="04276-158">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="04276-159">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="04276-159">Robust Programming</span></span>  
 <span data-ttu-id="04276-160">XML 문서는 ///로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-160">XML documentation starts with ///.</span></span> <span data-ttu-id="04276-161">새 프로젝트를 만드는 경우 마법사에서 몇 개의 시작 /// 줄을 자동으로 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="04276-161">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="04276-162">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04276-162">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="04276-163">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-163">The documentation must be well-formed XML.</span></span> <span data-ttu-id="04276-164">XML이 잘 구성되지 않은 경우 경고가 생성되고, 문서 파일에 오류가 발생했다는 주석이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="04276-164">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="04276-165">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04276-165">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="04276-166">권장 태그 집합이 있습니다(추가 정보 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="04276-166">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="04276-167">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04276-167">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="04276-168">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04276-168">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="04276-169">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-169">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="04276-170">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-170">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="04276-171">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04276-171">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="04276-172">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-172">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="04276-173">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-173">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="04276-174">컴파일러는 `cref` 특성에 설명된 형식을 찾을 때 모든 `using` 문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="04276-174">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="04276-175">\<summary> 태그는 Visual Studio 내의 IntelliSense에서 형식 또는 멤버에 대한 추가 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04276-175">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="04276-176">XML 파일은 형식 및 멤버에 대한 전체 정보를 제공하지 않습니다(예: 형식 정보가 포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="04276-176">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="04276-177">형식 또는 멤버에 대한 전체 정보를 가져오려면 실제 형식 또는 멤버에 대한 리플렉션과 함께 문서 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04276-177">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04276-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04276-178">See Also</span></span>  
 [<span data-ttu-id="04276-179">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="04276-179">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04276-180">/doc (C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="04276-180">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="04276-181">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="04276-181">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
